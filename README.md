# ALMANAC

A browser farming-village life sim in the lineage of Harvest Moon 64, built for
Ambrook. One seed = one valley; twelve authored villagers; year 1 is life before
the town gets connected. Full design in [SPEC.md](SPEC.md), build plan in
[PLAN.md](PLAN.md).

## Run it

The whole game is one file — no build step, no dependencies beyond Three.js r128
from CDN:

```
open index.html            # straight from disk, or
python3 -m http.server 8123    # then http://localhost:8123
```

Share a valley with the URL hash: `index.html#s=1234567`. Player progress is a
save code (Tab → Save): Base64 to clipboard or a downloadable `.almanac` file.
No localStorage/cookies/anything.

## Controls

- **WASD / arrows** move (virtual joystick + action button on touch)
- **E** — the one smart button: clear / till / plant / water / harvest / talk /
  ship / enter, by context. **Hold E** for the radial ring (pick held item)
- **Tab** menu · **J** journal · **M** map · **H** hide UI · **Esc** back

## Status

All four build phases complete (see [PLAN.md](PLAN.md)), plus two v2 passes:

- **v2 mechanics** — retuned against a study of HM64's reverse-engineered
  mechanics (ratios/formulas only, no expressive content): weighted weather
  tables with rare storms the whole town remembers the next day, hidden
  affection points with a talk/gift/repeat-talk economy, the priority-ladder
  dialogue evaluation order, soft crop death with a season-rollover reaper,
  a rest-only fatigue meter, and re-denominated sell values.
- **v2 graphics ("the HM64 pass")** — true tile-mesh terrain (one draw call,
  quantized corner heights, per-vertex shading), locked pixel-density ratios,
  trees/fences/props converted to baked billboard sprites, CI4-style 16-color
  quantization on every generated texture, real seasonal texture repaints
  (not tints), tick-based animation timing, and HM64-metric message boxes.
  Technique only — every texture, model, and sprite is generated at boot from
  original code; nothing from the reference game ships in this file.

Design decisions are documented in the comment block at the top of
`index.html`.

Dev/test hooks live on `window.ALMANAC` (state inspection, fast-forward,
day-skip helpers). They are not part of the game UI.
