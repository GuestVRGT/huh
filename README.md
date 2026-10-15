# Blockverse — GitHub Pages Edition

A responsive browser game-platform prototype with an original Blockverse identity, a dark game catalog, a local 3D playground, mobile touch controls, gamepad support, player-list UI, emotes, and selectable 3D avatar bundles.

## Publish with GitHub Pages

1. Go to https://github.com/new and create a **Public** repository named `blockverse`.
2. Extract this ZIP on your computer.
3. Upload **all files inside the `BlockverseStarter` folder** to the repository's root. Make sure `index.html`, `.nojekyll`, `README.md`, `male.glb`, and `female.glb` are at the same level. Do not upload only the ZIP file.
4. Click **Commit changes**.
5. Open **Settings → Pages**.
6. Under **Build and deployment**, choose **Deploy from a branch**.
7. Choose branch `main` and folder `/(root)`, then click **Save**.
8. After GitHub publishes, the site will be at `https://YOUR-USERNAME.github.io/blockverse/` (replace `YOUR-USERNAME`).

## Run locally

Three.js, GLTFLoader, and cannon-es are loaded from jsDelivr, so an internet connection is required. From this folder, run:

```bash
python3 -m http.server 8000
```

Then open http://localhost:8000.

## Controls

- **PC:** WASD or arrow keys to move, Space to jump, drag the world to look around. Use the on-screen emote buttons and player-list button.
- **Mobile/tablet:** left virtual joystick to move, JUMP button to jump, drag the world to look, and use the emote/player-list controls.
- **Gamepad:** left stick to move, right stick to look, A / Cross to jump, X / Square to dance toggle, Y / Triangle to toggle the player list. Browser/gamepad mappings can vary by controller and browser.
- **Avatar:** open Avatar & bundles to select Classic, Male bundle, or Female bundle. The two GLB files must remain beside `index.html`.

## Included

- Responsive game catalog with search, genre filters, favorites, and profile settings
- Three.js 3D playground and cannon-es physics
- Desktop keyboard, touchscreen, and browser Gamepad API controls
- Local player-list panel and simple emote actions (wave, dance, cheer, laugh)
- Bundled `male.glb` and `female.glb` 3D avatars, plus a classic block avatar
- Settings placeholders for PlayFab and Photon

## Current limitations

This is still a **local single-player prototype**. The player list displays only the local player; real multiplayer/presence, PlayFab accounts and persistence, Photon Realtime networking, Photon Voice, moderation, and server-authoritative physics are not connected. The supplied avatar GLBs include a `TPose` animation, not a full set of ready-made emote animations; emotes are lightweight procedural poses and should be upgraded with dedicated animation clips for production. Game catalog entries and player counts are sample data. GitHub Pages serves static files only and cannot run the authoritative multiplayer server. Never put private server secrets in browser code.
