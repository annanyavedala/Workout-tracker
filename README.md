# Form — Free Personal Workout Tracker

A dependency-free, offline-first PWA for strength, cardio, yoga and bodyweight training. Data is stored on-device using IndexedDB. No accounts, subscriptions, analytics or backend.

## Run locally

Use a static server (opening `index.html` as a file won't support service workers):

```bash
cd form-workout-app
python3 -m http.server 8000
```

Open http://localhost:8000 in your browser.

## Deploy free to iPhone

1. Create a free GitHub account and a repository.
2. Upload the contents of this folder to the repository root.
3. In the repository, open Settings → Pages → Build and deployment → Deploy from a branch. Choose `main` and `/ (root)`.
4. After deployment, open `https://YOUR_USERNAME.github.io/YOUR_REPO/` in Safari on your iPhone.
5. Tap Share → Add to Home Screen → Add (enable Open as Web App if shown).
6. Open it once while online; the service worker caches the app for offline use.

GitHub Pages hosts public repositories for free. Your app's *code* is public, but your workout records are only stored on your device and are not uploaded to GitHub. Never commit exported workout backups to the repository.

## Backup

Settings → Export JSON backup. Save the downloaded JSON to iCloud Drive or Files. Settings → Import backup restores it. Deleting Safari website data or the home-screen app may erase local data.

## Notes

- Default weight unit is pounds. Settings can switch to kilograms, converting recorded weights.
- Strength logs weight and reps; cardio logs distance (km) and minutes; yoga logs minutes and optional count/rounds; bodyweight logs reps and optional duration (minutes).
- The first version includes a searchable exercise catalog, custom exercises, routines, history and basic progress.
- Updates: change files and bump the cache name in `sw.js` (e.g. `form-static-v2`), then reload while online.
- Static hosting needs HTTPS for offline PWA installation; GitHub Pages provides HTTPS.
