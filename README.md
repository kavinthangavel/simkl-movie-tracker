# 🎬 Simkl Movie Tracker

[![Python Version](https://img.shields.io/badge/python-3.7%2B-blue.svg)](https://www.python.org/downloads/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Platforms](https://img.shields.io/badge/platforms-Windows%20%7C%20macOS%20%7C%20Linux-blue.svg)]()
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)

A powerful cross-platform automatic scrobbler for [Simkl](https://simkl.com) that seamlessly tracks your movie watching progress across multiple media players. Zero configuration required - it just works!

<div align="center">
  <img src="https://eu.simkl.in/img_blog_2012/logo.png" alt="Simkl Logo" width="200"/>
  <br/>
  <em>Inspired by <a href="https://github.com/iamkroot/trakt-scrobbler/">iamkroot's Trakt Scrobbler</a></em>
</div>

## ⚡ Quick Start

### Option 1: Download Pre-built Executable
1. Download the appropriate executable for your platform from the [Releases](https://github.com/kavinthangavel/simkl-movie-tracker/releases) page
2. Run the executable - on first run, you'll be guided through the setup process
3. The application will appear in your system tray

### Option 2: Run from Source

```bash
# Clone repository
git clone https://github.com/kavinthangavel/simkl-movie-tracker.git
cd simkl-movie-tracker

# Install dependencies
pip install -r requirements.txt

# Run the application
python simkl_movie_tracker.py
```

## 🚀 Features

- **Cross-Platform** - Works on Windows, macOS, and Linux
- **Zero Configuration** - Works with most media players out of the box
- **Smart Detection** - Intelligent movie recognition using guessit library
- **Background Operation** - Silent system tray interface with status notifications
- **Progress Tracking** - Monitors viewing progress across sessions
- **Automatic Scrobbling** - Marks movies as watched after 80% completion
- **Offline Support** - Maintains sync backlog when offline
- **Resource Efficient** - Minimal CPU and memory footprint
- **Runtime Detection** - Uses actual movie runtime from Simkl API

## 🎥 Supported Media Players

The application automatically detects media playback in supported players:

### Windows
- VLC Media Player
- MPC-HC/BE
- Windows Media Player
- MPV Player
- PotPlayer
- SMPlayer
- KMPlayer
- GOM Player

### macOS
- VLC
- IINA
- QuickTime Player
- MPV
- MPlayerX

### Linux
- VLC
- MPV
- SMPlayer
- Totem
- Kaffeine
- Parole

## 🛠️ Setup Guide

### System Requirements

- Windows 7/8/10/11, macOS 10.13+, or Linux with desktop environment
- Python 3.7 or higher (only if running from source)
- Simkl account and API credentials

### First-Run Setup

1. **Create a Simkl account and get API credentials**:
   - Create a [Simkl](https://simkl.com) account
   - Go to [Settings > Developer](https://simkl.com/settings/dev)
   - Create a new client to get your Client ID
   
2. **Run the application for the first time**:
   - You'll be prompted to enter your Simkl Client ID
   - The application will guide you through the authentication process
   - After authentication, the app will minimize to your system tray
   
3. **Configure startup options**:
   - The app will ask if you want it to run at startup
   - You can change this later from the tray icon menu

## 🎮 Usage

Once set up, the application runs silently in your system tray:

- **Right-click the tray icon** to access the menu
- The app automatically detects when you're watching movies
- Movies are marked as watched after reaching 80% completion
- You can view currently tracked media and progress from the tray menu

### Command Line Options

```bash
# Run normally with system tray icon
python simkl_movie_tracker.py

# Run in terminal mode without tray icon
python simkl_movie_tracker.py --headless

# Enable detailed logging
python simkl_movie_tracker.py --debug

# Run a movie completion test
python simkl_movie_tracker.py --test
```

## 🔧 Building the Application

To create a standalone executable:

```bash
# Install build dependencies
pip install pyinstaller

# Build for your current platform
python build_app.py
```

This creates an executable in the `dist` directory that can run without Python installed.

## 📋 How It Works

The app works by:

1. Monitoring active windows on your system
2. Detecting media player windows and extracting the movie title
3. Matching the title with Simkl's database
4. Tracking playback progress
5. Marking movies as watched when you've viewed 80%

All of this happens automatically in the background with minimal resource usage.

## 🔍 Troubleshooting

| Issue | Solution |
|-------|----------|
| Movie not detected | Ensure media player displays the filename in its window title |
| Authentication fails | Double-check your Client ID and try again |
| Incorrect movie match | Include the year in filename: "Movie (2023).mp4" |
| Tray icon not visible | Check system tray settings or try `--headless` mode |
| App crashes on startup | Check log file for errors (see status menu for location) |
| Window detection issues | Some desktop environments may require additional permissions |

## 📝 Development Notes

This project uses:
- `platformdirs` for cross-platform file management
- `pystray` for system tray functionality
- `guessit` for intelligent movie title parsing
- Platform-specific modules for window detection

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 👏 Acknowledgments

- [Simkl](https://simkl.com) for their excellent API
- [iamkroot's Trakt Scrobbler](https://github.com/iamkroot/trakt-scrobbler/) for inspiration
- [guessit](https://github.com/guessit-io/guessit) for powerful video filename parsing
- [pystray](https://github.com/moses-palmer/pystray) for cross-platform system tray support
