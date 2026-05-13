# Mind Map Studio

A fully offline, privacy-first mind mapping tool that runs entirely in your browser. No accounts, no data transmission, no dependencies — just a single HTML file.

## Who is this for?

Mind Map Studio is designed for environments where putting information into online tools would be inappropriate or impossible, including:

- **Counselling and therapy** — sorting thoughts, feelings, and connections during sessions
- **Clinical settings** — mapping symptoms, care pathways, or patient-reported concerns
- **Custodial environments** — structured activities where internet access is restricted
- **Workshops and group work** — brainstorming and idea-sorting without cloud tools
- **Air-gapped networks** — any setting where no internet connection is available

It replicates the experience of cutting phrases out on pieces of paper and moving them around on a table — but with the ability to draw connections, add labels, and save the result as an image.

## How to use it

### Online (GitHub Pages)

Visit the hosted version and start using it immediately. Once the page loads, everything runs locally in your browser — no further internet access is needed.

### Offline

Download `index.html` (or save the GitHub Pages version with Ctrl/Cmd+S) and open it directly in any modern browser. It works identically with no internet connection. You can distribute the file via USB stick, shared drive, email, or any other method.

## Features

### Core

- **Phrase cards** — type a list of phrases (one per line) and add them all to the canvas as movable cards
- **Drag to arrange** — touch or mouse, cards go where you put them
- **Connect** — draw lines between any two cards to show relationships
- **Labels** — add free text annotations anywhere on the canvas
- **Save as image** — export a clean PNG of your mind map

### Exploration Tools

- **Shuffle** — randomly rearrange all cards to break fixed thinking patterns
- **Float** — cards drift gently around the screen; tap one to freeze it in place as ideas emerge

### Customisation

- Card colours (8 palette options)
- Line colours and thickness
- Adjustable label text size
- Zoom and pan (mouse wheel, pinch-to-zoom, or buttons)
- Fit-to-view to frame all content
- Collapsible side panel for full-screen canvas

### Persistence

- **Auto-save** — work is saved automatically in the browser's local storage and restored when you return
- **Export/Import** — download your session as a `.json` file to back up, transfer between devices, or share with a colleague
- **No account required** — no sign-up, no login, no cloud

### Mobile Support

- Full touch support — drag cards, pinch to zoom, tap to connect
- Double-tap a card to edit its text
- Responsive layout with slide-out panel and bottom toolbar
- Works on phones and tablets

## Getting Started

### Option 1: GitHub Pages (recommended)

Fork or clone this repository. The `index.html` file is the entire application. Enable GitHub Pages in your repository settings and it will be live at your GitHub Pages URL.

### Option 2: Local file

Download `index.html` and open it directly in your browser. That's it. No server, no build step, no npm install.

### Option 3: Any static host

Drop `index.html` on any static file host — Netlify, Vercel, an internal server, a USB stick. It's a single self-contained file.

## How to Use

1. **Add phrases** — open the side panel, type phrases (one per line), and tap *Add to Canvas*
2. **Arrange** — drag cards anywhere. Drag empty space to pan. Scroll or pinch to zoom
3. **Connect ideas** — switch to *Connect* mode, tap one card then another to draw a line between them. Tap a line to remove it
4. **Annotate** — switch to *Label* mode and tap the canvas to place text labels
5. **Explore** — use *Shuffle* to randomise positions, or *Float* to let cards drift and freeze them as patterns emerge
6. **Edit text** — double-tap any card or label to edit its text
7. **Save your work** — your session auto-saves in the browser. Use *Export Session to File* to download a backup. Use *Save as Image* to export a PNG

## Privacy & Offline Use

- **Zero network requests** — the file contains no external scripts, fonts, CDNs, or tracking. It makes no HTTP requests whatsoever
- **No data leaves the device** — all state is kept in browser memory and (optionally) local storage
- **No analytics, no cookies, no fingerprinting**
- **Works fully offline** — load it once (or open from a file) and it works without any internet connection
- **Local storage is optional** — clearing browser data removes all traces. The export file is the only persistent artefact

This makes it suitable for use in:

- Counselling and therapy sessions
- Clinical and healthcare settings
- Custodial and secure environments
- Schools and safeguarding contexts
- Any situation where data sovereignty matters

## Technical Details

- Single HTML file, ~2,200 lines, no build process
- Vanilla JavaScript — no frameworks, no libraries, no dependencies
- Image export uses native Canvas 2D API (no html2canvas or other libraries)
- System font stack (no web font downloads)
- Session files are human-readable JSON
- Tested in Chrome, Firefox, Safari, and Edge (desktop and mobile)

## Session File Format

Exported `.json` files contain:

```json
{
  "version": 1,
  "timestamp": "2025-01-15T10:30:00.000Z",
  "cards": [
    { "id": "card-1", "x": 100, "y": 200, "text": "Main idea", "color": "#ffffff" }
  ],
  "labels": [
    { "id": "label-1", "x": 300, "y": 150, "text": "Note", "fontSize": 16 }
  ],
  "connections": [
    { "fromId": "card-1", "toId": "card-2", "color": "#2c2825", "thickness": 1.5 }
  ],
  "counters": { "card": 2, "label": 1, "line": 1 },
  "view": { "panX": 0, "panY": 0, "zoomLevel": 1 }
}
```

This is stable and forward-compatible. You could write scripts to generate session files programmatically if needed.

## Contributing

Issues and pull requests are welcome. The guiding principles are:

- **Stay offline** — no external dependencies, ever
- **Stay simple** — one file, no build step
- **Stay private** — no data leaves the device
- **Stay accessible** — works on any device with a browser

## Licence

This tool is free to use, modify, and distribute. If you use it in a professional or clinical setting and find it helpful, consider sharing it with colleagues who might benefit.
