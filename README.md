# Buff

A lifting app that tells you what to do each day, remembers your weights, and loads plates onto a barbell as you level up. It is one HTML file with no build step and no server.

## What it does

- **Monday to Sunday plan.** Six training days and a Sunday rest day, about 30 minutes each. Swap any day in if your week changes.
- **Bulk or cut.** Answer three questions and Buff picks one. It changes your rep ranges, rest times and daily walk.
- **Tells you the weight.** Each exercise shows a target based on last time, and goes up 5 lb when you hit the top of the rep range on every set.
- **XP and levels.** Sets, sessions, daily habits and new best lifts all earn XP. Every level adds a pair of plates to the bar for good.
- **Lazy mode.** "I don't feel like it" cuts the session to 3 moves and about 12 minutes, and your streak still counts.
- **App tour.** A short guided walk through every part of the app on first open. Replay it from Profile.
- **Memory.** Buff remembers your goal, your weights, notes on each exercise (like seat height) and reminders you give it (like "go easy on lunges"), and shows them when you train. Profile, then "What Buff remembers", lets you see and forget any of it. If you close the app mid-workout, it reopens where you left off.
- **Moves library.** All 25 exercises with a moving diagram, the muscles worked and one form tip.
- **Works offline** and can be added to your phone's home screen like an app.

## Put it on GitHub Pages

1. Create a new repository on GitHub and upload every file in this folder (keep the `icons` folder and the `.nojekyll` file).
2. In the repository, open **Settings**, then **Pages**.
3. Under **Build and deployment**, set **Source** to "Deploy from a branch", pick the `main` branch and the `/ (root)` folder, and save.
4. After a minute the app is live at `https://YOUR-USERNAME.github.io/REPO-NAME/`.

To install it on a phone, open that address in the browser and choose **Add to Home Screen**.

## Run it on your computer

Open `index.html` in a browser. For the offline and install features, serve the folder instead:

```
python3 -m http.server 8000
```

Then open `http://localhost:8000`.

## Where your data lives

Everything is saved in your browser on your device (`localStorage`). Nothing is sent anywhere. That also means:

- Each browser and each device has its own data.
- Clearing your browser data erases it.
- **Profile, then Backup** downloads a backup file and restores from one. Use it before switching phones.

## Files

| File | What it is |
|---|---|
| `index.html` | The whole app: layout, styles and code |
| `manifest.webmanifest` | Name, colors and icons for the home screen |
| `sw.js` | Offline support |
| `icons/` | App icons |
| `.nojekyll` | Tells GitHub Pages to serve the files as they are |

## Changing things

Everything is in `index.html`.

- **Exercises and days:** the `PLAN` list near the top of the script. Each exercise needs a matching entry in `GUIDE` for its diagram and tip.
- **Colors:** the `:root` block at the top of the styles (light theme), with the dark theme right below it.
- **Daily quotes:** the `QUOTES` list.
- **XP amounts:** search for `award(`.

After changing `index.html`, bump `VERSION` in `sw.js` (for example to `buff-v2`) so installed copies pick up the update.

## Good to know

- Weights are in pounds.
- The app sets how you train, not what you eat. It does not count calories or track body weight.
- It is a training log, not medical advice. If something hurts, stop.
