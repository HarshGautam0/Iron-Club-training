# 🏋️ The Iron Club Training Log

A workout tracker for your phone, styled like a vintage athletic club: leather, brass dials, rolling odometer counters and an analog stopwatch. It counts your reps for you, runs whole routines hands-free, speaks to you like a coach and installs like a real app.

Everything runs in the browser. There is no server, no account and no build step.

## Features

**Train**
- More than 50 exercises in five groups: **Legs**, **Arms**, **Core**, **Cardio** and **Stretch** (arms include push-ups, diamond push-ups, tricep dips, backpack curls and backpack rows).
- **Rep exercises** have a target and an **Auto** mode that counts up by itself at a Slow (3.0 s), Normal (2.0 s) or Fast (1.2 s) pace, with a tick on each rep. You can also tap the big red button to count manually.
- **Timed exercises** (plank, wall sit, stretches and so on) have a target in seconds. The analog stopwatch stops itself and beeps when time is up.

- **Exercise demos:** tap the 🎬 icon next to any exercise name for a looping stick-figure animation and a one-line form tip. The small red **YouTube** icon next to it opens a search for real videos of that exercise (needs internet).

**Routines**
- **Routine cards:** the Routine tab is a stack of cards. The first is your **Daily routine**: pick exercises from Strength, Core, Cardio or Stretch with **＋ Add exercise** and they appear inside that card. Below it, **📦 Add preset** adds ready-made workouts (Quick warm-up, Leg day, Knee stability and more) as their own cards. **Tap any card to start that workout.** Each card has **✎ Edit** (rounds, rests, reorder, remove exercises) and **🗑 Delete** (two taps; on the Daily routine it clears the exercises). A finished card is outlined green with a ✔. You can say "start leg day", "start daily routine" or "start routine" (the first one you haven't done today).
- Build a routine once with **＋ Add exercise**, set each exercise's target, then press **Start routine** and everything plays in order.
- Starts with an 8-second "Get ready", then adds a rest between exercises (0–120 s, you choose).
- **Rounds:** choose how many rounds (1-20) and the rest between rounds. The routine then repeats in order, round after round, with the coach announcing each one. You can also say "start routine with 3 rounds".
- Pause, skip or stop at any time. Skipping or stopping saves whatever you finished.
- Reorder with ↑ ↓ or remove with ×.
- **Presets** add a whole routine in one tap: Quick warm-up, Knee stability, Arms & abs, Legs & glutes, Fat-burn finisher, Leg day, Upper body, Core crusher, Cardio blast and Cool-down. They stack, so you can chain warm-up, workout and cool-down.
- Your workouts are remembered between visits.

**Voice coach and commands**
- 🔊 The coach counts reps aloud and announces each exercise, rests and "routine complete".
- ⏱ On every timer the coach counts down the last five seconds aloud (5, 4, 3, 2, 1): timed exercises, the routine's timed exercises and rests, and the "Get ready" countdown. It stays silent while paused or when the coach is muted.
- 🎤 Hands-free commands (see below).

**Dials, goals and history**
- Three analog dials: **Reps**, **Active minutes** and **Burn** (estimated calories).
- **Goals set themselves.** Nothing to type. See [How the goals work](#how-the-goals-work).
- A bar chart of reps for the current week (Monday to Sunday), plus your streak and active time for the week.
- The **Log** is a ledger page for today. It shows your 4 latest entries by default, with a **▾ Show all** button to expand the full scrolling list. Use the **◀ ▶** arrows to look back at the exercises you did on earlier days (up to 60 days). Doing the same exercise again updates its existing entry instead of adding a duplicate, for example "Push-ups, 35 reps (2×)".

**Themes**
- The 🎨 button in the header switches between **Walnut** (dark wood), **Oak** (light wood) and **Midnight**. It also changes the colour of your phone's status bar, so the clock and battery icons stay readable. Your choice is remembered, and you can say "change theme".

**Installable**
- Works as a Progressive Web App: add it to your home screen, open it full screen and use it offline after the first visit.

## Voice commands

Tap 🎤 once and it keeps listening. Tap again to stop.

| Say | What happens |
|---|---|
| "start 20 push-ups" | Opens the exercise, sets the target and starts counting |
| "start plank" / "do 45 plank" | Starts the stopwatch with that target |
| "start routine" | Starts your routine |
| "pause" / "resume" | Pauses or resumes the current exercise or routine |
| "skip" / "next" | Skips to the next step in a routine |
| "stop" / "finish" | Stops and saves what you've done |
| "log" / "save" | Logs the current set |
| "go to log" (or train, routine, dials) | Switches page |
| "mute" / "unmute" | Turns the spoken coach off or on |

The 🔊 button toggles spoken coaching. Voice commands need a browser with speech recognition (Chrome, Edge or Safari) and microphone permission. The app ignores the mic while it is speaking, so it won't answer itself.

## How the goals work

You never enter a goal. They adapt to you:

- **Starting goals:** 250 reps, 20 active minutes and 200 kcal.
- **After a few days:** each goal becomes about 15% above your average over your last 14 active days. It never drops below 60% of the starting goal.
- **Level up:** when you beat a goal, it steps up by about 40% mid-day and a **▲** appears beside the number, so the needle never gets stuck at the end of the dial.
- **Active minutes** count timed work plus rep exercises at about 3 seconds per rep.

## How calories are estimated

`calories = MET × body weight (kg) × hours`

Each exercise has a standard effort value (MET): stretching is low, jump rope and sprints are high. Rep exercises assume about 3 seconds per rep. Set your body weight on the Dials page (default 70 kg). Treat the numbers as a rough guide, probably within 20–30%, not an exact count.

## Deploy to GitHub Pages

1. Create a **public** repository on GitHub.
2. Push these files so that `index.html` is at the top level of the repo:

   ```bash
   git init
   git add .
   git commit -m "Iron Club training log"
   git branch -M main
   git remote add origin https://github.com/YOUR-USERNAME/iron-club.git
   git push -u origin main
   ```

3. In the repo go to **Settings → Pages**, set Source to **Deploy from a branch**, choose `main` and `/ (root)`, and save.
4. After a minute or two your app is live at `https://YOUR-USERNAME.github.io/iron-club/`.

Any static host works the same way (Netlify, Cloudflare Pages, Vercel). It must be served over **https** for install, voice and offline to work.

## Install on your phone

- **Android (Chrome):** open your site, then menu → **Install app** (or **Add to Home screen**).
- **iPhone (Safari):** open your site, then Share → **Add to Home Screen**.

## Updating the app

After you change `index.html`, bump the cache version in `sw.js` (for example `iron-club-v1` → `iron-club-v2`) and push. Without that, phones keep serving the old cached copy.


## Updating without losing your history

Your history (each day's exercises, the weekly chart, streak, active time, workout cards and settings) is saved in your browser for your site's address. Updating the files on the same GitHub Pages address does **not** touch it. It is only lost if you clear the site's data in your browser, open the app from a different address (for example the preview link instead of your GitHub link) or use a different browser or phone, since each keeps its own copy. Always keep using the same GitHub Pages link.

## Customising

Everything is in `index.html`:

- **Exercises:** the `X('group', 'rep' | 'time', [...])` lines list each exercise as `[id, name, emoji]`.
- **Presets:** the `PRE` array holds the preset routines as `[exerciseId, target]` pairs.
- **Effort values:** `MET_G` (per group) and `MET_X` (per exercise) control the calorie estimate.
- **Starting goals:** the `def` values inside the `goal()` function.

## Project structure

```
index.html            the whole app (HTML, CSS and JavaScript)
manifest.webmanifest  install settings (name, icons, colours)
sw.js                 service worker for offline use
icon-192.png          app icon
icon-512.png          app icon
README.md             this file
```

## Your data

Everything is stored in your browser's local storage on your own device (each day's exercise list, daily totals for the chart and goals, your routine, body weight and voice setting). Nothing is sent anywhere. Because it is stored locally:

- Each phone or browser keeps its own separate history.
- Clearing the site's data erases your history.

## Known limitations

- Calories are an estimate, as described above.
- Rep counting is by timer or by tapping. It does not detect movement.
- Voice recognition depends on your browser and microphone permission.
- Running and GPS tracking are not included on purpose. A browser page can't track a run reliably with the screen off, so a dedicated running app does that job better.

## License

No license has been chosen yet. Add a `LICENSE` file if you want others to be able to reuse the code.
