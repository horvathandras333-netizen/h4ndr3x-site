# H4NDR3X — artist site

Single-page static site for **H4NDR3X** — a human-led, AI-assisted music
project with no fixed genre. Machines generate. H4NDR3X decides.

## Stack

Nothing. One `index.html` with inline CSS and vanilla JS, plus a folder of images.
No build step, no dependencies, no framework. Open the file and it works.

- **Font** — Space Grotesk, from Google Fonts
- **Players** — Spotify or YouTube embeds (per release), loaded only on click/open so nothing third-party runs on page load
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
grid are both built from `RELEASES`; give a release its own named `var` (e.g.
`var SPENT_IT_RIGHT = {...}`) and include that same object in `RELEASES`, so a
release that's both featured and in the grid can't drift out of sync. Point
`FEATURED` at whichever release object is currently featured.

Each release needs **either** a Spotify album id **or** a YouTube video id (not
both are required) — the site plays whichever one is present, and hides the
"Open in Spotify" button when there isn't one:

```js
// Spotify release
{ id: 'SPOTIFY_ALBUM_ID', cover: 'assets/cover-name.jpg', title: 'TITLE', meta: 'Single — 2026' }

// YouTube-only release (no Spotify link yet)
{ youtubeId: 'YOUTUBE_VIDEO_ID', cover: 'assets/cover-name.jpg', title: 'TITLE', meta: 'Single — 2026 · YouTube' }
```

`genre` and `mood` are optional freeform strings — add either (or both) to show
a small tag chip on that release's card, modal and (for `FEATURED`) the Latest
Releases card. There's no predefined list; write whatever fits. Leave them off
and no tag renders — no "unclassified" placeholder. H4NDR3X is intentionally
genre-open, so don't group releases by genre or add filter UI for this until
the catalogue is much larger.

`sample` is an optional path to a full-length MP3 (e.g. `assets/audio-name.mp3`)
— when set, a native `<audio controls>` player labeled "Full track" appears on
that release's featured card and its modal; leave it off and nothing renders.
Starting the featured video/Spotify preview pauses the sample player and vice
versa, so they can't play over each other.

The `id` is the album ID from a Spotify share link (`open.spotify.com/album/<THIS_PART>`);
the `youtubeId` is the `v=` parameter from a YouTube watch link. Cover art goes
in `assets/` as a square JPG — for a release whose only art is a 16:9 YouTube
thumbnail, composite it onto a square canvas (e.g. blurred fill top/bottom)
rather than hard-cropping it, so text in the thumbnail doesn't get clipped.

The Visuals section is a gallery driven by the `VIDEOS` array (`title`,
`youtubeId`, `thumb`) — independent from the release data, so it can feature
any video regardless of which release is currently `FEATURED`. Add an entry
to feature another video; each renders its own tile linking straight to that
video.

The All Releases grid shows the `RECENT_COUNT` newest entries in `RELEASES`
directly and collapses the rest behind a "Show N earlier releases" dropdown,
so the grid stays focused on current material as the catalogue grows. Bump
`RECENT_COUNT` in `index.html` as new releases push older ones down.

The mailing-list CTA uses `booking@h4ndr3x.com`; update that `mailto:` link if
you use a different inbox or add a dedicated mailing-list service. There is no
booking CTA — H4NDR3X does not take bookings.

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
