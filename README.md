# Strict Fitness

A no-frills, no-signup fitness timer and workout planner that runs entirely in your browser. Build workouts, run them with a full interval timer, plan them out on a calendar, and even let AI build one for you — all with your data stored privately on your own device.

**[Open the app](#)** *(replace with your GitHub Pages link)*

---

## What it does

**Workout types.** Build workouts in 9 different formats:
- **Tabata** — fixed work/rest intervals across many rounds
- **HIIT** — a list of exercises, each with its own work/rest, repeated for N rounds
- **Circuit** — station to station, with a rest after each full round
- **Timed** — a straight list of timed steps, no repeats
- **EMOM** — a new interval every minute, cycling through your exercise list
- **AMRAP** — as many rounds as possible in a time cap, with a manual round counter
- **Warmup** — same as Timed, kept in its own category
- **Hyrox** — the official race format (8× 1km runs alternating with 8 fixed stations), auto-filled with real event distances and weights
- **Weightlifting** — reps, sets, rest, and weight per exercise, with a "Complete Set" button instead of a running clock

**Workout Player.** A full-screen timer with a circular countdown ring, pause/skip/previous controls, audio cues, and automatic history logging when you finish.

**Workout Program.** A calendar where you assign saved workouts to specific days. A "Today's Workout Program" view shows whatever's scheduled for today, with the option to start everything back-to-back with an automatic rest transition between each.

**AI-generated workouts.** Connect your own Anthropic API key and describe what you want ("a high-intensity chest workout") — or leave it blank and let it look at your recent history and suggest something. Nothing is sent anywhere without your own key.

**Exercise library.** A searchable, alphabetized list of exercises with one-sentence descriptions, editable at any time. New exercise names you type while building a workout are added automatically.

**History & stats.** Every completed workout is logged with duration, date, and body parts. The Home screen shows a weekly workout count and current streak.

**Light & dark mode**, a bottom tab bar, and a design built around one consistent gradient accent throughout.

---

## Tech stack

Nothing to install, nothing to build. It's a single HTML file — plain HTML, CSS, and JavaScript, no frameworks, no bundler, no dependencies. Open it in any modern browser and it works.

## Data & privacy

Everything is stored locally in your browser via `localStorage` — workouts, history, your schedule, your exercise library, and your settings. Nothing is sent to a server, ever, except:
- If you connect an AI provider, your prompt and a summary of your workout history are sent directly to Anthropic's API using your own key.

Clearing your browser's site data will erase everything, so export your workouts (Settings → Download File) periodically if you want a backup.

## Running it locally

Since it's a single static file, there's no build step:

1. Clone this repo
2. Open `index.html` directly in a browser, **or**
3. Serve the folder with any static file server (e.g. `python3 -m http.server`) if you want it running at `localhost`

## Hosting on GitHub Pages

1. Push this repo to GitHub
2. Go to **Settings → Pages**
3. Set the source to the branch containing `index.html` (usually `main`, root folder)
4. Your app will be live at `https://<username>.github.io/<repo-name>/`

## Browser support

Built for modern mobile Safari and Chrome. Uses a few modern browser APIs:
- `localStorage` for all data persistence
- `navigator.wakeLock` to keep the screen on during a workout (falls back gracefully if unsupported)
- Pointer Events for exercise drag-reordering
- `fetch` for the optional AI integration

## Project structure

```
├── index.html          # the entire app — HTML, CSS, and JS in one file
└── README.md
```

## Contributing / customizing

Since everything lives in one file, the easiest way to explore or modify it is to open `index.html` in a code editor and use its section comments (e.g. `/* ===== BUILDER ===== */`) to navigate. See the accompanying code guide for a full function-by-function walkthrough if you're new to the codebase.

## License

This project is licensed under the MIT License — see the [LICENSE](LICENSE) file for details. In short: you're free to use, copy, modify, and distribute this code, for personal or commercial purposes, as long as the original copyright notice is included.
