# Practice Console

A personal practice tool, installable as a phone app (PWA). It picks today's session from the
Music Practice Library Google Sheet, runs a timer and metronome, logs the session, and shows
progress by category.

## How it fits together

- **Library:** the `Activities`, `Focus areas`, `Threads` and `Settings` tabs of the library sheet.
  Edit them in Google Sheets; the app reads them on every sync.
- **Session log:** the `Sessions` tab of the same sheet. The app appends one row per session.
  Notes, minutes and categories can be edited there; leave `Session ID` and `Start (ms)` alone.
- **On the device:** the session in progress, metronome settings per activity, and any sessions
  saved while signed out or offline (they upload on the next sync).
- **Sign-in:** Google Identity Services with the `spreadsheets` scope. The OAuth client ID in
  `index.html` is public by design. Access tokens last about an hour, so the app asks you to
  tap **Connect** when it needs a fresh one.

## Files

- `index.html` — the whole app (markup, styles, script)
- `sw.js` — service worker: network-first, cached copy when offline
- `manifest.webmanifest`, `icons/` — install metadata

Hosted with GitHub Pages from the `main` branch root.
