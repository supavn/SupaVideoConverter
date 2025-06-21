# SupaVideoConverter

A cross-platform desktop application for video format conversion built with Electron, React, and Ant Design, built by Supa

## Features

- **Multi-format Support**: Convert MP4, AVI, MOV, MKV, WMV, FLV, WEBM, M4V, 3GP, OGV to MP4
- **Quality Options**: Multiple quality presets (Low, Medium, High, Lossless) and custom bitrate settings
- **Resolution Scaling**: Support for 720p, 1080p, and custom resolutions
- **Batch Processing**: Convert multiple files at once
- **Progress Tracking**: Real-time conversion progress with estimated time remaining
- **Drag & Drop**: Easy file selection with drag and drop support
- **Cross-platform**: Works on Windows and macOS

## Tech Stack

- **Electron** ^28.0.0 - Desktop app framework
- **React** ^18.2.0 - Frontend UI framework
- **Ant Design** ^5.12.0 - UI component library
- **Vite** ^5.0.0 - Build tool
- **FFmpeg** - Video processing engine
- **fluent-ffmpeg** ^2.1.2 - Node.js FFmpeg wrapper

## Installation

1. Clone the repository:
```bash
git clone <repository-url>
cd video-converter-app
```

2. Install dependencies:
```bash
npm install
```

## Development

To run the app in development mode:

```bash
npm run electron:dev
```

This will:
1. Start the Vite dev server on http://localhost:5173
2. Launch the Electron app automatically
3. Enable hot module replacement for React components

## Building

To build the React app:
```bash
npm run build
```

To package the Electron app for distribution:
```bash
npm run electron:dist
```

This will create distributables in the `dist` folder:
- **Windows**: `.exe` installer
- **macOS**: `.dmg` package

## Scripts

- `npm run dev` - Start Vite dev server only
- `npm run build` - Build React app for production
- `npm run preview` - Preview production build
- `npm run electron` - Run Electron with built files
- `npm run electron:dev` - Run in development mode
- `npm run electron:pack` - Package without building
- `npm run electron:dist` - Build and package for distribution

## Project Structure

```
video-converter-app/
├── src/                           # React application source
│   ├── components/                # React components
│   │   ├── FileInput/            # File selection component
│   │   ├── ConversionSettings/   # Settings configuration
│   │   ├── ProgressTracking/     # Progress display
│   │   └── OutputManagement/     # Results and output
│   ├── hooks/                    # Custom React hooks
│   ├── utils/                    # Utility functions
│   ├── styles/                   # Global styles
│   └── App.jsx                   # Main application
├── electron/                     # Electron main process
│   ├── main.js                   # Main process entry
│   ├── preload.js               # Preload script
│   └── services/                # Backend services
│       ├── VideoProcessor.js    # FFmpeg wrapper
│       ├── FileManager.js       # File operations
│       └── SettingsManager.js   # Settings persistence
├── build/                       # Build configuration
├── resources/                   # Static resources
└── package.json                 # Project configuration
```

## How to Use

1. **Select Files**: Drag and drop video files or use the file browser
2. **Configure Settings**: Choose output resolution, quality, and destination folder
3. **Start Conversion**: Begin the conversion process
4. **Track Progress**: Monitor real-time progress for each file
5. **Access Results**: Open output folder or play converted files

## Supported Formats

**Input Formats:**
- MP4, AVI, MOV, MKV, WMV, FLV, WEBM, M4V, 3GP, OGV

**Output Format:**
- MP4 (H.264/AAC)

## Quality Settings

- **Low**: 1 Mbps - Smaller files, lower quality
- **Medium**: 3 Mbps - Balanced quality and size
- **High**: 8 Mbps - Higher quality, larger files
- **Lossless**: 50 Mbps - Maximum quality
- **Custom**: User-defined bitrate (1-50 Mbps)

## Resolution Options

- **Keep Original**: Maintain source resolution
- **720p**: 1280x720 (HD)
- **1080p**: 1920x1080 (Full HD)
- **Custom**: User-defined dimensions

## Requirements

- **Node.js** 16+ (for development)
- **macOS** 10.15+ or **Windows** 10+
- At least 4GB RAM for processing large video files
- Available disk space for output files

## Troubleshooting

### Common Issues

1. **FFmpeg not found**: The app includes FFmpeg binaries, but if you encounter issues, ensure the app has proper permissions.

2. **Large file processing**: For files over 4GB, ensure you have sufficient disk space and RAM.

3. **Conversion fails**: Check that the input file is not corrupted and the output directory has write permissions.

### Development Issues

1. **Electron won't start**: Ensure all dependencies are installed with `npm install`

2. **Hot reload not working**: Check that Vite dev server is running on port 5173

3. **Build fails**: Clear node_modules and reinstall dependencies

## License

MIT License - see LICENSE file for details

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

## Support

For issues and feature requests, please create an issue in the repository.