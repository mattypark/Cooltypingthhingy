# Cooltypingthhingy

Type, and a garden grows out of your letters. Stems climb and weave over and under the type, leaves unfurl, roses open petal by petal and turn to face your cursor.

A one-file remix of [Type Garden](https://type-garden.vercel.app/) by [Akshat Agarwal](https://x.com/art_akshat), rebuilt from the source the original shares through its "Copy code" button. Plain canvas and JavaScript in a single `index.html`: no build step, no dependencies.

## Run it

Open `index.html` in a browser. To test on a phone on the same network, serve the folder:

```sh
python3 -m http.server 8000
```

## Typing

| Input | What happens |
| --- | --- |
| Type | Stems, leaves and roses grow out of each letter |
| Space | Cuts the stems: the word's last letter gets a bouquet, the next word starts a new garden |
| Backspace | The last letter withers |
| Enter | Clears everything |
| Move the pointer | The garden leans toward it and roses turn to face it |
| Click | A butterfly flies in and lands on the nearest open rose |
| Double-click | Plants a rose for everyone on the page |
| ⌘S / ⇧⌘S | Save PNG / SVG (also the buttons bottom right) |

Ten palettes sit in the bottom bar. On phones, tap to bring up the keyboard; predictive text and autocorrect are mirrored letter by letter.

## Poster

Switch to **Poster** (top right) for a 1080 × 1080 loop of any words:

- Motions: Breathe, Grow & wither, Typed, Gust, Reach, Scatter, Visitor
- Regrow garden reseeds it; palettes apply live
- Export the loop as MP4 (or WebM, depending on the browser) or as a zip of 30 fps PNG frames

## Settings

`SETTINGS` near the top of the script:

| Key | Default | |
| --- | --- | --- |
| `boil` | `true` | Lines redraw with a slight jitter, like hand-drawn animation |
| `recoil` | `20` | Pixels a cut tendril springs back (0–80) |
| `density` | `1` | How leafy and bridged each word grows (0.5–1.6) |
| `showHint` | `true` | Show the bottom bar |

## Live garden (optional)

Other visitors' cursors show up with flower names, and planted roses are shared. To turn it on, set `LIVE.url` and `LIVE.key` to a Supabase project URL and its **publishable (anon) key**, never the service-role key. Only Realtime broadcast and presence are used; there are no tables. Without them the page gardens alone, and `?tglocal` links tabs in one browser for testing.

## Differences from the original

- Letters are set in Playfair Display Bold from Google Fonts; the original uses GT Ultra, a commercial face. The interface uses DM Mono.
- SVG export keeps letters as live text with per-letter ids, and imports the web font so the file renders on its own. The original outlines each glyph from a font data file it hosts.
- The Supabase client loads from jsDelivr instead of a bundled copy.

## Credit

Design, drawing and motion: Akshat Agarwal, [Type Garden](https://type-garden.vercel.app/). This repo is a port of that work into a standalone page.
