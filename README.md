# Stackdown — Playtest Build

A fast, competitive twist on Solitaire. Everyone plays at once; all aces go to one shared **community pot** that builds up by suit (A→K). Race to drop the most cards before the buzzer. (Based on the classic card game Nertz / Pounce.)

**This build is a single-player "feel test" vs. adaptive bots** — it's for gathering feedback on the core gameplay. Real-time human-vs-human multiplayer needs a backend and is a later phase.

## Play it

It's one self-contained file, `index.html` — no build step, no dependencies. Open it in any modern browser, or host it (see below) and share the link.

## How to play

- **Tap** a card to send it to the pot (when it fits there).
- **Drag** a card to place it exactly where you want — the pot or a work pile. Valid spots light up while you drag.
- **Tap the Stock** to flip a fresh card.
- Build your **work piles** down in alternating colours (red 7 on black 8) to free buried cards.
- Empty your **Reserve** pile for +10; every card left at the buzzer is −2.
- Scoring: +1 per card to the pot, +5 Crown (play a King), +1 combo while you're hot, +10 reserve clear, −2 per leftover reserve card.

There's a 30-second guided tutorial on the start screen, and a **?** button for the rules anytime.

## Feedback

A **💬** button (top bar) and a **Feedback** button (results screen) open a quick panel. Responses are emailed to the project owner. To change the destination, edit this line near the top of the `<script>` in `index.html`:

```js
const FEEDBACK_URL = "mailto:jakeschirm@gmail.com";
```

(Set it to a Google Form / Typeform URL instead, or `""` to copy feedback to the clipboard.)

## Hosting on GitHub Pages

After pushing this repo to GitHub:

1. Go to the repo's **Settings → Pages**.
2. Under **Build and deployment → Source**, choose **Deploy from a branch**.
3. Pick branch **main** and folder **/ (root)**, then **Save**.
4. After a minute, your game is live at `https://<your-username>.github.io/<repo-name>/`.

Share that link with testers — it works on phones and desktops.

## Roadmap (not in this build)

Real-time multiplayer, accounts, daily-game scarcity, persistent groups/favorites, leaderboards, the shareable results card, and monetization are all later phases that build on this validated core.
