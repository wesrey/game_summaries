# Game Summaries

Open `index.html` through a web server to browse the summaries on a phone. From this folder, run:

```text
python -m http.server 8000
```

Then visit `http://<your-computer-ip>:8000/` on the phone while both devices are on the same network. The reader fetches and renders the Markdown files in the browser using `marked` and sanitizes the resulting HTML with `DOMPurify`.
