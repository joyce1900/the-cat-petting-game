# The Cat Petting Game

A continuous, no-goals game about petting cats. Cats wander in and out of a room. When a cat wants attention, a little paw bubble appears above its head. Walk over, pet it gently, and watch for warning signs — if you keep going past them, the cat will hiss and jump away. After a while, an owner reaches in through the door to take one home, and another cat eventually arrives. The room is never empty for long.

By Jiayi Yang · GAME 714 · SCAD

---

## Controls

- **WASD** — walk around the room
- **E** — pet the nearest cat (you must be close enough — a gold ring marks an interactable cat)
- **Mouse** — gently move the cursor over the cat in the popup to pet it
- **♪ button** (top-right) — toggle mute (a red slash appears through the icon when muted)

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
│   └── audio/             # MP3 audio files (served at /audio/*)
├── src/
│   ├── main.jsx           # React entry point
│   └── VisitorsGame.jsx   # The game (all logic here)
├── index.html
├── package.json
└── vite.config.js
```

---

## Credits

- Code & design: Jiayi Yang, with implementation assistance from Claude (Anthropic). See `AI_WORKLOG_Visitors.md` for the full development log.
- Audio: all sound effects and background music sourced from [Pixabay](https://pixabay.com/sound-effects/) under the Pixabay Content License (free for commercial and non-commercial use, no attribution required, but credited here for transparency). Files used: `background_music.mp3`, `cat_purr.mp3`, `cat_meow.mp3`, `cat_hiss.mp3`, `chime.mp3`, `soft_piano.mp3`, `mouse_click.mp3`.
- Pixel art (placeholder): generated programmatically via canvas drawing primitives in `VisitorsGame.jsx`. To be replaced with hand-drawn art assets by Jiayi Yang.
