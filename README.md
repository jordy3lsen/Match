# 🎵 Match – Intelligent Playlist Matcher for Windows

Match is a professional Windows desktop application that automatically
matches music playlists to your local audio library using advanced fuzzy
matching and version-aware scoring.

It is designed for DJs, music collectors, and power users who work with
large music libraries and broken or incomplete playlists.

---

## ✨ Key Features

### Core
- Automatic playlist-to-library matching
- Intelligent fuzzy matching engine
- Version-aware scoring (radio edit, remix, instrumental, etc.)
- Duplicate prevention
- Fast indexed scanning for large libraries

### Playlist Formats
- M3U / M3U8 (Extended playlists)
- CSV
- XSPF (XML Shareable Playlist Format)

### Interface
- Clean PySide6 (Qt6) GUI
- Frameless custom window
- Real-time progress updates
- Fully non-blocking background processing

### System
- Device-bound licensing system
- Automatic update checking
- Persistent user settings
- Standalone Windows executable

---

## 🧠 How Matching Works

Each playlist track is processed through the following pipeline:

Normalize → Exact Match → Token Match → Fuzzy Match → Score → Threshold

markdown
Copy code

### Text Normalization
- Lowercasing
- Removal of brackets and parentheses
- Special character filtering
- Whitespace normalization

Example:
"Track Name (Radio Edit) - 2023"
→ "track name radio edit 2023"

yaml
Copy code

### Version Scoring

**Positive weighting**
| Keyword | Score |
|-------|-------|
| radio edit | +4 |
| remix | +2 |
| club | +2 |

**Negative weighting**
| Keyword | Score |
|--------|-------|
| karaoke | -6 |
| instrumental | -5 |
| cover | -5 |

Minimum match threshold: **3**

---

## ⚡ Performance

Match uses a two-level indexing system:

- **Title Index**  
  `normalized_title → track list`

- **Token Index**  
  `word → track list`

This drastically reduces comparison cost and allows fast matching even
with thousands of audio files.

---

## 🏗️ Project Architecture

Match follows a modular MVC-style structure:

UI (Qt)
↓
Controller
↓
Engine
↓
Filesystem / Network

yaml
Copy code

### Main Directories

| Folder | Purpose |
|------|--------|
| `ui_qt/` | GUI components |
| `controller/` | Workflow & threading |
| `engine/` | Matching logic |
| `licensing/` | License & update handling |
| `assets/` | Icons and resources |

---

## 📥 Download & Installation (Recommended)

Match is distributed via an official downloader.

1. Go to the **Releases** page:
   https://github.com/YOUR_USERNAME/YOUR_REPO/releases

2. Download:
   **MatchDownloader.exe**

3. Run the downloader and follow the instructions

The downloader automatically fetches the latest installer and updates.

---

## 🔐 Security & Safety

- No bundled adware
- No telemetry
- No data collection
- No crypto-miners
- No hidden installers

All binaries are built from this repository and published via GitHub
Releases.  
Source code is fully inspectable.

---

## 🛠️ Build From Source (Developers)

### Requirements
- Windows 10/11
- Python 3.9+
- Git

### Setup
```bash
git clone https://github.com/jordy3lsen/match.git
cd Match
pip install -r requirements.txt
python main.py
⚙️ Configuration
Settings are stored at:

shell
Copy code
%APPDATA%\Match\settings.json
Example:

json
Copy code
{
  "songs_folder": "D:/Music/Library",
  "playlist_input": "D:/Music/Playlists/Input",
  "playlist_output": "D:/Music/Playlists/Output",
  "playlist_type": "m3u8",
  "check_updates": true
}
🔒 Licensing
Match uses a device-bound licensing system:

Machine fingerprinting

Local license storage

Server-side verification

License file location:

shell
Copy code
%APPDATA%\Match\license.json
🐞 Known Limitations
Limited UI error reporting

Manual thread management

No automated test suite (yet)

🤝 Contributing
Contributions are welcome.

Fork the repository

Create a feature branch

Commit your changes

Open a Pull Request

Please follow PEP8 conventions.

📄 License
MIT License
See LICENSE for details.

👤 Author
Developed by Jordy Elsen

⭐ Support
If you find Match useful:

Star the repository

Report bugs

Suggest features

Share with others
