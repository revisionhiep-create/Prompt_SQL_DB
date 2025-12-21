# Prompt SQL DB

A powerful, single-file HTML application for managing AI image generation prompts with SQLite database storage. Automatically extracts metadata from images, organizes with tags and categories, and provides a beautiful interface for browsing and managing your AI art collection.

![GitHub](https://img.shields.io/badge/license-MIT-blue.svg)
![Version](https://img.shields.io/badge/version-1.1-green.svg)

## 🎯 Overview

**Prompt SQL DB** is a self-contained web application that helps you organize and manage AI-generated images with their associated prompts, metadata, and tags. Perfect for artists, developers, and AI enthusiasts who work with Stable Diffusion, ComfyUI, Automatic1111, and other AI image generation tools.

### Key Highlights

- ✅ **Single File** - Everything in one HTML file, no installation required
- ✅ **Zero Dependencies** - Works offline, no server needed
- ✅ **SQLite Database** - Portable, exportable database files
- ✅ **Auto-Metadata Extraction** - Automatically parses prompts from PNG/JPEG/WebP images
- ✅ **Tag-Based Organization** - Flexible tagging system with categories
- ✅ **Performance Optimized** - Handles 1000+ images efficiently
- ✅ **Modern UI** - Beautiful glassmorphism design with dark/light themes

## ✨ Features

### 📸 Image Management
- **Automatic Metadata Extraction** - Extracts prompts, model, seed, steps, CFG, sampler, and more from:
  - PNG files (ComfyUI, A1111 formats)
  - JPEG files (EXIF UserComment with UTF-16 support)
  - WebP files
- **Full-Screen Detail View** - Click any image to see complete metadata
- **Arrow Key Navigation** - Navigate between images in detail view
- **Grid & List Views** - Switch between visual grid and compact list view
- **Folder Organization** - Organize images into virtual folders
- **Search & Filter** - Search by filename, prompts, or tags

### 🏷️ Tag System
- **6 Default Categories** - Art Style, Camera, Lighting, Theme, Mood, Color
- **Custom Categories** - Create your own categories with custom icons
- **Custom Tags** - Add tags to any category
- **Auto-Suggest** - Tags automatically suggested from parsed prompt content
- **Tag Filtering** - Click tags to filter images
- **Category Drawer** - Collapsible side panel for easy tag browsing
- **Visual Indicators** - Categories highlight in blue when tags are selected

### 💾 Database Management
- **SQLite Storage** - Single portable database file
- **Export/Import** - Save and load databases easily
- **Auto-Save** (ChromeEdge Edition) - Automatically saves database every 60 seconds (configurable)
- **Quick Save** (ChromeEdge Edition) - One-click save to last opened file
- **Auto-Open** (ChromeEdge Edition) - Automatically opens database on startup
- **Save on Close** (ChromeEdge Edition) - Attempts to save when closing the page
- **Save Indicator** - Visual indicator showing database state
- **Performance** - Optimized for large collections (1000+ images)

### 🎨 User Interface
- **Modern Design** - Glassmorphism effects with smooth animations
- **Dark/Light Themes** - Toggle between themes with persistence
- **Responsive Layout** - Works on different screen sizes
- **Keyboard Shortcuts** - ESC to close panels, arrow keys for navigation
- **Toast Notifications** - User-friendly feedback for all actions

### 🔧 Advanced Features
- **ComfyUI Support** - Full workflow parsing with recursive node traversal
- **A1111 Support** - Complete Automatic1111 metadata parsing
- **LoRA Detection** - Automatically extracts LoRA information
- **Resource Tracking** - Tracks LoRAs, ControlNets, IP-Adapters
- **UTF-16 Support** - Handles international characters in metadata
- **Error Handling** - Robust error handling with fallback parsing

## 🚀 Getting Started

### Installation

1. **Download** the appropriate version:
   - **`Prompt_SQL_DB.html`** - Cross-browser version (works in Chrome, Edge, Firefox, Safari)
   - **`Prompt SQL DB ChromeEdge Edition.html`** - Enhanced version with auto-save and advanced file management (Chrome/Edge only)
2. **Open** it in any modern web browser
3. **No installation required** - it's a single HTML file!

### Which Version Should I Use?

**Use `Prompt SQL DB ChromeEdge Edition.html` if you're using Chrome or Edge:**
- ✅ Auto-save every 60 seconds (configurable)
- ✅ Quick Save button (saves to last opened file)
- ✅ Auto-open database on startup
- ✅ Save on page close
- ✅ Smart saving option (only save when changes detected)
- ✅ Directory permission management

**Use `Prompt_SQL_DB.html` if you're using Firefox, Safari, or want cross-browser compatibility:**
- ✅ Works in all modern browsers
- ✅ Standard file save/load functionality
- ✅ All core features (metadata extraction, tags, folders, etc.)

### First Time Setup

1. **Create a Database**
   - Click "🆕 Create New Database" on the start screen
   - Or click "➕ Add Image" - database will auto-create

2. **Add Images**
   - Click "➕ Add Image" button
   - Select an image file (PNG, JPEG, or WebP)
   - Metadata will be automatically extracted
   - Add tags and organize as needed

3. **Import Existing Database** (Optional)
   - Click "📥 Import DB" button
   - Select your SQLite database file
   - All your images and tags will load

## 📖 Basic Usage Guide

### Adding Images

1. Click the **"➕ Add Image"** button in the header
2. Select an image file from your computer
3. The app will automatically:
   - Extract metadata (prompts, model, settings, etc.)
   - Suggest tags based on prompt content
4. Review and edit the extracted prompts if needed
5. Select tags from the category blocks
6. Click **"Save"** to add the image to your database

### Organizing with Folders

1. Click the **📁** button next to the folder dropdown
2. Click **"Create Folder"** to add a new folder
3. Select a folder from the dropdown to filter images
4. Move images to folders:
   - Click the **📁** button on any image card
   - Or use the **📁** button in the detail view
   - Select the destination folder

### Using Tags

**Adding Tags:**
- When adding/editing images, click tags in the category blocks
- Selected tags will highlight
- Click **✏️** on any category to add custom tags

**Filtering by Tags:**
- Click the **🏷️** button to open the category drawer
- Click any tag to filter images
- Click the **🧹** button to clear all filters
- Multiple tags can be active at once

**Managing Categories:**
- Click **📂 Add Category** to create custom categories
- Click **⚙️** on any category in the drawer to manage it
- Edit category name, icon, or delete category
- Default categories cannot be deleted but icons can be customized

### Viewing Images

**Grid View:**
- Default view showing image cards with thumbnails
- Hover to see filename and tags
- Click to open full-screen detail view

**List View:**
- Click the **🖼️** button to switch to list view
- Compact rows with 110x110px thumbnails
- Shows: Image, Filename, Model, Sampler, Size, Steps, CFG
- Better for browsing large collections

**Detail View:**
- Click any image to see full details
- Shows: Full image, prompts, all metadata, LoRAs/resources, tags
- Use arrow keys (← → ↑ ↓) to navigate between images
- Press ESC to close

### Searching

- Use the search bar at the top
- Search by:
  - Filename
  - Prompt text (positive or negative)
  - Tags
- Search works across all folders

### Database Management

**Export Database:**
- Click **"💾 Export DB"** button
- Choose save location (Save As dialog)
- File will be saved as `PromptDB.sqlite`

**Import Database:**
- Click **"📥 Import DB"** button
- Select your SQLite database file
- All data will be loaded

**Note:** All changes are saved in memory immediately. Export to save to a file.

**ChromeEdge Edition Users:** Auto-save is enabled by default (saves every 60 seconds). You can configure this in Settings (⚙️ button). Quick Save (⚡) button appears after first export.

## ⌨️ Keyboard Shortcuts

- **ESC** - Close category drawer or detail view
- **← →** - Navigate between images in detail view
- **↑ ↓** - Navigate between images in detail view
- **Click Image** - Open full-screen detail view

## 🗄️ Database Schema

The application uses SQLite with the following structure:

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
    created_at DATETIME DEFAULT CURRENT_TIMESTAMP,
    FOREIGN KEY (folder_id) REFERENCES folders(id) ON DELETE SET NULL
);

-- Image tags (many-to-many)
CREATE TABLE image_tags (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    image_id INTEGER NOT NULL,
    tag_name TEXT NOT NULL,
    category TEXT,
    FOREIGN KEY (image_id) REFERENCES images(id) ON DELETE CASCADE
);

-- Custom tags (user-added tags per category)
CREATE TABLE custom_tags (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    category TEXT NOT NULL,
    tag_name TEXT NOT NULL,
    UNIQUE(category, tag_name)
);

-- Custom categories (user-created categories)
CREATE TABLE custom_categories (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    name TEXT NOT NULL UNIQUE,
    icon TEXT,
    created_at DATETIME DEFAULT CURRENT_TIMESTAMP
);

-- Folders (virtual folder system)
CREATE TABLE folders (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    name TEXT NOT NULL UNIQUE,
    created_at DATETIME DEFAULT CURRENT_TIMESTAMP
);
```

## 🌐 Browser Compatibility

### Prompt_SQL_DB.html (Standard Version)
- ✅ **Chrome/Edge** - Full support (File System Access API for export)
- ✅ **Firefox** - Full support (download fallback for export)
- ✅ **Safari** - Full support (download fallback for export)
- ✅ **Opera** - Full support

### Prompt SQL DB ChromeEdge Edition.html
- ✅ **Chrome/Edge** - Full support with advanced features:
  - Auto-save with configurable interval
  - Quick Save to last opened file
  - Auto-open database on startup
  - Directory permission management
  - Save on page close
- ⚠️ **Firefox/Safari** - Core features work, but advanced file management features require Chrome/Edge

## 🔍 Supported Metadata Formats

### ComfyUI
- Full workflow JSON parsing
- Recursive node traversal
- Extracts: prompts, model, seed, steps, CFG, sampler, LoRAs, ControlNets, IP-Adapters

### Automatic1111 (A1111)
- Standard A1111 format
- Extracts: prompts, model, seed, steps, CFG, sampler, size, LoRAs

### JPEG EXIF
- UTF-16LE/BE encoding support
- EXIF UserComment extraction
- Handles international characters

## 📝 Tips & Best Practices

1. **Organize Early** - Create folders and add tags as you import images
2. **Use Custom Tags** - Add your own tags to categories for better organization
3. **Export Regularly** - Export your database periodically as backup
4. **List View for Large Collections** - Switch to list view when browsing 500+ images
5. **Search Across Folders** - Tags and search work across all folders
6. **Keyboard Navigation** - Use arrow keys in detail view for quick browsing

## 🐛 Troubleshooting

**Images not parsing correctly?**
- Ensure images have metadata embedded (ComfyUI/A1111 saved images)
- Check browser console for error messages
- Try re-saving the image in your AI tool

**Database not loading?**
- Ensure the SQLite file is not corrupted
- Try creating a new database and importing images again
- Check browser console for errors

**Performance issues with many images?**
- Use list view instead of grid view
- Use folders to organize large collections
- Use tag filters to narrow down results

## 📄 License

MIT License - Feel free to use, modify, and distribute.

## 🤝 Contributing

Contributions are welcome! Please feel free to submit issues or pull requests.

## 🔗 Related Projects

- Based on parsing logic from [Guru Manager](https://github.com/revisionhiep-create/comfyui-history-guru)
- Inspired by [PromptCraft](https://github.com/BesianSherifaj-AI/PromptCraft)

## 📧 Support

For issues, questions, or suggestions, please open an issue on GitHub.

---

**Made with ❤️ for the AI art community**
