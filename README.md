# Unity WebGL Launcher Chrome Extension

A Chrome extension that enables local execution of Unity WebGL builds by virtual file serving.

![Preview](https://github.com/user-attachments/assets/9276f664-3d0d-4ce1-a4a2-824a69bdad91)

## Features

- 🚀 **Local Unity WebGL Execution**: Run Unity WebGL builds directly from your Chrome browser
- 📂 **Folder Selection**: Use the Chrome File System Access API to select WebGL build folders
- 🌐 **Virtual File Server**: Dynamically serves game files while maintaining security policies
- 🛠 **Error Handling**: Friendly error messages and troubleshooting guidance
- 📁 **Folder Structure Visualization**: Preview selected folder contents before launch

## Requirements

- Unity WebGL builds containing `index.html`
- Extension permissions enabled for file system access

## Installation

1. Clone/download this repository or download the [Siesta-Launcher.zip](https://github.com/TolgaDurman/Siesta-Launcher/releases)
2. Open Chrome and navigate to `chrome://extensions/`
3. Enable "Developer mode" (toggle in top-right corner)
4. Click "Load unpacked" and select the repository folder
5. Pin the extension for easy access

## Usage

1. Click the extension icon in your toolbar
2. Select "Open Launcher"
3. In the player tab:
   - Click **Select WebGL Folder** and choose your build directory
   - Verify folder structure appears correctly
   - Click **Play** to launch the game

## Troubleshooting

**Common Issues:**
- 🚫 "Browser not supported": Use latest Chrome version
- 🔍 "index.html not found": Verify your Unity build output
- 🔐 Permission errors: Allow file access when prompted
- 🕒 Timeout issues: Ensure large assets are properly indexed

**Tips:**
- First-run may require explicit permission grants
- Hard refresh (Ctrl+Shift+R) if files aren't updating
- Ensure CORS policies are properly configured in Unity builds

## Technical Details

**Key Components:**
- Service Worker-based virtual file system
- DOM manipulation protection through script extraction
- Cross-origin isolation headers
- Persistent tab-based file access management

**Architecture:**
```plaintext
background.js (Service Worker)
├── Handles file requests
├── Manages tab communication
└── Implements virtual file server

player.js
├── Folder selection handler
├── Directory structure validation
└── File content processing

popup.js
└── Extension launcher
