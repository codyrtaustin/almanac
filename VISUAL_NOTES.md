# Visual comparison notes — ALMANAC vs. HM64 reference

Captured from a side-by-side pass against real HM64 screenshots (RPGFan
gallery) on 2026-07-19. Held pending an art bible from the user before any
implementation. Reference images are not stored in this repo — descriptions
only, per the project's technique-not-expression rule (see the header of
`index.html` and `almanac-project` memory).

## Findings, roughly worst-gap-first

1. **Crop sprites read as blobs, not vegetables.** HM64's ripe crops are
   large, glossy, saturated, and identifiable by silhouette alone (corn looks
   like corn from across the field). ALMANAC's ripe-stage sprites are small,
   pale, and largely interchangeable — a ripe turnip reads as "pale circle,"
   not "turnip." Fix direction: bigger sprite footprint per ripe tile, higher
   saturation, and a distinct per-crop shape language (not just a leaf-blob +
   a color dot).

2. **Farm-zone ground reads dull/khaki instead of lush green.** HM64 keeps
   unplanted field grass vividly green; only tilled soil goes brown. ALMANAC's
   `TCLS.SCRUFF` texture (in `p045_tilemesh.js` / the assembled `index.html`)
   applies a brownish speckle overlay uniformly across the whole farm-zone
   ground classification, not just genuinely overgrown `wild` tiles — this
   mutes the green across the entire field. Fix direction: restrict the scrub
   overlay to actual wild/neglected tiles, or lighten it substantially.

3. **Dialogue box is a flat cream plaque; reference is a carved wood sign.**
   HM64 boxes show visible wood-grain texture, a beveled/rounded-log border,
   and a small decorative icon (family emblem, or a blue-gem continue marker)
   in place of ALMANAC's flat color fill + chevron. Contained, low-risk
   texture upgrade.

4. **Structural: HM64's world grid is rotated ~45° relative to the camera.**
   Fields, animal pens, and fence lines are laid out so tile edges project as
   diamonds on screen rather than axis-aligned rectangles — a deliberate
   isometric-readability trick. Matching this exactly means rotating the
   tile/collision/targeting system, which conflicts with SPEC.md's locked
   camera pillar ("yaw 0 — every storefront faces the player") and is a large,
   late-stage structural risk. **Do not implement without explicit sign-off**
   — flagged, not queued.

5. **Confirmed intentional, not a gap:** real N64 output is heavily
   bilinear-blurred (soft mipmapped trees, hazy distance). ALMANAC's spec
   explicitly calls for "sharpened HM64" — crisp pixels replacing that blur.
   Current sharp rendering is correct per pillar §3; no action needed.

## Status

Waiting on an art bible from the user before scoping implementation. When
that arrives, re-derive priority against it rather than the ranking above —
the ranking here is purely "distance from reference," not "importance to the
final look."
