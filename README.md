# Learn 1 Thing

A cosy TV that plays short AI videos. Static site, no build step.

## Put it on GitHub Pages
1. Create a new repo and upload everything in this folder (keep the `ui/` folder).
2. Repo → Settings → Pages → Source: "Deploy from a branch", branch `main`, folder `/ (root)`.
3. Open the URL GitHub gives you (takes a minute the first time).

YouTube videos only play when the site is served over http(s). Opening `index.html` straight from your computer won't play them.
To test locally instead: run `npx serve` in this folder and open the address it prints.

## How it works
- Videos start with sound. If the browser blocks that on a first visit, the video plays muted and sound comes on at the first click, tap or key press. Click the TV screen to pause/play.
- Keyboard: → next, ← previous, Space pause, M mute.
- Three toggles swap the background loop: cat/dog (by the bed), coffee/tea (by the mug), day/night (by the lamp). All loops in `bg/` are downloaded before the site starts, so switching is instant.
- The big orange button on the TV: next video.
- When a video ends, the next one starts. Videos that can't be embedded are skipped.

## Edit
- Backgrounds: `bg/<pet>-<drink>-<time>.mp4` (1920×1080, no audio). `cat-tea-night` is missing for now and falls back to `cat-coffee-night` (see `FALLBACK` in `index.html`).
- Video list: `videos.js` (one entry per video; `id` is the YouTube video ID).
- How much the player is zoomed to hide YouTube's title/logo strips: `--zoom` in `index.html` (1 = default, matched to the screen height; higher values crop more).
