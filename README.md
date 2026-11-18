# Learn 1 Thing

A cosy TV that plays short AI videos. Static site, no build step, deployed on Vercel from `main`.

Live: https://learn-ruby-eight.vercel.app/

## How it works
- Videos start with sound. If the browser blocks that on a first visit, the video plays muted and sound comes on at the first click, tap or key press. Click the TV screen to pause/play.
- Top knob on the TV: next video. Lower knob: previous video. Keyboard: → / ←, Space to pause, M to mute.
- Coffee/tea toggle by the mug swaps the background.
- When a video ends, the next one starts. Videos that can't be embedded are skipped.

YouTube videos only play when the site is served over http(s). Opening `index.html` straight from your computer won't play them.
To test locally: run `npx serve` in this folder and open the address it prints.

## Edit
- Video list: `videos.js` (one entry per video; `id` is the YouTube video ID).
- Player crop: `--zoom` in `index.html` (1 = matched to the screen height; higher values crop more).
