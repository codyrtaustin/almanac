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

Phases 1–2 of 4 (see [PLAN.md](PLAN.md)): the farm, the seasonal clock, the
checks-in-the-mail economy, and the full 6-day Year 1 prologue are playable
end-to-end — now with baked sprite villagers on daily schedules, authored
dialogue banks, gifts and hearts, portraits with expressions, shop buy/sell,
forge tool upgrades, Ledger reports with per-crop profit chips, and invoiced
odd jobs. Design decisions taken during the build are documented in the
comment block at the top of `index.html`.

Dev/test hooks live on `window.ALMANAC` (state inspection, fast-forward,
day-skip helpers). They are not part of the game UI.
