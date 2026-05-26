# The Cat Petting Game

A continuous, no-goals game about petting cats. Cats wander into a small room one at a time. When one wants attention, a little paw bubble appears above its head. Click the cat to start petting; gently move your mouse over its body until it's happy. After a while an owner reaches in through the door to take a resting cat home, and a new visitor eventually arrives. The room is never empty for long.

By Jiayi Yang · GAME 714 · SCAD

---

## Controls

- **Mouse** — point and click. The pointing-hand cursor turns into a petting-hand when you hover over a cat that wants attention. Click to start petting.
- **Inside the petting popup** — move the mouse gently over the cat's body. Tufts of fur drift up from the cursor as you pet. Move too fast and the cat will get annoyed (its expression and tail change); keep going and it runs away.
- **♪ button** (top-right) — toggle mute. A slash appears through the icon when muted.

No menus, no save state, no end. Close the browser when you're done.

---

## Running locally

You'll need [Node.js](https://nodejs.org/) (version 18 or newer).

```bash
npm install
npm run dev
```

Then open the URL it prints (usually `http://localhost:5173`).

To build a production version:

```bash
npm run build
```

The built site lives in the `dist/` folder.

---

## Deploying to a public URL

### Vercel via GitHub (recommended)

1. Push the project to a GitHub repository
2. Sign up at https://vercel.com (free)
3. Click "Add New" → "Project" → "Continue with GitHub"
4. Authorize Vercel, then select the repo
5. Vercel auto-detects Vite — click "Deploy"
6. You get a public URL like `https://your-game.vercel.app`

Future updates: every push to GitHub triggers a re-deploy.

### Netlify drag-drop

1. Run `npm run build` locally
2. Go to https://app.netlify.com/drop
3. Drag the `dist/` folder onto the page

---

## Project structure

```
visitors-game/
├── public/
│   ├── audio/             # MP3 audio files (served at /audio/*)
│   └── art/               # Hand-painted pixel art (served at /art/*)
│       ├── room_background.png        # 320x240 room backdrop
│       ├── petting_background.png     # 320x240 petting popup backdrop
│       ├── cat1_white.png … cat5_orange.png   # room-view cat sprites
│       ├── cat1_petting/ … cat5_petting/      # per-cat petting popup sprites
│       │   └── catN_{normal,halfhappy,happy,angry1,angry2}.png
│       ├── bubble.png                  # "wants pets" icon above a cat
│       ├── heart.png                   # satisfied-after-petting icon
│       ├── annoyed.png                 # ran-away icon
│       ├── cat_gone.png                # puff of smoke when a cat runs away mid-pet
│       ├── fur1.png, fur2.png, fur3.png   # drifting fur particles
│       ├── cursor_pointinghand.png     # default cursor
│       └── cursor_pettinghand.png      # cursor over a pettable cat / inside popup
├── src/
│   ├── main.jsx           # React entry point
│   └── VisitorsGame.jsx   # The game (all logic here)
├── index.html             # global CSS: pixel-art rendering, custom cursor, fur drift keyframes
├── package.json
└── vite.config.js
```

---

## Credits

- Code & design: Jiayi Yang, with implementation assistance from Claude (Anthropic). See `AI_WORKLOG_Visitors.md` for the full development log.
- Pixel art: hand-drawn by Jiayi Yang (room, all five cats and their petting expressions, petting popup backdrop, fur particles, custom cursors, bubble / heart / annoyed / cat-gone icons).
- Audio: all sound effects and background music sourced from [Pixabay](https://pixabay.com/sound-effects/) under the Pixabay Content License (free for commercial and non-commercial use, no attribution required, but credited here for transparency). Files used: `background_music.mp3`, `cat_purr.mp3`, `cat_meow.mp3`, `cat_hiss.mp3`, `chime.mp3`, `soft_piano.mp3`, `mouse_click.mp3`.
