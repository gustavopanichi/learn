# Learn 1 Thing

A cosy TV that plays short AI videos. Static site, no build step.

## Put it on GitHub Pages
1. Create a new repo and upload everything in this folder (keep the `ui/` folder).
2. Repo → Settings → Pages → Source: "Deploy from a branch", branch `main`, folder `/ (root)`.
3. Open the URL GitHub gives you (takes a minute the first time).

YouTube videos only play when the site is served over http(s). Opening `index.html` straight from your computer won't play them.
To test locally instead: run `npx serve` in this folder and open the address it prints.

## How it works
- Videos always start with sound, never muted. If the browser won't allow sound before the visitor has interacted with the page, the TV shows the video's thumbnail with a pulsing play mark and starts (with sound) at the first click, tap or key press anywhere. Clicking the TV screen also pauses/plays.
- SketchDeck halfpipe in the top-left corner.
- Keyboard: → new video, ← previous, Space pause, M mute.
- The site starts on dog + coffee + night (`state` in `index.html`). Three toggles swap the background loop: cat/dog (by the bed), coffee/tea (by the mug), day/night (by the window). The starting loop loads first; the other 7 download in the background, one at a time. Small screens use the 960×540 copies in `bg/sm/`.
- Microwave-style display on the TV: time left on the current video (blinks while paused).
- Toggles make a deep wooden knock sound (generated in the browser, no audio file).
- TV buttons, left to right: play/pause (shows pause while playing; stays down and shows play while paused), new video / refresh (down while pressed), mute (stays down while muted).
- "How long do you have?" picker (1–5 / 5–10 / 10–15 min) chooses which videos play; changing it switches straight to a video of that length.
- 9-dot button (top right) opens a drawer listing every video by length, with a checkmark on the ones already seen (remembered in the visitor's browser; a video counts as seen after 60s, or half of it if shorter). Clicking one plays it; the YouTube icon opens it on YouTube. The drawer also has the Full screen button.
- Phones fill the whole screen (no side bands), keeping the TV, toggles and duration picker in view; on short screens the logo moves to the top-left corner. On phones the first video starts from a tap on the screen (iPhones require it).
- Phones only run in landscape: held upright, they show a "Turn your phone sideways" screen (and pause the video).
- Font: Instrument Serif, self-hosted in `fonts/` (SIL Open Font License).
- When a video ends, the next one starts. Videos that can't be embedded are skipped.

## Edit
- Backgrounds: `bg/<pet>-<drink>-<time>.mp4` (1920×1080, no audio) plus a 960×540 copy of each in `bg/sm/`.
- Video list: `videos.js` (one entry per video; `id` is the YouTube video ID). Rule: tutorials and explainers only; no product promos or launch videos, except Claude and Figma tutorials.
- How much the player is zoomed to hide YouTube's title/logo strips: `--zoom` in `index.html` (1 = default, matched to the screen height; higher values crop more).
