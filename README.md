# Video Converter

A web application that converts videos to MP4 format directly in your browser using FFmpeg.wasm.

## 📋 Description

This project is a video converter that works entirely client-side, with no need to upload files to external servers. It allows users to convert videos from various formats (MP4, WebM, MOV, AVI, etc.) to MP4 using WebAssembly technology.

## ✨ Features

- **Client-side conversion**: All processing happens directly in the browser
- **Multiple format support**: Accepts various video formats
- **Drag and drop**: Easy file selection with drag & drop functionality
- **PWA support**: Can be installed as a Progressive Web App
- **Real-time progress**: Shows conversion progress in real-time
- **No server upload**: Your files never leave your computer
- **Detailed logging**: Provides detailed conversion logs

## 🚀 Quick Start

### Prerequisites

- A modern web browser with WebAssembly support
- For mobile devices: iOS 14+ or Android Chrome 80+

### Installation

Simply open `index.html` in a web browser or host the files on a web server.

```bash
# Using a simple HTTP server (Python 3)
python -m http.server 8000

# Using Node.js http-server
npx http-server
```

Then navigate to `http://localhost:8000` in your browser.

## 📁 Project Structure

```
www/
├── index.html          # Main application file
├── ffmpeg.js           # FFmpeg.wasm library
├── manifest.json       # PWA manifest
├── icons/              # App icons for PWA
│   ├── favicon.ico
│   └── icon-152x152.png
└── sw.js              # Service Worker
```

## 🛠️ Usage

1. **Open the application** in your web browser
2. **Select a video file**:
   - Click the "Click to select video file" area
   - Or drag and drop a video file onto the area
3. **Review file information** (name and size will be displayed)
4. **Click "Convert to MP4"** to start the conversion process
5. **Wait for processing** (progress will be shown)
6. **Download the converted file** when the process completes

## 🔧 Technical Details

### Technologies Used

- **HTML5**: Application structure
- **CSS3**: Styling and responsive design
- **JavaScript**: Application logic
- **FFmpeg.wasm**: WebAssembly port of FFmpeg for video processing
- **Service Workers**: For PWA functionality
- **Web Manifest**: For app installation

### Browser Compatibility

- Chrome 80+ (recommended)
- Firefox 79+
- Safari 14+
- Edge 79+

### File Size Limitations

Due to browser memory constraints, very large video files (>500MB) may cause performance issues or crashes. For best results, use files under 200MB.

## 🎨 Customization

### Styling

The application uses CSS variables for easy customization. Key color variables in the CSS:

```css
:root {
    --primary-bg: #1a1a2e;
    --secondary-bg: #16213e;
    --accent-color: #4cc9f0;
    --success-color: #00db9f;
}
```

### Conversion Settings

The current conversion uses a simple FFmpeg command:
```javascript
const args = ['-i', inputFilename, outputFilename, '-y', '-nostdin', '-loglevel', 'info'];
```

You can modify this command in the `convertVideo()` function to change encoding settings.

## 📱 Progressive Web App

This application can be installed as a PWA on supported devices:

- **Desktop**: Chrome, Edge, or Safari - look for the install button
- **Mobile**: Use "Add to Home Screen" in your browser menu

### PWA Features

- Offline functionality (cached resources)
- App-like experience when installed
- Platform-specific icons

## ⚠️ Limitations

1. **Performance**: Conversion speed depends on your device's processing power
2. **File size**: Large files may cause browser memory issues
3. **Format support**: Limited to FFmpeg.wasm's supported codecs
4. **Mobile performance**: May be slower on mobile devices

## 🔒 Privacy & Security

- All processing happens locally in your browser
- No files are uploaded to external servers
- No tracking or analytics are included
- The application works offline after initial load

## 🐛 Troubleshooting

### Common Issues

**"FFmpeg failed to load"**
- Check your internet connection (required for initial FFmpeg.wasm download)
- Ensure WebAssembly is supported by your browser

**"Conversion takes too long"**
- Larger files take more time to process
- Try using smaller files or lower resolution videos

**"Browser crashes"**
- The file might be too large for your device's memory
- Close other tabs to free up memory

## 🤝 Contributing

Contributions are welcome! Please feel free to submit pull requests or open issues for bugs and feature requests.

## 📄 License

This project is open source. Feel free to use and modify as needed.

## 🙏 Acknowledgments

- [FFmpeg](https://ffmpeg.org/) for the powerful multimedia framework
- [FFmpeg.wasm](https://github.com/souzamonteiro/ffmpeg-wasm-browser.git) for the WebAssembly port
- All contributors and testers
