# Transfer Prototype

Clickable Ally transfer-flow prototype built from plain `.dc.html` pages.

## Preview

- **Double-click `index.html`.** It opens on the Incoming Transfers landing page (`Inventory Products.dc.html`). No server is needed.
- **Claude Code / Claude desktop:** run the preview named `transfer-prototype` (defined in `.claude/launch.json`). It serves the folder at http://localhost:8765, and `index.html` sends you to the landing page.
- **Local server:** `python3 serve.py`, then open http://localhost:8765 (caching is off, so edits show on reload)

The pages load React from a CDN, so you need an internet connection.

## Editing

After changing any `.dc.html` file, rebuild the component bundle:

```bash
python3 build-bundle.py
```

`_bundle.js` embeds every page so shared components (side nav, top nav, switchers) load without a server. Commit it along with your changes.
