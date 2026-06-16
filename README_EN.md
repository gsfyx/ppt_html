# PPT Template Editor (`ppt_template.html`)

## Overview

A fully-featured single-page HTML slide editor supporting multi-theme switching, slide management, element editing, animation effects, and fullscreen playback. Data is persisted via `localStorage` with support for JSON/HTML import and export.

## Key Features

### 1. Multi-Theme System

Five built-in visual themes, switchable with a single click across all slides:

| Theme | CSS Class | Description |
|-------|-----------|-------------|
| Tech Blue | `theme-blue` | Blue color palette for technology and enterprise scenarios |
| Violet | `theme-purple` | Purple color palette for creative and artistic scenarios |
| Minimal | `theme-minimal` | Clean, minimalist style for business and reporting scenarios |
| Office | `theme-office` | Classic office style for daily workplace scenarios |

### 2. Slide Management

- **New Slide**: Insert a new slide after the current one
- **Duplicate Slide**: Clone the current slide
- **Delete Slide**: Remove a slide (with confirmation dialog)
- **Drag-and-Drop Sorting**: Reorder slides via the left thumbnail panel
- **Thumbnail Panel**: Collapsible left sidebar for quick slide navigation

### 3. Slide Transitions & Playback

- Multiple transition animations (fade, slide, zoom, etc.)
- Configurable transition duration (default: 500ms)
- Auto-play mode with adjustable interval
- Previous/Next navigation
- Fullscreen playback: hides toolbar and thumbnail panel

### 4. Element Editing

#### 4.1 Text Editing
- **Inline Edit**: Double-click any text element to edit
- **Rich Formatting**: Bold, italic, underline, strikethrough, font size
- **Font Selection**: Supports Chinese and English fonts
- **Text Color**: Text foreground and background color settings
- **Alignment**: Left, center, right, justify
- **Hyperlinks**: Add clickable links to selected elements
- **Comments**: Add annotations to selected elements

#### 4.2 Element Manipulation
- **Drag & Move**: Reposition any element by dragging
- **Resize**: Drag corner handles to resize (with minimum size constraints)
- **Rotation**: Rotate elements freely
- **Marquee Multi-Select**: Click-and-drag to select multiple elements at once
- **Copy & Paste**: Ctrl+C / Ctrl+V support
- **Delete Elements**: Delete or Backspace to remove selected elements

#### 4.3 Element Animations
- **Entrance Effects**: Slide-in (left/right), fade, zoom, bounce, etc.
- **Animation Ordering**: Assign playback order per slide
- **Animation Timing**: Configure duration, delay, and iteration count
- **Start Mode**: Click-triggered, auto-play, and other trigger modes

### 5. Insert Functions

- **Insert Table**: Specify row/column counts to create a table with editable cells
- **Insert Image**: Add images from local files or URLs
- **Insert Icon**: Built-in icon library with SVG icon support
- **Insert Text Box**: Create editable text areas
- **Insert Shape**: Basic shapes (rectangle, circle, triangle, etc.)
- **Insert Hyperlink**: Add links to selected content
- **Insert Comment**: Add annotations to selected content

### 6. Slide Background

- **Background Image**: Set a background image for the current slide or all slides
- **Background Removal**: Clear background from current or all slides
- **Scope Toggle**: Single-page vs. global mode
- **Image Fit**: Cover/contain background display modes

### 7. Data Persistence

- **Auto-Save**: All edits are automatically saved to `localStorage`
- **Cache Key**: File name used as the cache key, supporting multi-document management
- **Undo/Redo**: Full undo/redo history stack (up to 120 states)
- **State Recovery**: Automatically restore the last editing state after page refresh

### 8. Import & Export

- **Export as JSON**: Download complete slide data (styles, elements, animation configs) as a JSON file
- **Export as HTML**: Download as a standalone HTML file
- **Import from JSON**: Load a JSON file to restore slide data
- **Clear Cache**: One-click clear of current document cache

### 9. Bottom Navigation Bar

- Page indicator: Shows current / total pages
- Previous/Next slide buttons
- Fullscreen toggle button
- Auto-play toggle

### 10. Keyboard Shortcuts

| Shortcut | Action |
|----------|--------|
| `←` / `→` | Previous / Next slide |
| `Home` / `End` | Jump to first / last slide |
| `Delete` / `Backspace` | Delete selected elements |
| `Ctrl+C` | Copy selected elements |
| `Ctrl+V` | Paste elements |
| `Ctrl+Z` | Undo |
| `Ctrl+Y` | Redo |
| `F5` / `F` | Enter fullscreen |
| `Esc` | Exit fullscreen |

## Technical Details

- **Pure Frontend**: No backend dependency — runs from a single HTML file
- **CSS Custom Properties**: Theme switching via CSS variable system
- **localStorage Caching**: All data stored locally in the browser
- **Responsive Layout**: Adapts to different screen sizes
- **Touch Support**: Basic touch device interaction support

## Cache Data Structure

```json
{
  "theme": "red",
  "slidesData": [
    {
      "id": "slide-0",
      "background": { "image": "data:image/...", "mode": "cover" },
      "elements": [
        {
          "id": "el-0",
          "type": "text",
          "content": "<p>content</p>",
          "position": { "left": 100, "top": 200 },
          "size": { "width": 600, "height": 300 },
          "style": { "fontFamily": "...", "fontSize": "..." },
          "animation": { "type": "fade-in", "duration": 500 }
        }
      ]
    }
  ],
  "currentIdx": 0,
  "transition": "fade",
  "transitionDurationMs": 500,
  "autoSlideIntervalMs": 5000
}
```

## Use Cases

- Embedded in WPS plugins as a PPT template preview and editing tool
- Standalone use as a lightweight online slide editor
- Integration with other systems as a visual editing frontend for PPT data structures
