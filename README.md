# Nana's Trainer

A personal-trainer web app in a single file. It plans each session (A/B/C rotation, Gym or Home mode), logs what you actually did, and adjusts weights, reps and exercises the way a coach would. It also tracks your progress.

- No account, no internet needed, no install.
- Your data stays in this browser on this device (localStorage).
- **Back up often:** Settings → Export JSON. Use Import JSON to restore or move to a new phone.

## Files

| File | What it is |
|---|---|
| `index.html` | The whole app. This file works on its own. |
| `manifest.webmanifest`, `sw.js`, `icon*.png`, `icon.svg` | Optional extras that make it installable and work offline when hosted online. |
| `screenshot.png` | Preview of the Today screen. |

## Option 1: Just open it (fastest)

1. Double-click `index.html`. It opens in your browser.
2. Bookmark it (Ctrl/Cmd + D) or set it as your home page.

Note: data is saved per browser. If you open the file in Chrome and then in Safari, you get two separate logs. A file on your computer also can't be opened from your phone, so use Option 2 if you train with your phone.

## Option 2: Host it free (recommended for phone use)

### Netlify Drop (about 1 minute, no Git)
1. Go to https://app.netlify.com/drop
2. Drag the whole `trainer-app` folder (or unzip `trainer-app.zip` first) onto the page.
3. You get a link like `https://something.netlify.app`. Make a free account to keep it permanently and rename it.
4. Open the link on your phone and add it to your home screen (below).

### GitHub Pages
1. Create a free account at https://github.com and click **New repository** (e.g. `trainer`), set to Public.
2. Click **Add file → Upload files**, drag in everything from this folder, and click **Commit**.
3. Go to **Settings → Pages**. Under "Branch" pick `main` and `/ (root)`, then click **Save**.
4. After a minute your app is live at `https://YOUR-USERNAME.github.io/trainer/`.

To update later, re-upload `index.html` (and bump `VERSION` in `sw.js` so phones pick up the new copy right away).

## Add to your phone's home screen
- **iPhone (Safari):** open the link → Share button → **Add to Home Screen**.
- **Android (Chrome):** open the link → ⋮ menu → **Install app** / **Add to Home screen**.

It then opens full-screen like a normal app and works offline.

## How it coaches you
- **Today:** suggests the next day in the rotation. Pick Gym or Home, log weight/reps (or seconds/minutes) per set, tap ✓ to start the rest timer, and rate each exercise Easy / Just right / Hard.
- **Progression rules:**
  - Gym lifts:
    - Every set hit and **Easy** → add load (+5 lb upper body, +10 lb lower body; 2.5/5 kg).
    - **Just right** → +1 rep per set. Once reps top out (+2), add load and go back to base reps.
    - **Hard** → hold.
    - Missed reps → hold. Missed and Hard, or missed two sessions in a row → deload 10%.
  - Home exercises:
    - Reps go up first, then you level up to a harder variation (push-up → decline → archer; squat → split squat → Bulgarian → pistol; and so on).
    - Holds add 5–10 s.
    - At the top of a ladder, you add tempo.
  - You can always tap **Keep (old exercise)** to stay on the easier version.
- **Consistency:** two or more missed sessions in a week, or 10+ days off → a lighter "re-entry" session (≈10–15% lighter, one fewer set). After 2 consistent weeks at 3×/week, it offers to move you to 4×/week.
- **Swap:** replace any exercise with one from the same movement pattern, for today or permanently.
- **History:** edit or delete any past session.
- **Progress:** charts per exercise, sessions per week with streak, weekly volume, and body weight.
- **Settings:** lb/kg (converts your data), days per week, rest timer, and plan editor (add, remove or reorder exercises, custom exercises, extra days). You can also Export/Import JSON or export to CSV.
