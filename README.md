# 🎵 Match – Intelligent Playlist Matcher for Windows

Match is a professional Windows desktop application that automatically
matches music playlists to your local audio library using advanced fuzzy
matching and version-aware scoring.

It is designed for DJs, music collectors, and power users who work with
large music libraries, broken playlists, or exported streaming playlists.

---

## ✨ Key Features

### Core
- Automatic playlist-to-library matching
- Intelligent fuzzy matching engine
- Version-aware scoring (radio edit, remix, instrumental, etc.)
- Duplicate prevention
- Fast indexed scanning for large libraries

### Playlist & Streaming Support
- Import playlists exported from streaming platforms
  (Spotify, Apple Music, YouTube Music, etc.)
- Rebuild streaming playlists using local audio files
- Supports M3U / M3U8 / CSV / XSPF formats

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

### Text Normalization
- Lowercasing
- Removal of brackets and parentheses
- Special character filtering
- Whitespace normalization

Example:
"Track Name (Radio Edit) - 2023"
→ "track name radio edit 2023"

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

This allows fast matching of large music libraries and exported streaming
playlists.

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

---

## 📥 Download & Installation (Recommended)

Match is distributed via an official downloader.

1. Go to the **Releases** page:
   https://github.com/jordy3lsen/match/releases

2. Download:
   **Match_Installer.exe**

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

---

## 🛠️ Build From Source (Developers)

```bash
git clone https://github.com/jordy3lsen/match.git
cd Match
pip install -r requirements.txt
python main.py
⚙️ Configuration
Settings location:

%APPDATA%\Match\settings.json
🔒 Licensing
Device-bound licensing system with local verification.

🤝 Contributing
Pull requests and feature suggestions are welcome.

📄 License
MIT License

👤 Author
Developed by Jordy Elsen

⭐ Support
Star the repo, report bugs, and share feedback.
