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

| Feature | Description |
|---|---|
| **Add phrases** | Type one phrase per line and add them as movable cards |
| **Drag to arrange** | Touch or click and drag cards anywhere on the canvas |
| **Edit text** | Double-tap (or double-click) any card or label to edit its text |
| **Connect cards** | Draw lines between cards to show relationships (tap a line to remove it) |
| **Add labels** | Place free text annotations anywhere on the canvas |
| **Card colours** | Choose from 8 card background colours |
| **Line styles** | Choose line colour and thickness |
| **Label sizing** | Adjust label text size from 10px to 48px |
| **Shuffle** | Randomly rearrange all cards to break fixed thinking patterns |
| **Float mode** | Cards drift gently around the screen — tap to freeze them in place as ideas emerge |
| **Save as image** | Export the canvas as a high-resolution PNG |
| **Help screen** | Built-in instructions shown on first load, accessible anytime via Help & Info |

## Privacy

- **No data leaves the device.** Everything runs in-browser using standard HTML, CSS, and JavaScript.
- **No external requests.** No CDNs, no analytics, no fonts loaded from the internet, no tracking of any kind.
- **No storage.** Nothing is saved to cookies, localStorage, or any persistent storage. When you close the tab, the data is gone — by design.
- **No server.** The file does not need a web server. It runs from a `file://` URL, a USB stick, or any static hosting.

## Technical details

- Single HTML file, approximately 1,700 lines including all CSS and JavaScript
- Zero external dependencies
- Works in all modern browsers (Chrome, Firefox, Safari, Edge) on desktop, tablet, and mobile
- Full touch support for phones and tablets
- Image export uses the native Canvas 2D API (no third-party libraries)
- System fonts only — no web font downloads

## Hosting your own copy on GitHub Pages

1. Fork or clone this repository
2. Ensure the file is named `index.html` in the repository root
3. Go to **Settings → Pages → Source**, select your main branch, and save
4. Your instance will be live at `https://yourusername.github.io/your-repo-name/`

## Licence

This tool is free to use, modify, and distribute. If you use it in a professional or clinical setting and find it helpful, consider sharing it with colleagues who might benefit.
