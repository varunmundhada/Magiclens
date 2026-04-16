# Magiclens

**Magiclens** is a browser-based **AR/GPS-enhanced underground pipeline explorer** built with **CesiumJS**. It visualizes underground pipeline segments on a 3D globe, supports GPS location tracking, and includes an AR-style “look around” mode using device orientation (mobile).

## What’s in this repo
- `index.html` — Main **Underground Pipeline Explorer** app (CesiumJS, GPS, AR mode, settings UI).
- `pipeline_explorer.html` — Alternative/extra pipeline explorer page (similar purpose).
- `revelomagiclens1.html` / `revelomagiclens2.html` — Additional Magiclens demo pages/iterations.

## Key Features
- 3D globe visualization with **CesiumJS**
- **Bing Maps** imagery layer
- Pipeline rendering as underground **polyline volumes** (tube-like pipes)
- Click pipelines to view metadata (type, depth, material, diameter)
- **GPS tracking** (shows user position)
- **AR mode** using **device orientation** (requires GPS enabled first)
- Settings panel for:
  - translucency / fade by distance
  - show/hide pipelines
  - underground mode
  - terrain alpha + underground depth sliders
- Mobile-friendly UI (touch optimized + responsive controls)

## How to Run
### Option A: Open directly
You can open `index.html` directly in a browser, but some browsers may restrict network requests depending on security settings.

### Option B (Recommended): Run a local server
From the repo folder:
```bash
python -m http.server 8000
```

Then open:
- `http://localhost:8000/index.html`

## Notes / Requirements
- For **GPS**: allow location permission in your browser.
- For **AR mode**: use a mobile device that supports `DeviceOrientationEvent` and grant motion/orientation permissions (iOS may prompt).
- Pipelines are fetched from configured **WFS (GeoServer)** endpoints inside the HTML (update URLs if needed).
- The Cesium Ion token and Bing Maps key are referenced in the page; for production, move keys to a secure config and do not hardcode them.

## Author
Varun Mundhada
