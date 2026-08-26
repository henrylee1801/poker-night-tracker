# Stardust Poker Tracker

A single-file, no-backend poker night tracker: buy-ins, cash-outs, per-night
results, and a running lifetime leaderboard. Everything is stored in your
browser's `localStorage` — no server, no database, no account, no cost.

## Using it right now

Just open `index.html` in any browser (double-click it, or drag it into a
browser tab). It works fully offline. Add it to your phone's home screen
(Safari/Chrome → Share/Menu → "Add to Home Screen") for an app-like feel at
the table.

Because everything lives in that one browser's local storage:
- It's tied to **one device/browser**. Use whichever device you'll actually
  have at the table.
- Use the **Data tab → Export Backup** regularly (definitely after finishing
  a big night) so you have a `.json` copy of your history somewhere safe.
  Import restores it.
- Clearing your browser's site data / private-browsing mode will wipe it —
  export first if you're ever unsure.

## Hosting it for free (optional)

You don't have to host it anywhere — opening the file locally works fine.
But if you'd rather have a stable URL you can bookmark, any of these are
free and take a few minutes:

### Option A — GitHub Pages
1. Create a new GitHub repo (e.g. `poker-night-tracker`) and push this
   folder to it:
   ```bash
   cd poker-night-tracker
   git init
   git add index.html README.md
   git commit -m "Poker night tracker"
   git branch -M main
   git remote add origin https://github.com/<your-username>/poker-night-tracker.git
   git push -u origin main
   ```
2. On GitHub: repo → **Settings → Pages** → Source: `main` branch, `/root`.
3. Your site is live at `https://<your-username>.github.io/poker-night-tracker/`.

### Option B — Netlify Drop
Go to [app.netlify.com/drop](https://app.netlify.com/drop) and drag the
`poker-night-tracker` folder onto the page. You get a live URL instantly,
no account required (an account lets you keep the URL stable long-term).

### Option C — Cloudflare Pages
Similar to GitHub Pages: connect the repo at
[pages.cloudflare.com](https://pages.cloudflare.com), no build command
needed, output directory `/`.

Note: whichever URL you use, the data still only lives in **your browser**
on **your device** — hosting it just gives you a stable place to load the
page from, it doesn't add shared/multi-device storage. If you later want
everyone at the table to see live results from their own phones, that needs
a real backend (e.g. Cloudflare Workers + D1, still free) — happy to build
that version if you want it.

## What it does

- **Tonight tab** — add players as they sit down, log buy-ins (quick $20/
  $50/$100 buttons or a custom amount), and cash each player out at the end.
  Once everyone's cashed out it checks that total buy-ins == total
  cash-outs, so you catch chip-count mistakes on the spot.
- **History tab** — every finished night, with each player's buy-in,
  cash-out, and net.
- **Leaderboard tab** — lifetime net profit/loss per player across all
  finished nights, with nights played, total buy-in/cash-out, and best/worst
  night.
- **Data tab** — export/import a JSON backup, see quick stats, or wipe
  everything.
