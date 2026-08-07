# HANDOFF — Intubation

## What it does

Field airway management reference for NCEMS/Clark Fire District 13 paramedics — a single-file web app, no backend, built on the 2026 Clark County EMS Patient Care Protocols. Currently v2.3. Sections:

- **DSI** — weight-based dosing, Target Vital Signs gate, 3-minute timer, LEMON/Mallampati checklists, equipment list, DOPE troubleshooting mnemonic
- **Adult Crash Airway** — weight dosing, failure path, DOPE
- **Peds RSI** — Broselow color-coded ages or length sizing, full dosing, integrated Target Vital Signs + timer
- **Post-Intubation** — Fentanyl/Ketamine/Midazolam with re-dose reminder timers
- **Concentrations (Admin)** — drug concentration reference + contact info, reached by tapping the version button on the splash screen

Key behavior: tap a med card to log it "given" with a timestamp (multi-dose, running count), a Meds Given log with per-dose delete/Clear All, a max-dose warning (once per drug) for Ketamine/Rocuronium/Etomidate/SUX/Midazolam, post-intubation re-dose timers that blink when due, a "3 MIN MET" blink for the DSI timer, and a 1-hour session reset that clears the prior call's meds/timers. Disclaimer/warning page shows on first load and every new session. There's a Bigfoot easter egg: tap the splash background 5 times fast.

## Where the data lives

- **No backend, no server-side storage at all.**
- **`localStorage` only**, and only for in-session state: `medsGiven` (the log of doses given this call), `disclaimerAccepted` (versioned, currently gated on string `'2026.06'`), and `sessionStart` (epoch ms, used to expire the session after 1 hour and wipe `medsGiven`).
- This means nothing persists between calls except by design (the 1-hour reset explicitly clears it), and nothing is shared across devices — it's a purely local, per-phone reference tool.

## Structure

- `index.html` — the entire current app (v2.3): HTML, CSS, JS in one file.
- `apple-touch-icon.png` (180×180) and `icon-512.png` (512×512) — home-screen/PWA icons.
- `README.md` — thorough and current: deploy steps (must upload via Safari, not the GitHub app), iOS cache-clearing note, full changelog to v2.3, protocol basis, disclaimer text.
- `intubation-guide.html` — **see "Anything odd" below.**

## Anything odd

- **`intubation-guide.html` is a stale, older build (`<title>NCEMS Intubation Guide v1.3</title>`) left sitting in the repo alongside the current `index.html` (v2.3).** It's not referenced by the README's file list or the current app, and isn't linked from `index.html`. If someone opens `intubation-guide.html` directly (e.g. an old bookmark or a stray link), they'd see a stripped-down v1.3 version — no admin/concentrations page, no max-dose warning, etc. Worth deleting or clearly marking as archived so nobody deploys or links to it by accident.
- **iOS caches hard** — same as the other apps here. After every deploy, anyone using the home-screen icon has to delete and re-add it to see updates and pick up new icons.
- Disclaimer gating uses a hardcoded version string (`'2026.06'`) rather than tying to the app's own version number — if the disclaimer text changes, that string needs a manual bump or returning users won't be re-prompted.
- This is a **reference tool only** per its own disclaimer — doesn't supersede clinical judgment, drug concentrations should be verified against the service's actual stock on the Concentrations page before use.
