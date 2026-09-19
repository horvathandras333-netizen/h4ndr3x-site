# h4ndr3x.com — Rebrand Change Spec

Widening H4NDR3X from drum & bass to general music. These are find-and-replace targets against the live page; locate each string in the source HTML.

The anchor concept stays the same: human-led songwriting with AI-assisted refinement and production. What comes out is tempo and genre language.

---

## Correction (2026-09-19) — lyric-writing description

Earlier items in this doc (1, 3, 5, 6) described the process as "every lyric written by hand" / "100% human lyrics." That overstated it. The artist writes the lyrics but AI helps develop and refine them — corrected site-wide (meta description, About heading/body) to "human-led songwriting, AI-assisted production." See the "Superseded" notes on the affected items below; the live site now reflects the corrected description, not the original wording in those sections.

---

## 1. Head — title and meta

Highest impact. These are what Google and every link preview show.

**Title and `og:title`**

- Current: `H4NDR3X — Drum & Bass Producer`
- Proposed: `H4NDR3X — Producer`

**Meta description**

- Current: `H4NDR3X — drum & bass producer. Rolling breaks, subterranean bass, machine-tight drums engineered for 3 AM. Listen on Spotify and YouTube.`
- Proposed: `H4NDR3X — a human-AI production project. Every lyric written by hand. Listen on Spotify and YouTube.`

**`og:description`**

- Current: `Rolling breaks. Subterranean bass. Machine-tight drums, engineered for 3 AM.`
- Proposed: `Machines generate. H4NDR3X decides.`

Also updated `twitter:title`/`twitter:description` to match (they duplicated the old title/og:description), and removed the `"genre": "Drum and Bass"` field from the JSON-LD structured data — not in the original spec, but it's the same "what Google sees" category and directly contradicted the rebrand.

**Superseded (2026-09-19):** meta description overstated the lyric-writing process. Current live text: `Discover H4NDR3X: human-led songwriting, AI-assisted production and music without fixed genre boundaries. Listen on Spotify and YouTube.`

- [x] Applied

---

## 2. Hero eyebrow

- Current: `Drum & Bass — Producer`
- Proposed: `Producer`

- [x] Applied

---

## 3. Hero tagline

- Current: `Rolling breaks. Subterranean bass. Machine-tight drums, engineered for 3 AM.`
- Proposed: `Machines generate. H4NDR3X decides.`

This promotes the strongest line on the site out of the About section and into the position that was doing the genre-pinning.

Alternative, if the line stays in About instead:

`Every lyric written by hand. Everything else is up for argument.`

Applied the primary option (line promoted to hero, removed from About body). The alternative above was never applied and is now also inaccurate (see the lyric-writing correction) — don't use it.

- [x] Applied

---

## 4. About heading

- Current: `Engineered in the dark. Built for the floor.`
- Proposed (original): `Written by hand. Built with machines.`

**Superseded (2026-09-19):** overstated the lyric-writing process. Live heading is now `Human-led. Built with AI.`

- [x] Applied (current text differs from the original proposal above — see superseded note)

---

## 5. About body

**Current (pre-rebrand)**

> H4NDR3X is a human-AI production project — drum & bass with surgical precision, rolling breaks, subterranean low-end and atmospheres pulled from empty warehouses and late-night city air. Machines generate. H4NDR3X decides. Every release is mixed to move concrete.

**Proposed (original rebrand pass)**

> H4NDR3X is a human-AI production project. Every lyric is written by hand. The machines fill in around them, and nothing ships until it has been argued with. The genre moves from one release to the next — that part is deliberate. The method doesn't.

Note: if change 3 is applied, "Machines generate. H4NDR3X decides." comes out of here so it doesn't appear twice on one page.

**Superseded (2026-09-19):** "Every lyric is written by hand" overstated it — AI helps develop and refine the lyrics too. Live paragraph, revised same day to state the genre-open philosophy more directly:

> H4NDR3X is my music project, combining lyrics I write with AI-assisted refinement and production. I shape the words, steer the sound and decide what makes the final cut. Good music is good music — genre is just where a track happens to land. One release might hit like drum and bass, the next might sit closer to dark R&B or something anime-inspired. I don't chase a sound or stay inside one. I follow the song, and if it's worth hearing, it gets made.

- [x] Applied (current text differs from the original proposal above — see superseded note)

---

## 6. Stats block

- Current (pre-rebrand): `174` / `BPM`
- Proposed (original rebrand pass): `100%` / `Human lyrics`

Keeps the three-stat visual rhythm and swaps a genre declaration for the thing that actually holds the catalogue together. A fixed site-wide tempo is the single most genre-locking element on the page and contradicts any release that isn't 174.

`8+ Releases` and `2026 Active` stay unchanged.

**Superseded (2026-09-19):** `100% Human lyrics` overstated the process and was replaced (same day, separate request) with `1 Producer` — no numeric lyric-authorship claim at all now. Live stats row: `1 Producer` / `8+ Releases` / `2026 Active`.

- [x] Applied (current text differs from the original proposal above — see superseded note)

---

## 7. Latest Releases label

- Current: `174 BPM / 2026`
- Proposed: `2026`

- [x] Applied

---

## 8. All Releases — per-card genre tags

Add a short genre tag to each release card, drawn from what that track actually is:

- [ ] Sunfire
- [ ] I Found You in the Static
- [ ] Still You Wanted More
- [ ] Spent It Right

This turns the range into something legible rather than something that looks unfocused, and gives new material somewhere to sit without contradicting a header. It also makes per-release BPM useful again if it's wanted at card level — variation becomes a feature instead of a contradiction.

**Blocked / partially applied:** this list doesn't match the live site. The actual catalog is `SPENT IT RIGHT` (featured) plus `ADRENALINE`, `MY FOUNDATION`, `THE PRESSURE`, `NEON DETONATE`, `FINALLY BREATHING`, `FEARLESS`, `BRASSLINE` in the grid — none of "Sunfire," "I Found You in the Static," or "Still You Wanted More" exist in `index.html`. Per-track genres aren't something Claude can infer from titles alone.

For now, only removed the leftover `Drum & Bass` tag from Spent It Right's meta line (`Single — 2026 · Drum & Bass` → `Single — 2026`), matching the rest of the rebrand. No new genre tags added to any card yet.

Direction confirmed: labels are optional and freeform per track, no fixed list, no filter UI until the catalogue is bigger — see the improvement-ideas doc, item 6.

**Mechanism implemented.** Any release object in `index.html` can now take optional `genre`/`mood` strings, rendered as tag chips on its card, its release-details modal, and (for `FEATURED`) the Latest Releases card — nothing renders when absent, no "unclassified" placeholder. No labels have been added to any track yet; that's a separate content task for whenever the artist supplies them, not a blocker on this item.

- [x] Applied (mechanism); labels themselves are a future content task

---

## 9. Housekeeping

Unrelated to the rebrand, but live on the page now.

- [x] Visuals section is printing its own build instruction to visitors: "To add real videos: paste your YouTube video URL into each tile's href attribute". Delete. — already gone from the current `index.html`, nothing to delete.
- [x] Latest Releases contains an empty `<img>` with no `src`, rendering as a broken image. — removed the empty `src=""` attribute on `#feat-img`; JS already sets it on load, this just avoids the pre-JS broken-image/stray-request state.
- [x] Copyright line reads `© H4NDR3X` with a blank year. — already resolved; footer JS sets the year correctly on load.

---

## 10. All Releases catalogue completeness (2026-09-19)

`SPENT IT RIGHT` was the featured release but was missing from the "All Releases" grid — the catalogue looked one track short. Fixed by including the same `FEATURED` object by reference as the first entry in `RELEASES`, so its card, its release-details modal, and the featured card all stay in sync from one source of truth (no duplicated/divergent data).

- [x] Applied

---

## 11. First YouTube-only release — "Break the Frame" (2026-09-19)

New single, published today on YouTube (`KJ9i0ow6Eyw`), not yet on Spotify. Made it the new `FEATURED` release; `SPENT IT RIGHT` moved into `RELEASES` as a regular (non-featured) card by reference — same pattern as item 10.

The release system previously assumed every track had a Spotify album id. Generalized it:

- Any release can now carry `id` (Spotify) **or** `youtubeId` (YouTube), instead of requiring `id`.
- Featured "Preview" and the release-details modal play whichever is present — Spotify embed if `id`, YouTube embed if `youtubeId`.
- The modal's "Open in Spotify" button is hidden entirely for a release with no `id`, rather than pointing at a broken link.
- "YouTube" buttons/links point at that release's specific video when `youtubeId` is set, falling back to the general channel videos page otherwise.
- Cover art: initially composited from the 16:9 YouTube thumbnail (blurred square fill) since no dedicated art existed yet. Superseded same day once the artist supplied the real 1:1 cover (`ChatGPT Image Sep 19, 2026, 10_51_46 AM.png` from Downloads) — same Shibuya-crossing artwork, properly composed as a square. Saved as `assets/cover-break-the-frame.jpg`.
- Genre/mood tags: set `genre: 'Rap-Rock'` and `mood: 'Defiant'` on this release, using the video's own hashtags (`#RapRock #JRock`) and description (rejecting expectations, defiance) as the source — the artist's own words, not invented. First release to actually use the optional-tag mechanism from item 8.
- Visuals section's single tile now features this video specifically (own thumbnail + direct link) instead of the generic "visit the channel" tile — a first step on the improvement-ideas doc's item 3.
- Stats block `Releases` count bumped `8+` → `9+` to match the catalogue.
- All Releases subtitle changed from "Opens Spotify player inline" (no longer universally true) to "Opens an inline player".
- **Full-track audio sample** (same day, follow-up): the artist supplied `Break the Frame.mp3` (3:36, matches the video exactly) from Downloads. Added an optional `sample` field to the release data model — when set, a native `<audio controls>` "Full track" player appears on the featured card and the release modal; absent everywhere else, no placeholder. Starting the video preview pauses the audio sample and starting the sample stops the video preview, so they can't overlap. Saved as `assets/audio-break-the-frame.mp3` (4.8 MB). See README's "Editing releases" section for the field format.
- **Featured Tracks spotlight** (same day, follow-up): the artist noticed "Break the Frame" wasn't showing in the "Featured Tracks" section and asked for it to be spotlighted there. That section's player is a live Spotify artist embed, which structurally can only show tracks actually on Spotify — it was never going to show a YouTube-only release. Added a small clickable spotlight card above the embed, driven by `FEATURED` (cover, title, and an eyebrow that reads "not on Spotify yet" only when `FEATURED.id` is absent) — clicking it opens the same release-details modal as everywhere else. Automatically follows whichever release is `FEATURED` next, no manual upkeep needed.

- [x] Applied

---

## Not changing

- Visual design. Dark, technical and precise reads as "producer" more than "drum and bass" — the words were doing the pinning, not the styling.
- Site structure (Releases / Tracks / Videos / About / Contact).
- Spotify, YouTube, Instagram and SoundCloud links.
- The name itself. "H4NDR3X" carries no genre on its own.

## Elsewhere, once the site is done

Same genre language will need loosening in:

- Spotify for Artists bio
- MusicBrainz, Discogs and Genius genre fields
- DistroKid genre tags on future releases (set per track rather than defaulting to Drum & Bass)
