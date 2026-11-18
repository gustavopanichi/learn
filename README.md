# Learn 1 Thing

A cosy TV that plays short AI videos. Static site, no build step.

## Put it on GitHub Pages
1. Create a new repo and upload everything in this folder (keep the `ui/` folder).
2. Repo → Settings → Pages → Source: "Deploy from a branch", branch `main`, folder `/ (root)`.
3. Open the URL GitHub gives you (takes a minute the first time).

YouTube videos only play when the site is served over http(s). Opening `index.html` straight from your computer won't play them.
To test locally instead: run `npx serve` in this folder and open the address it prints.

## How it works
- Videos always start with sound, never muted. If the browser won't allow sound before the visitor has interacted with the page, the TV waits on static and starts (with sound) at the first click, tap or key press anywhere. Clicking the TV screen also pauses/plays.
- Keyboard: → next, ← previous, Space pause, M mute.
- Three toggles swap the background loop: cat/dog (by the bed), coffee/tea (by the mug), day/night (by the window). All 8 loops in `bg/` are downloaded before the site starts, so switching is instant.
- TV buttons: next (down while pressed), play/pause (stays down while paused), mute (stays down while muted).
- "How long do you have?" picker (1–5 / 5–10 / 10–15 min) chooses which videos play; changing it switches straight to a video of that length.
- Fullscreen button top-right. A light moving film grain sits over the whole page (`#grain` in `index.html`; change its `opacity` to tune it).
- Font: Instrument Serif, self-hosted in `fonts/` (SIL Open Font License).
- When a video ends, the next one starts. Videos that can't be embedded are skipped.

## Edit
- Backgrounds: `bg/<pet>-<drink>-<time>.mp4` (1920×1080, no audio).
- Video list: `videos.js` (one entry per video; `id` is the YouTube video ID).
- How much the player is zoomed to hide YouTube's title/logo strips: `--zoom` in `index.html` (1 = default, matched to the screen height; higher values crop more).
