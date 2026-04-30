# KnowPlan 📅

A shared weekly availability calendar. See who's around — morning or afternoon — no login needed.

## Features

- 📅 **Weekly grid** — Mon–Fri × Morning/Afternoon
- 👤 **Name-based** — just type your name and tap slots
- 🌐 **Real-time** — all changes sync instantly across devices
- ✕ **Anyone can remove** anyone (no auth, open trust model)
- 📱 **PWA** — installable to home screen (iOS & Android)
- 🧭 **Week navigation** — browse past and future weeks

## Firebase Setup

1. Go to [https://console.firebase.google.com](https://console.firebase.google.com)
2. Create a new project (e.g. `knowplan`)
3. Add a **Web app** to the project
4. Copy the Firebase config and paste it into `docs/index.html` (look for `REPLACE_ME`)
5. Go to **Firestore Database** → Create database → Start in **test mode**
6. Done — deploy `docs/` to GitHub Pages or any static host

## Deploy (GitHub Pages)

```bash
git init && git add . && git commit -m "Initial knowplan"
gh repo create knowplan --public --push --source=.
# Enable GitHub Pages → source: /docs branch
```

Live at: `https://<you>.github.io/knowplan/`

## Data Model

Firestore collection `weeks`, one document per week (e.g. `2026-W18`):

```json
{
  "d1_morning":   ["Alice", "Bob"],
  "d1_afternoon": ["Alice"],
  "d2_morning":   ["Charlie"],
  ...
}
```
