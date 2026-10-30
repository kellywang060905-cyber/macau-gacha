# 🎴 Macau Gacha — Two-Player Showdown

A single-file card game inspired by Macau's culture — play hot-seat two-player, or solo against a built-in computer opponent. No build tools, no dependencies — just open it in a browser.

## 🎮 Game Overview

- **Two ways to play**: hot-seat **2 players**, or **single-player vs the computer** (Player 2 is a built-in AI that picks its cards and decides on the Gacha by itself; its hand always stays face-down).
- Each player duels for **5 rounds**, starting with **3 cards** and **$3,000**.
- **Deck**: 48 cultural cards in 4 suits (values 1–12): 🔴 Festive Heritage · 🟡 Gastronomy · 🔵 Landmarks · 🟢 Modern Entertainment.
- **Each round**: both players ante **$200**, secretly play a card face-down, then reveal simultaneously. Higher value wins the **$400 pot**; ties are decided by suit rank (Red > Yellow > Blue > Green). Then everyone draws 1 free card, followed by an optional **$500 Gacha popup** (extra card, but a full hand requires discarding 1 old card).
- **Bankruptcy**: can't pay the $200 ante → you're out, opponent wins immediately.
- **Final scoring**: every $100 cash = 1 point · 2 same-suit cards = 4 pts · 3 same-suit = 9 pts · never gacha'd all game = **+5 "Rational Spender"** bonus. Highest total wins.

In two-player mode, pass the device between turns so nobody peeks! 🤝

## ▶️ Play locally

Double-click `index.html` (or open it in any modern browser). Works on desktop and mobile.

## 🚀 Deploy to GitHub Pages

### Option A — Upload via the GitHub website (easiest)

1. Create a new repository at [github.com/new](https://github.com/new) (e.g. `macau-gacha`).
2. On the repo page, click **Add file → Upload files** and drag in `index.html`.
3. Commit the upload.
4. Go to **Settings → Pages**.
5. Under *Build and deployment*, set **Source** to **Deploy from a branch**, select the `main` branch and the `/ (root)` folder, then click **Save**.
6. After a minute or two, your game is live at:
   `https://<your-username>.github.io/<repo-name>/`

### Option B — Git CLI

```bash
# inside this folder (macau-gacha/)
git init
git add index.html README.md
git commit -m "Add Macau Gacha game"
git branch -M main
git remote add origin https://github.com/<your-username>/<repo-name>.git
git push -u origin main
```

Then enable Pages as in step 4–5 above.

## 🛠️ Notes

- Single self-contained HTML file — no external assets required (sound effects are generated with the Web Audio API; the only network request is an optional Google Font).
- The computer opponent uses a simple heuristic: it weighs pot-winning odds against breaking its suit collections, plays aggressively when bankruptcy looms, and mostly skips the Gacha (which loses points on average).
- All UI text is in English.
