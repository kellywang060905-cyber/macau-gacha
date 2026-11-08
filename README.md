# 🎴 Macau Gacha — Card Showdown

A single-file card game inspired by Macau's culture — play solo against a built-in computer opponent, or run the **🎬 Demo Mode** that presents the full rules step by step, advancing only when you click **Next ➜** (great for presentations). No build tools, no dependencies — just open it in a browser.

## 🎮 Game Overview

- **Two ways to play**:
  - **vs Computer** — Player 2 is a built-in AI that picks its cards and decides on the Gacha by itself; its hand always stays face-down.
  - **🎬 Demo Mode** — a fully scripted exhibition match (Player A vs Player B) that advances **only when you click "Next ➜"**: each step shows a commentary line explaining the rule being played. It walks through the setup (buy-in, deck, 3-card hands, 5 rounds), then each round's 4 numbered steps — (1) fixed ante → (2) secret play & reveal (incl. the suit tiebreak) → (3) free draw → (4) optional Gacha — then final scoring and the winner-takes-all settlement, ending with the responsible-gaming lesson that discipline (never gacha'ing) beats spending.
- **Buy-in (simulated)**: each player "inserts" **$80 → 800 pts** (1 pt = $0.10). No real money, no withdrawals, no mid-game recharge — it's a classroom simulation of a real-money-style bankroll.
- Each player duels for **5 rounds**, starting with **3 cards**.
- **Deck**: 48 cultural cards in 4 suits (values 1–12): 🔴 Festive Heritage · 🟡 Gastronomy · 🔵 Landmarks · 🟢 Modern Entertainment.
- **Each round (Fixed Limit)**:
  1. **Forced ante** — Rounds 1–2: 100 pts each (pot 200). Rounds 3–5: 200 pts each (pot 400). No raising, no folding.
  2. **Secret play** — both players pick a card face-down and reveal simultaneously.
  3. **Winner takes the pot** — higher value wins; ties go to suit rank (🔴 > 🟡 > 🔵 > 🟢). Played cards are discarded.
  4. **Free draw + Gacha** — everyone draws 1 free card (hand limit 3); then an optional **50 pts ($5) Gacha popup** (1 extra card; a full hand must discard an old card).
- **Bankruptcy**: can't pay a round's ante → you're out, opponent wins immediately. The 800-pt bankroll exactly covers all 5 antes, so only Gacha overspending can break you.
- **Final scoring** (after Round 5): every 100 pts cash = 1 point · 2 same-suit cards = 4 pts · 3 same-suit = 9 pts · never gacha'd all game = **+5 "Rational Spender"** bonus.
- **💰 Winner Takes All**: after scoring, the loser's remaining points are seized by the winner — you walk away with everything or nothing. Tie on score → more remaining points wins; still tied → draw.

In Demo Mode the game never advances on its own: each step ends with a commentary line, and the match only moves on when you click **Next ➜** — like slides, so you can talk through every rule at your own pace during the presentation. Click the **▾** button in the bubble's corner to collapse it out of the way (so the class can watch the cards reveal); click **▸** to expand it again.

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
- The computer opponent uses a simple heuristic: it weighs pot-winning odds against breaking its suit collections, plays aggressively when bankruptcy looms, and mostly skips the Gacha (which loses points on average). Against a sensible human strategy it wins roughly half the time.
- The Gacha machine is the only guaranteed winner: every 50-pt pull is negative-EV for the player, and the points spent disappear from the table — a built-in responsible-gaming lesson.
- All UI text is in English.
