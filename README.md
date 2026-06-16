# Stackdown — Playtest Build

A fast, competitive twist on Solitaire. Everyone plays at once; all aces go to one shared **community pot** that builds up by suit (A→K). Race to drop the most cards before the buzzer. (Based on the classic card game Nertz / Pounce.)

**This build is a single-player "feel test" vs. adaptive bots** — it's for gathering feedback on the core gameplay. Real-time human-vs-human multiplayer needs a backend and is a later phase.

## Play it

It's one self-contained file, `index.html` — no build step, no dependencies. Open it in any modern browser, or host it (see below) and share the link.

## How to play

**Goal: get more cards into the shared pot than the bots before the buzzer. Most cards wins.**

- **Tap** a card to auto-play it — to the pot if it fits, otherwise onto a work pile. If it fits more than one spot, those spots light up so you can **drag** it where you want.
- **Drag** a card to place it exactly where you want — the pot or a work pile. Valid spots light up while you drag.
- An **empty pile is wild** — you can move any card onto it.
- **Tap the deck** to flip a fresh card into your waste.
- Build your **work piles** down in alternating colours (red 7 on black 8) to free buried cards.

First launch drops you straight into a guided match with a couple of in-context tips (no setup screen). A **?** button shows the rules anytime, and **Options** on the start screen tweaks match length / bot pressure. At the buzzer, **📲 Share my result** opens your phone's share sheet (Messages, etc.) with a quick brag card and a link back to the game.

## Feedback

A **💬** button (top bar) and a **Feedback** button (results screen) open a quick panel. Responses are emailed to the project owner. To change the destination, edit this line near the top of the `<script>` in `index.html`:

```js
const FEEDBACK_URL = "mailto:jakeschirm@gmail.com";
```

(Set it to a Google Form / Typeform URL instead, or `""` to copy feedback to the clipboard.)

## Analytics (how players engage)

Optional product analytics via [PostHog](https://posthog.com) (free tier). Make a free project, copy the **Project API key** (starts with `phc_`), and paste it near the top of the `<script>` in `index.html`:

```js
const POSTHOG_KEY  = "phc_xxx";                 // "" disables analytics
const POSTHOG_HOST = "https://us.i.posthog.com"; // or eu
```

Events captured: `app_open`, `match_start`, `first_pot_play` (time-to-first-play), `coach_start/complete/skip`, `hint_used`, `rules_opened`, `match_end` (pot count, placement, won), `share`, `feedback_sent`. Build funnels from these — e.g. *% who finish the coach*, *matches per player*, *where first-timers drop off*. Leave the key blank and nothing is loaded or sent.

## Hosting on GitHub Pages

After pushing this repo to GitHub:

1. Go to the repo's **Settings → Pages**.
2. Under **Build and deployment → Source**, choose **Deploy from a branch**.
3. Pick branch **main** and folder **/ (root)**, then **Save**.
4. After a minute, your game is live at `https://<your-username>.github.io/<repo-name>/`.

Share that link with testers — it works on phones and desktops.

## Roadmap (not in this build)

Real-time multiplayer, accounts, daily-game scarcity, persistent groups/favorites, leaderboards, and monetization are all later phases that build on this validated core.
