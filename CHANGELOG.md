## v0.5.0 -- 2026-08-14

Okapi 0.5.0 — every linear symbology the engine can reach, and a New button that picks one

Okapi encoded exactly one symbology. It now encodes eight, and the New
button is a split control that chooses between them.

Symbologies
- EAN-13, EAN-8, UPC-A, UPC-E, Code 128, Code 128AB, HIBC Code 128, DPD.
- Every dimensional constant is read from its governing standard and
  cited in the source: the GS1 General Specifications first-hand for the
  retail rows, Zint's own standards-derived table for the rest, marked as
  Zint's reading rather than dressed up as ours.
- Each row is checked against Zint's independent derivation on every
  build, so a mistyped constant fails a test rather than shipping.

New
- One click makes another of what you are working on; the chevron opens a
  filterable menu grouped by family. The choice sticks: the open document
  is the memory, so the next New matches the last, until you change it or
  open something else.

The payload field
- Formats itself to mirror the printed HRI, driven by the same digit
  grouping the symbol draws.
- Says whether the payload is incomplete, valid, or bad, so a
  half-typed GTIN no longer looks like a broken one.
- Reports a bad code on the field that produced it, with the full
  diagnostic in the strip.

The inspector
- Sections appear according to what a symbology actually has: no guard
  descent without guard bars, no magnification without a standard range,
  no typography without an HRI.

Two new diagnostics
- A bar height with no standard to fall back on is reported rather than
  drawn as nothing.
- An HRI wider than the room its symbology gives it is reported rather
  than cropped silently from exported artwork.

Files
- Project format 2 records the symbology. Version 1 files still open, and
  read as EAN-13 — the only symbology the app that wrote them could make.


## v0.1.1 -- 2026-08-10

First published release of Okapi.

Barcode artwork for packaging prepress: EAN-13 with bar width reduction,
quiet zone and bar height compliance checks, and SVG or PDF export with
spot separations and overprint.

This is also the first release to carry auto-update. The app checks on the
splash at launch and every two hours while it is open, and installs updates
signed with the Okapi updater key. Builds are signed and notarized for
direct distribution on macOS arm64.


