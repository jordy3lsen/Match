Download: https://github.com/jordy3lsen/Match/releases/download/Match/Match_Installer.exe More features: https://match.lemonsqueezy.com/

# 🎵 Match – Intelligent Playlist Matcher for Windows

Match is a professional Windows desktop application that automatically
matches music playlists to your local audio library using advanced fuzzy
matching and version-aware scoring.

It is designed for DJs, music collectors, and power users who work with
large music libraries, broken playlists, or exported streaming playlists.

---

<img width="3071" height="1919" alt="Screenshot 2026-02-02 203031" src="https://github.com/user-attachments/assets/e507b121-50bc-4fcb-a4dd-0eb4dcc49757" />

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

---

## 📥 Download & Installation

Match is distributed via an official downloader.

1. Go to the **Releases** page:
   https://github.com/jordy3lsen/match/releases

2. Download:
   **Match_Installer.exe**

3. Run the downloader and follow the instructions

The downloader automatically fetches the latest installer and updates.

4. Donate or submit email for premium features:
https://match.lemonsqueezy.com/
---

## 🔒 Licensing

Match uses a device-bound licensing system with local verification.
Each license is tied to a specific machine.

---

## 📄 License

This software is proprietary.

All rights are reserved by the author.
Unauthorized copying, modification, or redistribution is prohibited.

See the `LICENSE` file for details.

---

## 👤 Author

Developed by **Jordy Elsen**

---

## ⭐ Support

If you find Match useful:

- Star the repository
- Report bugs
- Share feedback
