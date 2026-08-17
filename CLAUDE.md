# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this is

A single static page for the band dRUId ZIRCONIA — no build step, no framework, no dependencies. Three files make up the entire site:

- `index.html` — page structure and content
- `style.css` — all styling
- `images/lcd-druid.svg` — the band's logo (LCD/dot-matrix style wordmark), displayed centered as the main visual. Converted from the source PDF (`pdf2svg` + `svgo`), then hand-cropped to a tight viewBox around the artwork.
- `CNAME` — GitHub Pages custom domain file, must contain exactly `druidzirconia.com`

## Design constraint

The site is intentionally minimal: black background, monospace font, ASCII/terminal aesthetic in the spirit of the original (ASCII-graphics) version of Dwarf Fortress. Keep additions consistent with that look — no web fonts, no frameworks, no imagery beyond the logo and simple bracketed text links (e.g. `[ bandcamp ]`).

## Previewing locally

No build step — open `index.html` directly in a browser, or serve the directory for relative-path fidelity:

```
python3 -m http.server
```

## Deployment

Hosted on GitHub Pages directly from the `main` branch root (`treysuiter/druid-zirconia-webpage`), pushing to `main` deploys automatically. The custom domain `druidzirconia.com` is wired up via the `CNAME` file plus DNS records at the registrar (Namecheap):

- Four `A` records on `@` pointing to GitHub Pages' IPs (185.199.108/109/110/111.153)
- A `CNAME` record on `www` pointing to `treysuiter.github.io.`

There is also a `TXT` record on `_atproto` (`did=did:plc:cjb5hxguh27ca2wasffr7vvl`) unrelated to web hosting — it verifies `druidzirconia.com` as the band's Bluesky handle via AT Protocol. Do not remove it when touching DNS.
