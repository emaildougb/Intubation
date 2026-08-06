# NCEMS Intubation Guide

Field airway management reference for North Country EMS / Clark Fire District 13 paramedics. Single-file web app — no build step, no dependencies, hosted on GitHub Pages.

**Current version: v2.3**

## Links

- **Live app:** <https://ncemsderek.github.io/Intubation/>
- **Repo:** <https://github.com/ncemsderek/Intubation>
- **Upload new version:** <https://github.com/ncemsderek/Intubation/upload/main>

## Files in this repo

- `index.html` — the entire app (HTML, CSS, JS in one file)
- `apple-touch-icon.png` — 180x180 home-screen icon (pale logo on forest green)
- `icon-512.png` — 512x512 icon for general / PWA use
- `NCEMS_logo_transparent.png` — logo backdrop on the splash screen
- `README.md` — this file

## How to deploy an update (iPhone)

1. Save the new files from Claude to your Files app.
1. Open the upload link above in **Safari** (the GitHub app can’t upload files).
1. Tap “choose your files,” pick `index.html` (and `apple-touch-icon.png` + `icon-512.png` the first time), scroll down, tap **Commit changes**.
1. Confirm `index.html` is named exactly `index.html`.

**iOS cache note:** After every deploy, anyone using the home-screen icon must **delete and re-add it** to see the update (and to pick up the new app icon). Test in plain Safari first.

## Home-screen icon

When someone adds the live link to their home screen, it now shows the NCEMS airway icon (pale logo on forest green) and opens full-screen like a native app, labeled “Intubation.”

## Sections

- **DSI** — weight dosing, Target Vital Signs gate, 3-min timer, LEMON, Mallampati, equipment, considerations, DOPE
- **Adult Crash Airway** — weight dosing, failure path, DOPE
- **Peds RSI** — Broselow color-coded ages or length sizing, full dosing, integrated Target Vital Signs + timer
- **Post-Intubation** — Fentanyl / Ketamine / Midazolam with re-dose reminder timers
- **Concentrations (Admin)** — tap the version button on the splash to verify drug concentrations + contact info

## Key features

- Weight dosing in **kg (default)** or lbs with quick presets; switching units keeps the entered number.
- Doses in mL (large, inline) and mg; Ketamine + Rocuronium marked preferred.
- Tap a med card to log it **GIVEN** with timestamp; multi-dose; running count.
- **Meds Given log** — per-dose timestamps, delete one with its x, or Clear All (confirms, then closes).
- **Max-dose warning** (Ketamine/Rocuronium/Etomidate/SUX/Midazolam) — once per drug, “Give Dose Anyway” / “Return to Last Page.”
- **Post-intubation re-dose timers** — Fentanyl 5 min, Ketamine 15 min, Midazolam 15 min; blinks when due.
- **3-minute timer met** blinks a “3 MIN MET — PROCEED” notice (DSI + Peds).
- **1-hour session reset** to the warning page; clears prior call’s meds and timers.
- Disclaimer / warning page on first load and each session.
- iPad-optimized large fonts, high-contrast Target Vital Signs buttons, SF Mono numbers.

## Easter egg

Tap anywhere on the splash background 5 times quickly -> a Bigfoot strides across the bottom for 3 seconds.

## Changelog

### v2.3

- **Home-screen icon added** — `apple-touch-icon.png` (180x180, pale NCEMS airway logo on forest green) plus web-app meta tags so the app installs to the home screen with a real icon, full-screen, titled “Intubation.” Also includes `icon-512.png`.

### v2.2

- Concentrations page contact email ([d.boyce@northcountryems.org](mailto:d.boyce@northcountryems.org)); Succinylcholine -> SUX in the table; consistent scroll anchors; max-dose warning shows once per drug with “Give Dose Anyway” / “Return to Last Page”; Midazolam “?” opens a red tap-to-close popup.

### v2.1

- Concentrations admin page, max-dose warning, single-dose delete in Meds Given, Midazolam “?” toggle, default unit kg, unit-switch keeps number, 3-minute timer-met blink.

### v2.0

- Version checkpoint rolling up v1.6-v1.9: clickable/multi-dose med cards, Meds Given log, Target Vital Signs buttons + auto-scroll, peds DSI integration, disclaimer page, DOPE boxes, walking Bigfoot, 1-hour reset, post-intubation re-dose timers, Midazolam warning, SF Mono font.

## Protocol basis

Built on the **2026 Clark County EMS Patient Care Protocols**. Other agencies may stock different concentrations — verify on the Concentrations page before use.

## Disclaimer

Reference tool only. Does not supersede clinical judgment. Do not work outside your scope of practice. Verify all doses, concentrations, and protocols against your service’s current standards before administration.