# Fetchpoint — Bot Admin Console

A static admin dashboard for a video-download Telegram bot. Runs entirely
in the browser with mock data — no build step, no server required.

## Files

| File              | Purpose                                              |
|-------------------|-------------------------------------------------------|
| `index.html`      | Page structure and layout                             |
| `css/styles.css`  | All styling, including light/dark theme tokens         |
| `js/data.js`      | Mock data generator (jobs, users, platform mix)        |
| `js/render.js`    | Functions that turn data into DOM markup               |
| `js/theme.js`     | Light/dark/system theme toggle                         |
| `js/app.js`       | Entry point — wires up nav, filters, and initial render |

## Running it

Open `index.html` directly in a browser, or serve the folder locally:

```
python3 -m http.server 8000
```

then visit `http://localhost:8000`.

## Connecting real data

Replace the contents of `js/data.js` with calls to your bot's API (or
database) instead of the random generators. Keep the same shape for each
job object — `id`, `user`, `platform`, `link`, `size`, `time`, `status` —
and the rest of the dashboard (`render.js`, `app.js`) will keep working
unchanged.
