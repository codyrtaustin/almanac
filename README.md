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

All four build phases complete (see [PLAN.md](PLAN.md)): the 6-day Year 1
prologue with the checks-in-the-mail squeeze, baked sprite villagers on daily
schedules with dialogue banks, gifts, hearts and vignettes, 18 crops / 14 fish
/ four festivals, the full network arc (Bramm through Rolf, including the
walkable four-settlement chain morning), customer contracts, the Bramm & Sable
Restday romance, Old Ness's dignified refusal, grants, chickens, the ridge
marker and the white fox, PNG year-review export, and a WebAudio soundtrack
with four original jukebox tracks. Design decisions are documented in the
comment block at the top of `index.html`.

Dev/test hooks live on `window.ALMANAC` (state inspection, fast-forward,
day-skip helpers). They are not part of the game UI.
