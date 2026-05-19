# The Cat Petting Game

A continuous, no-goals game about petting cats. Cats arrive at the room from time to time. You walk over to one and pet it. After a while, an owner comes and takes one home. Another one shows up later.

By Jiayi Yang · GAME 714 · SCAD

---

## Controls

- **WASD** — walk around the room
- **E** — pet the nearest cat (you have to be close — a gold ring appears around interactable cats)
- **Mouse** — gently move over the cat in the popup to pet it
- **ESC** or the **×** button — close the petting popup
- **♪ button** (top-right) — open audio settings (mute, music volume, effects volume)

The game has no goal, no score, no save state. Close the browser when you're done.

---

## How to run locally

You'll need [Node.js](https://nodejs.org/) installed (version 18 or newer).

```bash
npm install
npm run dev
```

Then open the URL it prints (usually `http://localhost:5173`).

To build a production version:

```bash
npm run build
```

The built site will be in the `dist/` folder.

---

## How to deploy to a public URL

### Option 1: Vercel via GitHub (recommended)

1. Push the project to a GitHub repository
2. Sign up at https://vercel.com (free)
3. Click "Add New" → "Project" → "Continue with GitHub"
4. Authorize Vercel, then select the repo
5. Vercel auto-detects Vite — just click "Deploy"
6. You get a public URL like `https://your-game.vercel.app`

Future updates: every push to GitHub triggers a re-deploy.

### Option 2: Netlify drag-drop

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

- Code & design: Jiayi Yang, with assistance from Claude (Anthropic)
- Audio: Pixabay
