# H4NDR3X — artist site

Single-page static site for the drum & bass project **H4NDR3X**.
Rolling breaks. Subterranean bass. Machine-tight drums, engineered for 3 AM.

## Stack

Nothing. One `index.html` with inline CSS and vanilla JS, plus a folder of images.
No build step, no dependencies, no framework. Open the file and it works.

- **Font** — Space Grotesk, from Google Fonts
- **Players** — Spotify embeds, loaded only on click so nothing third-party runs on page load
- **Motion** — CSS keyframes throughout, all disabled under `prefers-reduced-motion`

## Run it

```bash
python -m http.server 8000
```

Then open http://localhost:8000. Opening `index.html` directly off disk works too,
though a server is closer to how it behaves deployed.

## Editing releases

Release data lives in one place — the `FEATURED` and `RELEASES` arrays near the top
of the `<script>` block in `index.html`. The featured card and the "All Releases"
grid are built from them, and every release opens a Spotify-backed detail dialog.
Adding a track means adding one object:

```js
{ id: 'SPOTIFY_ALBUM_ID', cover: 'assets/cover-name.jpg', title: 'TITLE', meta: 'Single — 2026' }
```

The `id` is the album ID from a Spotify share link:
`open.spotify.com/album/<THIS_PART>`. Cover art goes in `assets/` as a square JPG.

The Visuals tile is driven by the `FEATURED_VIDEO` object. When a specific video is
ready to feature, replace its `url` with the `https://youtu.be/VIDEO_ID` URL and
update its `label`.

The booking and mailing-list CTAs use `booking@h4ndr3x.com`; update those two
`mailto:` links if you use a different inbox or add a dedicated mailing-list service.

## Deploying

The `<link rel="canonical">`, Open Graph tags and structured data in `<head>` are
set to `https://h4ndr3x.com/`. Hosting anywhere else means updating those URLs,
or search engines and link previews will keep pointing at the domain. The share
image is `assets/og-h4ndr3x.jpg` (1200 × 630).

## Links

- [Spotify](https://open.spotify.com/artist/4HKwa55lGXawLWP4HIoaFa)
- [YouTube](https://www.youtube.com/@H4NDR3X)
- [Instagram](https://www.instagram.com/h4ndr3x.official/)
- [SoundCloud](https://soundcloud.com/handrex)
