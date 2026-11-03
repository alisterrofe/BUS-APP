# OPUS interactive 3D furniture viewer

This is a standalone GitHub Pages-ready test build. It does **not** contain the old viewer's original `index.html`, which was not attached.

## Folder structure

```
index.html
models/
  BASE_OPU3BS.obj
  DRAWER_01_OPU3BS.obj
  DRAWER_02_OPU3BS.obj
  DRAWER_03_OPU3BS.obj
```

## Publish to GitHub Pages

1. Create a public GitHub repository (or use an existing repository).
2. Upload `index.html` and the complete `models` folder into the root of the repository. Do not upload just the ZIP as a single file.
3. Under **Settings → Pages**, select **Deploy from a branch**, choose `main` and `/ (root)`, then save.
4. Open the GitHub Pages URL shown in that settings page after deployment.

Do not double-click `index.html` to test locally: browsers commonly block local OBJ loading. Instead use GitHub Pages or a local HTTP server (e.g. `python -m http.server 8000`).

The page loads Three.js modules from jsDelivr, so testing requires an internet connection.

## Controls

- Click a drawer to open / close it.
- Drag a drawer vertically to pull it in or out.
- Drag empty space to orbit the camera.
- Mouse wheel / trackpad to zoom.
- Reset view + drawers returns the furniture to its initial state.
- The model-switching arrows become active when multiple models are configured under the OPUS range in the `ranges` array near the top of the JavaScript.

## Materials

The supplied OBJs reference missing MTL files. This build assigns basic neutral materials so it works without MTL files or textures.

## Drawer direction

These OBJs have their drawer fronts towards positive Z. The code opens along positive Z. If a future export has the opposite orientation, change that model's `openAxis` and/or update its export orientation.
