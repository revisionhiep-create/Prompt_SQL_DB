# Prompt SQL DB (ChromeEdge Edition)

A powerful, single-file HTML application for managing AI image generation prompts with SQLite database storage. Automatically extracts metadata from images, organizes with tags and categories, and provides a beautiful interface for browsing and managing your AI art collection.

![GitHub](https://img.shields.io/badge/license-MIT-blue.svg)
![Version](https://img.shields.io/badge/version-1.3.3-green.svg)

## 🎯 Overview

**Prompt SQL DB** is a self-contained web application that helps you organize and manage AI-generated images with their associated prompts, metadata, and tags. Perfect for artists, developers, and AI enthusiasts who work with Stable Diffusion, ComfyUI, Automatic1111, and other AI image generation tools.

### Key Highlights

- ✅ **Single File** - Everything in one HTML file, no installation required
- ✅ **Zero Dependencies** - Works offline, no server needed
- ✅ **SQLite Database** - Portable, exportable database files
- ✅ **Batch Importer** - Sync entire folders of images automatically
- ✅ **Auto-Metadata Extraction** - Parses prompts from PNG/JPEG/WebP (including Flux/Civitai resources)
- ✅ **Bulk Selection** - Select, move, tag, or delete multiple images at once
- ✅ **Performance Optimized** - Handles thousands of images with virtualized cleanup and debounced search
- ✅ **Modern UI** - Glassmorphism design with dark/light themes and keyboard-first workflow

## ✨ Features

### 📸 Image Management
- **Automatic Metadata Extraction** - Extracts prompts, model, seed, steps, CFG, sampler, and more from:
  - PNG files (ComfyUI, A1111 formats)
  - JPEG files (EXIF UserComment with UTF-16 LE/BE support)
  - WebP files
- **Batch Importer (Sync Folder)** - Select a local directory to scan for images, extract metadata, and add them to your database in one go.
- **Full-Screen Detail View** - Click any image to see complete metadata, interactive tags, and one-click copy buttons.
- **Advanced "Smart" Search** - Search by filename, prompt, or use prefixes like `model:sdxl`, `size:1024x1024`, `steps:20`, `cfg:7`, `sampler:euler`, `seed:12345`.
- **Navigation** - Use arrow keys (← →) or click empty black space to close the detail view.

### 🖱️ Selection & Bulk Actions
- **Range Selection** - Hold `Shift` to select a range of images (like Windows/Google Drive).
- **Multi-Selection** - Use `Ctrl` or `Cmd` to toggle selection for individual images.
- **Bulk Actions Bar** - When images are selected, a floating bar appears to:
  - **Bulk Tag**: Apply tags to all selected images.
  - **Bulk Move**: Organize multiple images into a folder.
  - **Bulk Delete**: Remove multiple entries instantly.

### 🏷️ Tag System
- **6 Default Categories** - Art Style, Camera, Lighting, Theme, Mood, Color.
- **Custom Categories & Tags** - Create your own organization system with custom icons.
- **Filter Chips** - Visual indicators below the search bar showing active filters.
- **Auto-Suggest** - Tags automatically suggested from parsed prompt content.
- **Category Drawer** - Collapsible side panel (320px) for deep tagging and filtering.

### 💾 Database Management
- **Quick Save (⚡)** - One-click save to the last opened database file (Chrome/Edge).
- **Auto-Save** - Configurable interval (default 5 mins) to ensure you never lose work.
- **Status Dot** - Visual indicator showing database state (🟢 Saved, 🟡 Unsaved, 🔵 Saving).
- **Drag & Drop** - Drop images to add them, or SQLite files to load your database instantly.
- **Auto-Open** - Remembers your last database and folder for seamless sessions.

### 🎨 User Interface
- **Modern Design** - Glassmorphism effects, smooth animations, and optimized layout.
- **Dark/Light Themes** - Toggle between themes with persistent memory.
- **Responsive Layout** - Adapts to different screen sizes.
- **Toast Notifications** - Contextual feedback for all operations.

## 🚀 Getting Started

### Installation

1. **Download** the appropriate version:
   - **`Prompt SQL DB ChromeEdge Edition.html`** - **Recommended**. Enhanced version with auto-save, sync folder, and advanced file management (Chrome/Edge only).
   - **`Prompt_SQL_DB.html`** - Cross-browser version (works in Firefox, Safari) with core features.
2. **Open** it in any modern web browser.
3. **No installation required** - it's a single HTML file!

### Which Version Should I Use?

**Use `Prompt SQL DB ChromeEdge Edition.html` if you're using Chrome or Edge:**
- ✅ **Batch Importer (Sync Folder)** functionality.
- ✅ **Auto-save** and **Quick Save** (saves directly to file).
- ✅ **Auto-open** database on startup.
- ✅ **Keyboard Shortcuts** for database management.

**Use `Prompt_SQL_DB.html` if you're using Firefox or Safari:**
- ✅ Works in all modern browsers.
- ✅ Standard file save/load (downloads a file).
- ✅ All core management features (tags, folders, smart search).

## ⌨️ Keyboard Shortcuts

| Shortcut | Action |
| :--- | :--- |
| **`Ctrl + S`** | Quick Save to last opened file (Chrome/Edge) |
| **`Ctrl + O`** | Import/Open Database |
| **`Ctrl + E`** | Export/Save Database |
| **`/`** | Focus Search Bar |
| **`T`** | Toggle Dark/Light Theme |
| **`V`** | Toggle View Mode (Grid/List) |
| **`B`** | Toggle Category Drawer |
| **`ESC`** | Close detail view, drawer, or modals |
| **`←` `→`** | Navigate images in detail view |
| **`Shift + Click`** | Select range of images in grid |

## 🗄️ Database Schema

The application uses a portable SQLite structure:

```sql
-- Images table
CREATE TABLE images (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    filename TEXT NOT NULL,
    image_data BLOB NOT NULL,
    positive_prompt TEXT,
    negative_prompt TEXT,
    model TEXT,
    seed TEXT,
    steps TEXT,
    cfg TEXT,
    sampler TEXT,
    size TEXT,
    metadata_text TEXT,
    folder_id INTEGER,
    created_at DATETIME DEFAULT CURRENT_TIMESTAMP
);
-- ... plus tables for image_tags, custom_tags, custom_categories, and folders.
```

## 🔍 Supported Metadata Formats

- **ComfyUI**: Full workflow JSON parsing, recursive node traversal, and resource tracking.
- **Automatic1111 (A1111)**: Complete metadata parsing including LoRAs and styles.
- **Civitai/Flux**: Support for `Civitai resources` JSON blocks and modern embedding formats.
- **JPEG EXIF**: Robust support for `UserComment` with UTF-16 LE/BE detection.

## 📝 Tips & Best Practices

1. **Sync Your Library**: Use the **Sync Folder** button to quickly bring in hundreds of images from your generation folders.
2. **Bulk Tagging**: Use `Shift + Click` to select a range of images, then use the bulk action bar to add tags like "Favorites" or "SDXL" to all of them at once.
3. **Interactive Metadata**: In detail view, click on any prompt, model name, or seed to instantly copy it to your clipboard.
4. **Smart Search**: Try searching `model:flux` or `steps:20` to quickly filter your collection.
5. **Memory Management**: The app automatically revokes Object URLs to keep memory usage low, even with 1000+ images.

## 📄 License

MIT License - Feel free to use, modify, and distribute.

## 🔗 Related Projects

- Based on parsing logic from [Guru Manager](https://github.com/revisionhiep-create/comfyui-history-guru)
- Inspired by the AI art community's need for offline organization.

---

**Made with ❤️ for the AI art community**
