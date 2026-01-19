# MHT2PDF Converter

English | [简体中文](README.md)

![Python](https://img.shields.io/badge/python-3.10-blue.svg)
![License](https://img.shields.io/badge/license-MIT-green.svg)
![Language](https://img.shields.io/badge/language-Python-blue.svg)

A desktop application designed for converting MHT/HTML files to PDF, specifically tailored for personal information documents. Built with PyQt5 and QtWebEngine.

## Overview

MHT2PDF is a professional document format conversion tool designed to convert various personal information MHT (MHTML) and HTML files into high-quality PDF documents. It's particularly suitable for converting medical reports, transcripts, certificates, bills, health records, and other important personal documents. With a user-friendly graphical interface and support for both single-file and batch conversion modes, it helps you easily convert scattered web archive files into PDF format that's convenient for saving and printing.

## Typical Use Cases

- **Healthcare**: Medical examination reports, medical records, test results, vaccination records
- **Education**: School transcripts, exam results, study certificates, training certificates
- **Finance**: Bank statements, transaction records, electronic invoices, insurance documents
- **Certificates**: Various electronic certificates, qualification certificates, honor certificates
- **Government Services**: Social security inquiries, provident fund records, government service records
- **Other Documents**: Any web archive files that need to be saved or printed

## Core Features

### Single File Conversion Mode
- Import single MHT or HTML files
- Real-time file content preview
- Visual web page rendering
- One-click export to standard PDF format
- Progress bar showing conversion status

### Batch Conversion Mode
- Select multiple MHT/MHTML files simultaneously
- Import files from folders in batch
- Option to include subfolders
- Automatically maintain original folder structure
- Optional deletion of original files after conversion
- Detailed conversion log recording
- Real-time display of conversion progress and status

### File Processing Features
- Automatic Quoted-Printable encoding decoding
- Base64 image resource processing
- Embedded resource extraction support
- Automatic Chinese encoding handling
- Smart A4 page layout optimization
- Automatic table and image adaptation

## Supported MHT File Styles

This tool can convert MHT files containing the following content and styles:

### Text Content
- Standard text paragraphs with various fonts and sizes
- Heading styles (H1-H6)
- Text decorations: bold, italic, underline
- Superscript and subscript text
- Lists (ordered lists, unordered lists, nested lists)
- Blockquotes and code blocks

### Table Styles
- Standard HTML tables
- Tables with and without borders
- Cell merging (rowspan, colspan)
- Table background colors and border styles
- Nested tables
- Header and body styles
- Automatic A4 page width adaptation

### Images and Media
- Base64 encoded embedded images
- Common image formats: JPG, PNG, GIF, BMP
- Automatic image scaling to fit page
- Image alignment (left, center, right)
- Text-image mixed layouts

### CSS Styles
- Inline styles
- Internal stylesheets (style tags)
- Text and background colors
- Margins and padding
- Border styles and rounded corners
- Font family, size, and weight
- Text alignment and line height
- Basic Flexbox and Grid layouts

### Page Layout
- Responsive layout auto-adaptation
- Multi-column layouts
- Floating elements
- Absolute and relative positioning
- Optimized pagination control

### Special Elements
- Hyperlinks (converted to clickable links in PDF)
- Horizontal rules
- Blockquotes
- Preformatted text
- Form elements (display only, no interactive functionality)

### Encoding Support
- UTF-8, GBK, GB2312, and other Chinese encodings
- Automatic Quoted-Printable decoding
- Automatic Base64 resource decoding
- Full Unicode character support

### Known Limitations
- JavaScript-generated content not supported
- Flash, ActiveX, and other plugin content cannot be displayed
- Audio and video show placeholders only
- Complex CSS3 animations and transforms may not work
- iframe embedded content may display incompletely
- Overly complex page layouts may require adjustment

## Technical Architecture

### Programming Language
- Python 3.x

### Core Dependencies
- **PyQt5**: Provides graphical user interface framework
- **PyQtWebEngine**: Provides web rendering engine for high-quality HTML content rendering

### Key Technical Features
- High-fidelity web rendering based on Qt WebEngine
- Multi-threaded batch processing mechanism
- Temporary file management and automatic cleanup
- Signal-slot mechanism for asynchronous operations
- QPrinter for PDF print output

## Project Structure

```
htmToPdf/
├── 2PDF.py                 # Main program file
├── requirements.txt        # Python dependencies list
├── MHT2PDF.spec           # PyInstaller packaging configuration
├── pdf.ico                # Program icon (if exists)
└── build/                 # Build output directory
    └── MHT2PDF/           # Compiled executable
```

## Installation

### Requirements
- Python 3.6 or higher
- Windows OS (recommended)

### Dependency Installation

1. Clone or download the project locally
```bash
cd htmToPdf
```

2. Install dependencies
```bash
pip install -r requirements.txt
```

## Usage

### Running Python Script
```bash
python 2PDF.py
```

### Using Executable File
If packaged as executable, directly run `MHT2PDF.exe`

### Single File Conversion Process
1. Switch to "Single File Conversion" tab
2. Click "Import MHT/HTML File" button
3. Select the file to convert
4. Preview file content
5. Click "Export to PDF" button
6. Choose save location and filename

### Batch Conversion Process
1. Switch to "Batch Conversion" tab
2. Select files by:
   - Clicking "Select Multiple MHT Files" to choose multiple files directly
   - Clicking "Select Folder" to batch import all MHT files in folder
3. Check "Include Subfolders" to recursively search subdirectories
4. (Optional) Click "Select Output Directory" to customize output location
5. (Optional) Check "Delete Original MHT Files After Conversion"
6. Click "Start Batch Conversion" button
7. Wait for conversion to complete and check conversion log

## Feature Details

### MHT File Preprocessing
- Automatic parsing of MHT file MIME structure
- Recognition and processing of Content-Transfer-Encoding
- Extraction of embedded images and style resources
- Conversion to standard HTML temporary files

### PDF Output Optimization
- Automatic A4 paper size adaptation
- Optimized margins (1cm top/bottom, 1.5cm left/right)
- Automatic table width adjustment
- Text wrapping and pagination optimization
- Smart image size scaling

### Batch Processing Mechanism
- Asynchronous processing to avoid UI freezing
- Automatic directory structure preservation
- Failed file statistics and reporting
- Optional original file deletion strategy

## Packaging

The project uses PyInstaller for packaging, with configuration file `MHT2PDF.spec`

### Packaging Command
```bash
pyinstaller MHT2PDF.spec
```

### Packaging Features
- Single-file executable
- Embedded program icon
- No console window
- Includes necessary resource files
- UPX compression to reduce size

## Notes

1. **Resource Usage**: Batch conversion of many files consumes significant memory, recommend processing in batches
2. **File Encoding**: Program automatically handles common encodings, but special encodings may require manual conversion
3. **Original File Deletion**: When using "Delete Original Files" feature, ensure conversion succeeds before deletion
4. **Temporary Files**: Program creates temporary files in system temp directory, automatically cleaned after conversion
5. **Web Complexity**: Overly complex web pages may require longer rendering time

## FAQ

### Q: PDF layout is messy after conversion?
A: This may be due to original HTML style issues. The program has built-in page optimization, but some special styles may need manual adjustment.

### Q: Program unresponsive during batch conversion?
A: Batch conversion processes files one by one, please be patient. Check the conversion log to understand current progress.

### Q: Images not showing in PDF?
A: Check if images are properly embedded in the original MHT file. The program supports Base64 encoded images.

### Q: How to preserve original folder structure?
A: Don't check "Include Subfolders" option during batch conversion, and the program will automatically maintain the original structure in the output directory.

## System Requirements

- Operating System: Windows 7/8/10/11
- Memory: At least 2GB RAM
- Disk Space: At least 100MB available space
- Display: Recommended resolution 1280x720 or higher

## Version Information

- Current Version: 1.0
- Developer: https://github.com/LeeKaiGit

## License

This project is licensed under the MIT License. See [LICENSE](LICENSE) file for details.

## Changelog

### Version 1.0
- Initial release
- Support for single file and batch conversion
- MHT file parsing implementation
- A4 page optimization
- Batch processing mechanism
- Graphical user interface

## Technical Support

If you encounter issues or have suggestions for improvement, feel free to submit an Issue or Pull Request.

## Development Notes

### Code Structure
- `HTMLtoPDFConverter`: Main window class, manages overall interface
- `BatchConverter`: Batch conversion thread class (reserved for extension)
- MHT file parsing using `quopri` and `base64` modules
- PDF generation using `QPrinter` and `QWebEngineView`

### Key Methods
- `preprocess_mht_file()`: MHT file preprocessing
- `export_pdf()`: Single file PDF export
- `process_batch_files()`: Batch file processing
- `inject_rendering_improvements()`: Page rendering optimization

## Contributing

Contributions, bug reports, and feature suggestions are welcome. Before submitting a Pull Request, please ensure code style consistency and passing tests.
