# Blockverse — GitHub Pages Edition

A responsive browser game-platform prototype with an original Blockverse identity, a dark game catalog, multiple distinct 3D playground maps, mobile touch controls, gamepad support, player-list UI, skeletal locomotion/emotes, and selectable 3D avatar bundles.

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

## Service configuration

The site has your service IDs preconfigured in `index.html`. PlayFab's official browser client SDK is loaded from Microsoft's PlayFab CDN and the site attempts `LoginWithCustomID` using a browser-persisted random custom ID, then updates the PlayFab display name when you save it. The first successful login creates a PlayFab player account. This is anonymous browser identity, not a secure email/password account. Clearing browser storage can create a different player identity.

Configured IDs:
- PlayFab Title ID: `164E0A`
- Photon Realtime App ID: `45b1dd1e-3c30-4f22-99b3-9f169625e7c9`
- Photon Voice App ID: `2d967d73-dddf-4c97-a5f1-954f1eef05d6`

**Photon is configured but not yet connected.** Photon’s official JavaScript SDK is distributed separately from the App ID; the SDK files must be added to the project before realtime rooms, player movement synchronization, and voice can work. This project does not pretend that IDs alone enable those features. Use the official [Photon SDK downloads](https://www.photonengine.com/sdks) and [JavaScript API docs](https://doc-api.photonengine.com/en/javascript/current/index.html).

## Included

- Responsive game catalog with search, genre filters, favorites, and profile settings
- Three.js 3D playground and cannon-es physics
- Desktop keyboard, touchscreen, and browser Gamepad API controls
- Local player-list panel and simple emote actions (wave, dance, cheer, laugh)
- Bundled `male.glb` and `female.glb` 3D avatars, plus a classic block avatar
- Built-in PlayFab anonymous login and display-name update; preconfigured Photon Realtime and Voice app IDs

## Current limitations

This is still a **local single-player prototype**. The maps now have distinct layouts and environments, and the bundled GLB armature bones are procedurally animated for walking and emotes. These changes do not add online networking by themselves. The player list displays only the local player; real multiplayer/presence, Photon Realtime networking, Photon Voice, moderation, and server-authoritative physics are not connected. PlayFab anonymous login is implemented but should be tested in your title before release. The supplied avatar GLBs include a `TPose` animation, not a full set of ready-made emote animations; emotes are lightweight procedural poses and should be upgraded with dedicated animation clips for production. Game catalog entries and player counts are sample data. GitHub Pages serves static files only and cannot run the authoritative multiplayer server. Never put private server secrets in browser code.
