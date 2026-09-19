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

## 12. Two more releases — "Taking It Well" and "Leave It Till the Morning" (2026-09-19)

Artist released two more YouTube-only singles the same day: **Taking It Well** (`f7NkQbZxwZU`, published 8 min before this entry, newer of the two) and **Leave It Till the Morning** (`1HzFskN_3GY`, published 24 min before). Followed the exact same pattern as item 11:

- `TAKING_IT_WELL` (`genre: 'Drum & Bass'`, `mood: 'Euphoric'` — from the video's own `#DrumAndBass #DnB` tags and description's "euphoric vocals") became the new `FEATURED` release, since it's the most recent of all releases.
- `LEAVE_IT_TILL_THE_MORNING` (`genre: 'Alternative'`, `mood: 'Heartbreak'` — from `#alternativemusic #HeartbreakSong`) and `BREAK_THE_FRAME` both moved into the regular `RELEASES` grid, same reference pattern as before.
- Cover art: the artist had already generated proper 1:1 covers for both (found in Downloads, `ChatGPT Image Sep 19, 2026, 11_58_12 AM.png` for Taking It Well, `11_42_35 AM.png` for Leave It Till the Morning) — used those directly, no compositing needed this time.
- Full-track samples: `Taking It Well (Extended remix).mp3` and `Leave It Till Morning.mp3` from Downloads. The "(Extended remix)" filename is misleading — its duration (257.8s) matches the YouTube upload (4:17–4:18) almost exactly, so it's the same track, not a different edit; used as-is.
- Stats `Releases` bumped `9+` → `11+` (11 tracks total now).

**Visuals section upgraded from one hardcoded tile to a real 3-video gallery** (improvement-ideas doc item 3, previously only partial) — now data-driven from a `VIDEOS` array (title, YouTube id, thumbnail), showing Taking It Well, Leave It Till the Morning and Break the Frame, each linking to its own video. Uses only real, already-available thumbnails — no new assets invented.

**All Releases split into recent + collapsible "earlier releases"** (same day, follow-up): with 11 tracks now, the artist asked to keep focus on the newest ones and hide older ones behind a dropdown. The grid now shows the 4 newest releases (`RECENT_COUNT = 4`: Taking It Well, Leave It Till the Morning, Break the Frame, Spent It Right — everything released today) directly; the other 7 sit inside a native `<details>`/`<summary>` dropdown labeled "Show 7 earlier releases," closed by default, styled to match the site's pill buttons. Cards inside the dropdown work identically to the visible ones (same click-to-preview modal). Bump `RECENT_COUNT` in `index.html` as more releases land.

- [x] Applied

---

## 13. Catalogue gap — "No Grand Design" and "Sparks in the Dark" (2026-09-19)

While researching the two newest releases, noticed the artist's channel had two older videos (~4 months old, April 2026) that were never added to the site at all: **No Grand Design** (`svJbG1zT8S8`) and **Sparks in the Dark** (`QIHhqhCQ_X8`). Flagged it; artist confirmed to add both. Neither is on Spotify, so both follow the `youtubeId` pattern from item 11. Both land in `RELEASES` only (older tier, inside the "earlier releases" dropdown) — neither is anywhere near recent enough to be `FEATURED`.

- `NO GRAND DESIGN`: `genre: 'Liquid DnB'`, `mood: 'Emotional'` — both directly from the video's own description ("deep, emotional drum and bass track... liquid DnB energy").
- `SPARKS IN THE DARK`: no `genre`/`mood` set. Its description talks about connection and memory but never names a genre or a single clear mood word the way the other tagged tracks do — left untagged rather than guess, per the site's "optional, no placeholder" convention.
- No `sample` (full-track MP3) for either — unlike the two newest releases, no matching audio file was available in the artist's Downloads folder for these older tracks.
- Cover art: neither had dedicated square art (unlike Taking It Well / Leave It Till the Morning, which already had ChatGPT-generated 1:1 covers waiting). Both composited from their 16:9 YouTube thumbnails with the same blurred-fill technique as the original Break the Frame fallback (item 11), since a hard crop risked clipping their thumbnail text/composition.
- Stats `Releases` bumped `11+` → `13+`.
- Not added to the Visuals gallery (`VIDEOS` array) — kept that at 3 curated/current videos per the original improvement-ideas ask; both are still reachable via "All videos ↗" and the All Releases dropdown.

- [x] Applied

---

## 14. All three newest releases featured, not just one (2026-09-19)

Artist asked for the 3 newest songs (Taking It Well, Leave It Till the Morning, Break the Frame) to all appear "under featured," not just the single newest one in a solo hero card.

Restructured "Latest Releases" from one hardcoded glass card (fixed `feat-*` element ids) into a **new `FEATURED_RELEASES` array** (`[TAKING_IT_WELL, LEAVE_IT_TILL_THE_MORNING, BREAK_THE_FRAME]`) rendered as N independent stacked glass cards via a `buildFeaturedCard(release)` function — same visual design as before, just built per-release instead of hand-authored once. Each card has its own scoped preview overlay, YouTube-embed iframe, and full-track sample player (no shared ids, so they can't collide or step on each other — verified each card's preview/sample toggle independently and cross-pauses correctly: opening one card's video preview pauses only that card's sample, and vice versa).

`FEATURED` (used by the Featured Tracks spotlight, and anywhere else that means "the single most current release") now reads as `FEATURED_RELEASES[0]` — still the newest release, unchanged behavior there. All three remain included in `RELEASES` too (same by-reference pattern as items 10/11), so they still appear in the All Releases grid.

To feature more or fewer releases, edit the `FEATURED_RELEASES` array — nothing else needs to change.

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
