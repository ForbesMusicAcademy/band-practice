# Forbes Music Academy — Band Sheets

This repo is **public** and exists only to host `.html` files that let
Forbes Music Academy students open their band-class chord/tab chart in
Play-along mode from home, via a plain link, no sign-up, no app.

## What's in here — and what isn't

- One `.html` file per song. Each is the Band Sheet Builder tool with that
  song's chart baked in. No student names, no personal data, no business
  records — this repo is a publish target for chart data only.
- `index.html` — a plain list of links to every song.
- `robots.txt` — asks search engines not to index this (families get the
  link directly; it's not meant to be discoverable, though it is public).

## Where the real source lives

This repo has **no source of truth** — it's disposable and fully
regenerable. The actual chart data, the tool's source code, and the build
scripts all live in Dave's private workspace repo, in:

- `structured-band-songs/*.json` — the canonical saved chart per song
- `tools/band-sheet-builder.html` — the master tool
- `tools/build-all-preloads.py` — rebuilds every song from the master +
  writes this repo's `index.html`

## Publishing an update

From the private workspace's `tools/` folder:

```
python3 build-all-preloads.py
```

That regenerates `hosted-songs/` there. Copy its contents into this repo,
commit, and push — GitHub Pages picks it up automatically.

## Hosting

Served via GitHub Pages from this repo's default branch. If a custom
domain gets set up later (e.g. `songs.forbesmusicacademy.com.au`), it'll
be recorded here.
