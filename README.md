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
grid are both built from them, so adding a track means adding one object:

```js
{ id: 'SPOTIFY_ALBUM_ID', cover: 'assets/cover-name.jpg', title: 'TITLE', meta: 'Single — 2026' }
```

The `id` is the album ID from a Spotify share link:
`open.spotify.com/album/<THIS_PART>`. Cover art goes in `assets/` as a square JPG.

The two tiles in the Visuals section are still placeholders pointing at the channel
root — swap each `href` for a real `https://youtu.be/VIDEO_ID` when there's a video
to point at.

## Deploying

The `<link rel="canonical">` and Open Graph tags in `<head>` are set to
`https://h4ndr3x.com/`. Hosting anywhere else means updating those four URLs,
or search engines and link previews will keep pointing at the domain.

## Links

- [Spotify](https://open.spotify.com/artist/4HKwa55lGXawLWP4HIoaFa)
- [YouTube](https://www.youtube.com/@H4NDR3X)
- [Instagram](https://www.instagram.com/h4ndr3x.official/)
- [SoundCloud](https://soundcloud.com/handrex)
