## v1.2.0 -- 2026-10-16

Release v1.2.0
- The barcode type is now a button on the line above the payload field: click the name to switch types.
- Under the field, a description of the chosen type: its history, what it carries, and where it is used.
- Rules for each type, in folding sections: what you can type, what the data means, print size and clear space, and where the symbol goes. Print sizes come from the same numbers the app checks against.
- Batch payloads: enter many codes at once, or paste a CSV column, and click through the results.
- Recent projects have moved to File ▸ Open Recent, with Clear Menu.
- Choose which barcode types the menu offers, grouped by family.
- The sidebar now scrolls when its content is taller than the window.


## v1.1.1 -- 2026-10-16

Release v1.1.1
Changed
- The libraries Okapi is built on are updated to their latest versions. Nothing changes in how the app looks or works.


## v1.1.0 -- 2026-10-14

Release v1.1.0
New
- A trashcan beside the code field clears it in one click and puts the cursor back, ready for the next code.
Changed
- The settings panel on the right now starts hidden for new users; open it with the panel button in the top-right corner. Whether it is open or closed is remembered between launches, so anyone who already has it open keeps it open.
- The icons beside the code field sit closer together.


## v1.0.0 -- 2026-10-14

Release v1.0.0
New
- Drag the barcode straight out of Okapi. Press on the barcode and drag it into an Illustrator or InDesign document: it lands exactly as a paste does, as editable vector artwork with its spot colour and overprint intact. Drag it onto the desktop or into a Finder folder to save it as a PDF named after the barcode's data. Hold ⌘ as you start the drag to include the white background, as ⌘-click does. A click that does not move still copies, as before.


## v0.11.0 -- 2026-10-14

Release v0.11.0


## v0.10.0 -- 2026-10-13

Release v0.10.0
New
- GS1-128 and GS1 DataMatrix. Type the GS1 element string with the Application Identifiers in brackets, e.g. (01)09506000134352(10)ABC123 or [01]09506000134352[10]ABC123. Okapi checks the data with the GS1 rules built into its barcode engine: an unknown AI or data of the wrong length is refused; a wrong check digit, an invalid date, letters where an AI expects digits, or more than 48 data characters in a GS1-128 is drawn and reported as a warning. Rules about which AIs must or must not appear together are not checked yet.
- Sizes for GS1-128 and GS1 DataMatrix follow the GS1 tables for where the barcode is scanned, including a new "Logistic units" choice (GS1 table 5) for SSCC and other logistics labels. A GS1-128 longer than GS1's 165.10 mm limit, quiet zones included, gets a warning.
- Every warning now points at the setting it is about. The settings panel marks each section that has a warning, even when folded, and clicking a warning in the strip at the bottom opens that setting and highlights it.
Changed
- The "Human readable digits" switch is now called "Human readable text", since GS1-128 prints an element string rather than digits.


## v0.9.3 -- 2026-10-13

Release v0.9.3
Fixed
- More reliable start-up updates. If the start screen cannot tell the app that an update has been found, it no longer starts a download that would be cut off halfway; Okapi opens at the version you have and picks the update up next time. Any other start-up hiccup of this kind is now recorded in the app's log instead of passing unnoticed.


## v0.9.2 -- 2026-10-13

Release v0.9.2
Fixed
- Okapi no longer cuts short its check for updates when it starts. On a slow connection the start screen could close while it was still waiting for an answer, so an available update was missed until the app had been open for two hours. The start screen now gets the full time it allows for the check, and still opens the app if something goes wrong.


## v0.9.1 -- 2026-10-13

Release v0.9.1
Fixed
- An update that Okapi gave up on while starting can no longer install itself later. If a download stalled and Okapi opened at the version you have, the download could still finish in the background and replace the app on disk while you were working. Now an update is only installed when its download finishes while the start screen is still waiting for it; otherwise it is simply picked up again next time.


## v0.9.0 -- 2026-10-12

Release v0.9.0
New
- Say where a barcode will be scanned. GS1 sets different size limits depending on where a barcode is scanned: at a retail checkout only, in warehouses and distribution only, or both. Until now Okapi always checked EAN and UPC barcodes against the retail-checkout limits, so an EAN-13 at 100% on an outer case showed no warning even though GS1 requires it to be at least 150% when it is also scanned in a warehouse. The Size section now has a "Scanned at" setting for EAN-13, EAN-8, UPC-A, UPC-E and ITF-14, shows the size range GS1 allows for your choice, and warns when the barcode is too small or too large for it.
- Changing the setting never resizes your barcode; it only changes what the warnings check against. Documents where you don't choose anything are checked exactly as before.
Changed
- Size warnings for EAN, UPC and ITF-14 now name the GS1 table they come from, e.g. "below the 1.50 minimum in GS1 symbol specification table 3 (Retail POS and general distribution)".


## v0.8.0 -- 2026-10-12

Release v0.8.0
New
- Export now tells you when the barcode is out of spec. If the file you export has warnings or errors, for example a quiet zone that is too narrow or a size below the GS1 minimum, a notice says so the moment the file is written, e.g. "Exported with 2 warnings". The file is still written; each finding is listed in the strip at the bottom of the window.
- Copying to the clipboard says the same, e.g. "Copied to clipboard — 1 warning".
Fixed
- A failed export (for example a full disk) is now reported as a failed export, instead of marking the barcode data as invalid.


## v0.7.2 -- 2026-10-12

Release v0.7.2

Fixed
- Updates now install when Okapi starts. Until now the launch-time update was cut off when the start screen closed, so installed copies never updated themselves. When a new version is available, Okapi now waits for it on the start screen, shows the download progress, and restarts into the new version.
- A download that stalls or fails no longer gets in the way: after 30 seconds without progress, Okapi opens at the version you have.

Please install this version once by hand from the .dmg below. Copies older than 0.7.2 still have the faulty start screen and will only pick it up if left open for two hours. From 0.7.2 on, every update installs by itself at launch.


## v0.7.1 -- 2026-10-09

Release v0.7.1

New
- ITF-14, drawn to GS1 with its 4.83 mm bearer bar frame on by default. A "Bearer bars" switch turns the frame off, with a warning. Type 13 digits, or paste a full 14-digit GTIN; its check digit is verified.
- Overprint fill is now on by default.
- A "White background" switch leaves out the white rectangle behind the bars.
- Hover over the barcode for a quick hint; keep the pointer there for a card with its size, X-dimension, ink, overprint and warnings.
- ⌘-click the barcode to copy it with the white background, even with the switch off.
- Hide the inspector with the panel button in the title bar. The panel, its folded sections and the preview zoom are remembered between launches.

Improved
- The placeholders in the payload field are easier to read in dark mode.


## v0.6.0 -- 2026-09-02

Release v0.6.0
Initial relase for data matrix and lots of other formats.


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


