# Macos Portfolio

An interactive, coquette-themed macOS-style desktop portfolio for Vishwajeet: desktop folder icons, a Dock and app windows.

Alloy prototype: https://alloy.app/vishwajeet-srk/p/34b077d8-5b1b-4dc3-abf3-6a5d9fe60c62

## Project structure

```
site/
  index.html          # entry page
  index-*.js          # built app bundle (React)
  index-*.css         # styles
  landscape.html      # background placeholder
docker-compose.alloy.yaml
.alloy/environment.json
```

`site/` holds a **pre-built static site**, so there's no `npm install` or build step. Any static file server can serve it.

## Run locally

Start the server from the repo root with one of the options below, then open **http://localhost:3000**.

### Option 1: Python (no install on most machines)

```bash
cd site
python3 -m http.server 3000
```

On Windows use `python -m http.server 3000`.

### Option 2: Node.js

```bash
npx serve site -l 3000
```

### Option 3: Docker

```bash
docker compose -f docker-compose.alloy.yaml up
```

The compose file uses `network_mode: host`. On Docker Desktop (macOS or Windows), host networking needs to be enabled in Docker Desktop's settings. If it isn't, use Option 1 or 2.

> Don't open `site/index.html` by double-clicking it. The app is an ES module, and browsers block those over `file://`. Serve it over HTTP as shown above.

## Deploy

Upload the `site/` folder to any static host (Vercel, Netlify, GitHub Pages). With Vercel, set the output/root directory to `site` and leave the build command empty.

## Notes

- Images and project links load from external URLs, so the page needs internet access to display them.
- To edit the design, change it in the Alloy prototype and export the files again. The bundle in `site/` is compiled output, not the original source.
