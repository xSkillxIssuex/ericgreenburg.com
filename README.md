# Eric Greenburg — NLE Portfolio

A non-linear-editor styled portfolio site. Static HTML/JS/CSS — no build step, no server code.

## What's here

```
index.html            The site (open directly in a browser, or serve it)
support.js            Runtime that powers the page
netlify.toml          Netlify config (publish dir + cache headers)
assets/
  wwe_60.js           WWE 2K24 :60 timeline data
  whiteclaw.js        White Claw :30 timeline data
  wwe_2k24.mp4        WWE program video
  whiteclaw.mp4       White Claw program video
  splash-art.jpg      Loading-screen image
  instrument-mark.png Studio imprint
  eric-e-serif.png    Header monogram
```

Fonts load from Google Fonts and a couple of demo bins stream sample clips from public URLs,
so the live site expects an internet connection. The two featured pieces (WWE, White Claw)
are fully local.

## Deploy to Netlify

### Option A — Connect this Git repo (recommended)
1. Push this folder to a new GitHub repo (see below).
2. In Netlify: **Add new site → Import an existing project → GitHub**, pick the repo.
3. Build command: **leave blank**. Publish directory: **`.`** (already set in `netlify.toml`).
4. Deploy. Netlify serves the static files (with HTTP range support, so video scrubbing works).

### Option B — Drag & drop (no Git)
1. Go to https://app.netlify.com/drop
2. Drag this entire folder onto the page. Done.

## Push to GitHub

From inside this folder:

```bash
git init
git add .
git commit -m "NLE portfolio site"
git branch -M main
git remote add origin https://github.com/<you>/<repo>.git
git push -u origin main
```

> Note: `wwe_2k24.mp4` (~11 MB) and `whiteclaw.mp4` (~17 MB) are committed normally.
> They're under GitHub's 100 MB per-file limit, so no Git LFS is required.

## Run locally

Any static server works (don't just double-click — the dynamic data imports need HTTP):

```bash
python3 -m http.server 8080
# then open http://localhost:8080
```
