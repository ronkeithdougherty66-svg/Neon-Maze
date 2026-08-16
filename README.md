# Neon Maze

A neon maze-chase arcade game built as an installable web app (PWA). Gather
every dot, dodge the three roaming Sprites, grab power pellets to turn the
hunt around, and try to beat your saved high score.

**Features**
- Normal mode (Sprites chase you) and Practice mode (maze only, no chasers)
- High score saved on your device between sessions, with a celebration
  banner + sound the moment you beat it
- Pause and End Run controls
- Sound toggle (all effects are synthesized — no audio files to load)
- Touch swipe / on-screen d-pad controls, plus arrow keys / WASD on desktop
- Installable to your phone's home screen and playable offline

## Hosting it on GitHub Pages

1. Create a new GitHub repository (e.g. `neon-maze`).
2. Upload every file in this folder, **keeping the same structure**:
   ```
   index.html
   manifest.json
   service-worker.js
   icons/
     icon-192.png
     icon-512.png
     icon-maskable-512.png
     apple-touch-icon.png
     favicon-64.png
   README.md
   ```
   Easiest way: on the repo's GitHub page, click **Add file → Upload
   files**, drag the whole folder in, and commit.
3. Go to the repo's **Settings → Pages**.
4. Under **Build and deployment → Source**, choose **Deploy from a
   branch**, pick the `main` branch and the `/ (root)` folder, then
   **Save**.
5. GitHub will give you a URL that looks like:
   `https://YOUR-USERNAME.github.io/neon-maze/`
   It can take a minute or two to go live after the first deploy.

## Installing it on your Android phone

1. Open the GitHub Pages URL above in **Chrome** on your phone.
2. Tap the **⋮** menu in the top right.
3. Tap **Add to Home screen** (Chrome may also show this automatically
   as an **Install app** banner or prompt).
4. Confirm — you'll get a Neon Maze icon on your home screen that opens
   full-screen, just like a regular app.

Because of the service worker, once you've opened it at least once with
a connection, it'll keep working even with no signal.

## Updating it later

If you come back to tweak the game, edit `index.html` and change the
`CACHE_NAME` value at the top of `service-worker.js` (e.g. `neon-maze-v2`)
so returning players get the new version instead of a cached old one.
Re-upload the changed files to the same GitHub repo and Pages will
redeploy automatically.

## Notes

- No backend, accounts, or analytics — the high score lives only in your
  phone's browser storage for this site. Clearing site data/cache will
  reset it.
- All art and sound are generated in code (canvas + Web Audio), so there
  are no external assets to keep track of.
