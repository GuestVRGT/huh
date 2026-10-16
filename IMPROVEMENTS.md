# huh improvements (clothing + multiplayer)

## Clothing fit
`applyAvatarTint` now maps:
- **Shirt** → torso + arms (+ body)
- **Pants** → legs
- **Head** → skin tone

Catalog equip colors:
- `shirt-violet` `#6b3fa0`
- `shirt-lime` `#8dbb3c`
- `pants-dark` `#2a2a38`
- `pants-violet` `#5a3a80`

## Photon multiplayer
On join game, connects Realtime App ID from `SERVICES.photonRealtimeAppId`, joins/creates room, raises event `10` with pose `{p:[x,y,z], y:yaw}`.

## Apply the full patch
Replace `index.html` with the file from the Grok session artifact `huh_index_patched.html`:

```bash
cp huh_index_patched.html index.html
git add index.html
git commit -m "Apply clothing + Photon multiplayer patch"
git push
```

Or download from the chat attachment and upload via GitHub web UI.
