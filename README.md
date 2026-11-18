# Learn 1 Thing

A cosy TV that plays short AI videos. Static site, no build step.

## Put it on GitHub Pages
1. Create a new repo and upload everything in this folder (keep the `ui/` folder).
2. Repo → Settings → Pages → Source: "Deploy from a branch", branch `main`, folder `/ (root)`.
3. Open the URL GitHub gives you (takes a minute the first time).

YouTube videos only play when the site is served over http(s). Opening `index.html` straight from your computer won't play them.
To test locally instead: run `npx serve` in this folder and open the address it prints.

## How it works
- Videos start muted (browsers only allow muted autoplay). Click the TV screen to turn sound on/off.
- Top knob on the TV: next video. Lower knob: previous video. Keyboard: → / ← and M.
- Coffee/tea toggle by the mug swaps the background.
- When a video ends, the next one starts. Videos that can't be embedded are skipped.

## Edit
- Video list: `videos.js` (one entry per video; `id` is the YouTube video ID).
- How much the player is zoomed to hide YouTube's title/logo strips: `--zoom` in `index.html` (1 = no crop, 1.15 default).
