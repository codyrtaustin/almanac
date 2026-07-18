# ALMANAC — Build Plan

The full spec lives in [SPEC.md](SPEC.md) and is the source of truth. The `/goal`
command caps conditions at 4000 characters, so the plan is chunked as **four
sequential goal conditions** — one per build phase from SPEC §19 — each a compact,
verifiable acceptance checklist that references SPEC.md by section rather than
restating it. Run them one at a time; each phase ends with a runnable single-file
`index.html` and a self-run browser acceptance check.

## How to use

Before starting each phase:

```
/goal <paste contents of goals/phase-N.txt>
```

| Phase | Goal file | Scope (SPEC §19) | Ships |
|---|---|---|---|
| 1 — The Farm & The Year | [goals/phase-1.txt](goals/phase-1.txt) | Worldgen, camera, controls, farming loop, clock + rollover, check-mail lag, saves, full 6-day Year 1 with placeholder dialogue | Year 1 playable end-to-end ≤25 min |
| 2 — The Town | [goals/phase-2.txt](goals/phase-2.txt) | 12 chibis + bake + portraits, dialogue, schedules, shops, gifts/hearts, mail, Ledger v1, Journal v1, menus | Year 1 with real scenes; a living town |
| 3 — The Years | [goals/phase-3.txt](goals/phase-3.txt) | Full crop/fish/forage tables, weather, 4 festivals, vignettes, arc stages 3–4, contracts, upgrades, jukebox v1 | Year 2 as a full ~55-min farm year |
| 4 — The Life | [goals/phase-4.txt](goals/phase-4.txt) | Stage 5 (Rolf), Bramm & Sable, Old Ness, grants, animals, fox, year-review PNG, full audio, polish | Full arc ≈80 min; §20 acceptance |

## Chunking rationale

- **SPEC.md carries the 31k chars; goals carry only pass/fail conditions.** Each
  goal is 3.3–3.6k chars, safely under the limit, and every item is phrased as
  something checkable by playing the build in a browser.
- Phase boundaries follow SPEC §19 exactly, so each goal ends on the spec's own
  self-check acceptance row (expanded into concrete verifiable bullets).
- Cross-phase dependencies are ordered: phase 3's Maren egg contract allows a
  stub source until phase 4 delivers chickens; Rolf's 9-heart vignette is built
  in phase 3 but stays gated until phase 4's stage 5.

## Conventions for the build

- One file: `index.html` at repo root, sections CONFIG / RNG / WORLDGEN /
  RENDER / SIM / CAST / UI / AUDIO / SAVE, all tuning in one CONFIG object.
- Unspecified design decisions get logged in a comment block at the top of the
  file (per SPEC's development protocol).
- Test after every phase: desktop Chrome at 640×360 + touch device emulation.
