# To‑Do + Minuteur (1:08) — Vercel

A single‑file web app (with PWA/offline) that rings every **1:08** and includes a simple To‑Do list stored in `localStorage`.

## Deploy to Vercel (GitHub method)
1. Create a new GitHub repo and upload these files.
2. Go to https://vercel.com/new, import the repo, framework preset **Other**, and deploy.
3. Assign a domain if you want (`Project Settings → Domains`).

## Deploy via Vercel CLI
```bash
npm i -g vercel
vercel login
vercel       # first time (creates the project)
vercel --prod
```

That’s it. This is a static site, no server code required.

## PWA
- Install to your phone from the browser menu. On iOS, first open in Safari, tap **Share → Add to Home Screen**.
- iOS will only play sound after a user gesture: tap **Start** once per session.
- Keep the screen awake for reliable chimes (background tabs may be throttled by the OS).


## Vibration-only mode
- The timer now vibrates continuously at ring time until you press **Start** (restart), **Stop**, or **Reset**.
- On **Android/Chrome**, `navigator.vibrate` is supported.
- On **iOS/Safari**, web vibration is **not supported**; the app will not vibrate. Consider enabling a short sound fallback or using Web Push notifications (Android supports custom vibration on notifications).
