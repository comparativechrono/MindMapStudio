# Mind Map Studio

A fully offline, privacy-first mind mapping tool that runs entirely in your browser. No accounts, no data transmission, no dependencies — just a single HTML file.

## Who is this for?

Mind Map Studio is designed for environments where putting information into online tools would be inappropriate or impossible, including:

- **Counselling and therapy** — sorting thoughts, feelings, and connections during sessions
- **Clinical settings** — mapping symptoms, care pathways, or patient-reported concerns
- **Custodial environments** — structured activities where internet access is restricted
- **Workshops and group work** — brainstorming and idea-sorting without cloud tools
- **Air-gapped networks** — any setting where no internet connection is available

It replicates the experience of cutting phrases out on pieces of paper and moving them around on a table — but with the ability to draw connections, sort cards into areas, add labels, and save or print the result.

## How to use it

### Online (GitHub Pages)

Visit the hosted version and start using it immediately. Once the page loads, everything runs locally in your browser — no further internet access is needed.

### Offline

Download `index.html` (or save the GitHub Pages version with Ctrl/Cmd+S) and open it directly in any modern browser. It works identically with no internet connection. You can distribute the file via USB stick, shared drive, email, or any other method.

## Features

### Cards and text

- **Phrase cards** — type a list of phrases (one per line) and add them all at once, or paste a list straight onto the canvas
- **Quick cards** — double-click (or double-tap) the canvas to add a single card where you want it
- **Multi-line text** — Enter finishes typing, Shift+Enter starts a new line
- **Card colours** — twelve colours, and three text sizes for emphasis
- **Labels** — free text annotations anywhere on the canvas, in six colours and any size

### Connections

- **Drag to connect** — drag from the dot on a card's edge to another card; drop on empty space to create a new connected card
- **Tab** — adds a new card already connected to the selected one, for fast brainstorming
- **Arrows** — none, one way, the other way or both ways, and lines can be reversed
- **Line labels** — e.g. "leads to", "makes worse", "helps"
- **Line styles** — thin, medium or thick; solid, dashed or dotted; straight or curved; seven colours
- **Select first, then change** — clicking a line selects it, it is never deleted by accident

### Organising

- **Multi-select** — Shift+click, or drag a box with the Select tool (or Shift+drag)
- **Move, duplicate, copy and paste** groups of cards
- **Arrange** — align edges or centres, space out evenly, or tidy into a grid
- **Sorting areas** — coloured rectangles or ovals to sort cards into; moving an area carries its cards with it
- **Colour key** — note what each card colour means; it appears in exports too
- **Undo and redo** — for everything, including shuffle, float, deletes and template changes

### Templates

Ready-made layouts, all fully editable:

- **Five areas** — situation, thoughts, emotions, physical sensations and behaviours, and how each affects the others
- **Circle of control** — in my control, things I can influence, outside my control
- **Weighing up a change** — the good and not so good sides of changing and of staying the same
- **Circles of support** — the people, groups and services in someone's life, by how close they feel
- **Timeline** — past, present and future
- **Values card sort** — eighteen common values to sort into very, quite and not so important

### Exploration tools

- **Shuffle** — randomly rearrange cards to break fixed thinking patterns
- **Float** — cards drift gently around the screen; tap one to freeze it in place as ideas emerge

### Saving, exporting and printing

- **Save to a file** — download the map as a `.json` file to keep, back up, or open on another computer
- **Password-protected files** — optionally encrypt the file (AES-256-GCM, with the key derived from your password using PBKDF2-SHA-256, 600,000 iterations). Without the password the file cannot be opened
- **Export** — PNG image or SVG vector image, on a paper or white background, with the map title and date at the top if you like
- **Print** — a print-ready page, automatically landscape or portrait

### Mobile support

- Full touch support — drag cards, pinch to zoom, double-tap to edit
- A toolbar appears beside whatever is selected, so styling works without the side panel
- Responsive layout with slide-out panel and bottom toolbar
- Works on phones and tablets

## Privacy

- **Network lock** — the page carries a Content Security Policy that blocks every network request: no remote images, fonts, scripts, frames or connections, even if content copied from a website is pasted in
- **Nothing stored by default** — "Remember my work here" is off unless you turn it on, so nothing about your maps is written to the browser. Turn it off on shared or public computers
- **When remembering is on** — maps are auto-saved in this browser's local storage and listed under **My maps**, for example one map per client. Turning remembering off asks whether to remove the maps already saved there
- **Unsaved-work warning** — when nothing is being stored, the browser warns you before you close a map that hasn't been saved to a file
- **No accounts, analytics, cookies or fingerprinting**
- The map title is never shown in the browser tab, so it isn't exposed on a shared screen

This makes it suitable for use in:

- Counselling and therapy sessions
- Clinical and healthcare settings
- Custodial and secure environments
- Schools and safeguarding contexts
- Any situation where data sovereignty matters

## Keyboard shortcuts

| Keys | Action |
|---|---|
| Double-click | Add a card |
| Enter | Edit the selected card, label, area or line label |
| Shift+Enter | New line while typing |
| Tab | Add a card connected to the selected one |
| Delete / Backspace | Delete what is selected |
| Ctrl+Z / Ctrl+Shift+Z | Undo / redo |
| Ctrl+C, Ctrl+X, Ctrl+V | Copy, cut, paste (pasting a list of lines makes cards) |
| Ctrl+D | Duplicate |
| Ctrl+A | Select everything |
| Shift+drag | Select an area of the canvas |
| Arrow keys | Nudge the selection (Shift for bigger steps); pan when nothing is selected |
| V, S, C, L | Move, Select, Connect and Label tools |
| N | New card in the middle of the view |
| F | Fit everything in view |
| + / − | Zoom in / out |
| Ctrl+S | Save to a file |
| Ctrl+O | Open a file |
| Ctrl+P | Export or print |
| Esc | Cancel, or clear the selection |

On a Mac, use Cmd instead of Ctrl.

## Getting Started

### Option 1: GitHub Pages (recommended)

Fork or clone this repository. The `index.html` file is the entire application. Enable GitHub Pages in your repository settings and it will be live at your GitHub Pages URL.

### Option 2: Local file

Download `index.html` and open it directly in your browser. That's it. No server, no build step, no npm install.

### Option 3: Any static host

Drop `index.html` on any static file host — Netlify, Vercel, an internal server, a USB stick. It's a single self-contained file.

## Technical Details

- Single HTML file, no build process, no frameworks, no libraries, no dependencies
- The map is held in a plain data model; the page is drawn from it, so undo, multi-select and exports never depend on reading the screen
- Card sizes are cached as they change, so dragging and floating never force the browser to re-measure; only the lines attached to moving cards are redrawn
- One layout routine feeds the SVG export, the PNG export and printing, so all three match
- Exported images stay within the canvas size limits of phones and tablets
- System font stack (no web font downloads)
- Session files are human-readable JSON (unless password-protected)
- Uses only standard browser features found in current Chrome, Edge, Firefox and Safari: Pointer Events for mouse, touch and pen, ResizeObserver, and the Web Crypto API for password protection

## Session File Format

Saved `.json` files (version 2) look like this:

```json
{
  "app": "Mind Map Studio",
  "version": 2,
  "id": "map-…",
  "title": "Session 3",
  "created": "2026-10-16T10:30:00.000Z",
  "modified": "2026-10-16T11:05:00.000Z",
  "cards": [
    { "id": "card-1", "x": 100, "y": 200, "text": "Main idea", "color": "#ffffff", "size": "normal", "z": 1 }
  ],
  "labels": [
    { "id": "label-1", "x": 300, "y": 150, "text": "Note", "fontSize": 16, "color": "#8a8480", "z": 2 }
  ],
  "zones": [
    { "id": "zone-1", "x": 0, "y": 0, "w": 380, "h": 280, "title": "Thoughts", "color": "#e2eaf5", "shape": "rect", "z": 3 }
  ],
  "connections": [
    { "id": "link-1", "from": "card-1", "to": "zone-1", "color": "#2c2825", "width": 1.5,
      "style": "solid", "arrow": "end", "label": "leads to", "curved": false,
      "fromId": "card-1", "toId": "zone-1", "thickness": 1.5 }
  ],
  "legend": { "visible": true, "x": 600, "y": 40, "labels": { "#ffffff": "Thoughts" } },
  "view": { "panX": 0, "panY": 0, "zoom": 1 }
}
```

- `style` is `solid`, `dashed` or `dotted`; `arrow` is `none`, `end`, `start` or `both`; `shape` is `rect` or `ellipse`; `size` is `normal`, `large` or `xlarge`
- Connections join cards and sorting areas
- `fromId`, `toId` and `thickness` repeat `from`, `to` and `width` so that the previous version of the app can still open the cards and lines in a newer file
- **Version 1 files open unchanged**, and a map auto-saved by the previous version is moved into My maps the first time this version runs
- Password-protected files (`.mindmap`) are a JSON envelope with `format: "mindmap-studio-encrypted"`, the PBKDF2 salt and iteration count, the AES-GCM IV, and the encrypted map; nothing about the map, including its title, is readable without the password

You could write scripts to generate session files programmatically if needed.

## Contributing

Issues and pull requests are welcome. The guiding principles are:

- **Stay offline** — no external dependencies, ever
- **Stay simple** — one file, no build step
- **Stay private** — no data leaves the device
- **Stay accessible** — works on any device with a browser

## Licence

This tool is free to use, modify, and distribute. If you use it in a professional or clinical setting and find it helpful, consider sharing it with colleagues who might benefit.
