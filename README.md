# Files Converter 🔄

A powerful web-based file converter that supports multiple file formats. Upload any supported file and convert it to your desired format with a beautiful, user-friendly interface.

## Features

- 🎨 **Beautiful UI** - Modern, responsive design with drag-and-drop support
- 📁 **Multiple Format Support** - Convert between various file formats
- 🔒 **Secure** - Files are processed and deleted immediately after conversion
- ⚡ **Fast** - Quick conversion processing
- 📱 **Responsive** - Works on desktop and mobile devices

## Supported Conversions

### Image Formats
- **PNG** ↔ JPG, JPEG, PDF, BMP, GIF, TIFF, WebP, ICO
- **JPG/JPEG** ↔ PNG, PDF, BMP, GIF, TIFF, WebP, ICO
- **BMP** ↔ PNG, JPG, PDF, GIF, TIFF, WebP
- **GIF** ↔ PNG, JPG, PDF, BMP, TIFF, WebP
- **TIFF** ↔ PNG, JPG, PDF, BMP, GIF, WebP
- **WebP** ↔ PNG, JPG, PDF, BMP, GIF, TIFF
- **ICO** ↔ PNG, JPG, PDF, BMP

### Document Formats
- **PDF** → TXT, PNG, JPG
- **TXT** → PDF, DOCX
- **DOCX** → TXT, PDF

## Installation

### Prerequisites
- Python 3.8 or higher
- pip (Python package installer)

### Setup

1. Clone the repository:
```bash
git clone https://github.com/dev-Basscee/Files-Converter.git
cd Files-Converter
```

2. Create a virtual environment (recommended):
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

3. Install dependencies:
```bash
pip install -r requirements.txt
```

### For PDF to Image conversion (optional but recommended):
On Ubuntu/Debian:
```bash
sudo apt-get install poppler-utils
```

On macOS:
```bash
brew install poppler
```

On Windows:
- Download poppler from: https://github.com/oschwartz10612/poppler-windows/releases
- Add the `bin/` folder to your PATH

## Usage

1. Start the application:
```bash
python app.py
```

2. Open your browser and navigate to:
```
http://localhost:5000
```

3. Use the application:
   - Click the upload area or drag and drop a file
   - Select your desired output format
   - Click "Convert File"
   - The converted file will download automatically

## Project Structure

```
Files-Converter/
├── app.py                 # Flask backend application
├── requirements.txt       # Python dependencies
├── templates/
│   └── index.html        # Frontend HTML/CSS/JS
├── uploads/              # Temporary upload directory (auto-created)
├── converted/            # Temporary conversion directory (auto-created)
└── README.md            # This file
```

## API Endpoints

### GET `/`
Returns the main application interface

### GET `/api/supported-formats`
Returns JSON object of all supported conversion formats

### POST `/api/convert`
Converts uploaded file to specified format
- **Parameters:**
  - `file`: The file to convert (multipart/form-data)
  - `output_format`: Desired output format (string)
- **Returns:** Converted file as download

## Configuration

You can modify the following settings in `app.py`:
- `MAX_CONTENT_LENGTH`: Maximum file size (default: 50MB)
- `UPLOAD_FOLDER`: Directory for temporary uploads
- `CONVERTED_FOLDER`: Directory for temporary conversions

## Security

- Files are automatically deleted after conversion
- Maximum file size limit prevents abuse
- Secure filename handling prevents directory traversal
- Input validation on all file operations

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

This project is open source and available under the MIT License.

## Troubleshooting

### PDF to Image conversion not working
- Make sure poppler-utils is installed (see Installation section)

### Memory issues with large files
- Adjust the `MAX_CONTENT_LENGTH` in app.py
- Consider implementing chunked processing for very large files

### File format not supported
- Check the supported formats list above
- Request new format support by opening an issue

## Future Enhancements

- [ ] Support for more file formats (audio, video, archives)
- [ ] Batch conversion support
- [ ] Cloud storage integration
- [ ] API rate limiting
- [ ] User accounts and conversion history
- [ ] Advanced conversion options (quality, resolution, etc.)