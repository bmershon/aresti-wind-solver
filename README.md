# Aresti Wind Solver

A single-page planner for placing an aerobatic sequence in the 1,000 m box with layered winds.

- Reads OpenAero sequence strings, `.seq` files, and Form A PDFs (Aresti catalog numbers)
- Top-down box view with judges, safety line, CIVA penalty line, moving wind, and the no-wind track
- Judges' view with box height limits, disqualification height, lowest-point target, and a wind-by-height profile
- Flies each figure with a point-mass energy model: loops wind-corrected to stay round, verticals and 45s drift, rolling turns not wind-corrected
- Entry and exit strategy solver: diving wing wags, level-off point, drive-in, start altitude, figure placement near the centre
- CIVA Section 6 Part 1 (2026) checks: heights, zone penalties, time limit, wind limits, axis directionality
- "Open in OpenAero" link for the official Forms A/B/C

**Demo status:** the default aircraft is a Sukhoi Su-26 with performance numbers estimated by the pilot from memory (top speed 175 kt, stall 60 kt, 6 g loops, pilot g limits +9.5 / −6), until replaced with measured AcroWorx performance. Treat results as planning aids, not flight guidance.

## Deploy to GitHub Pages

1. Create a new repository (for example `aresti-wind-solver`).
2. Upload `index.html`, `README.md`, `LICENSE`, and `.nojekyll` to the repository root.
3. In the repository, open **Settings → Pages**, set **Source** to *Deploy from a branch*, choose `main` and `/ (root)`, and save.
4. After a minute the site is live at `https://<your-user>.github.io/aresti-wind-solver/`.

Everything is in `index.html`. The only external requests are Google Fonts and pdf.js from cdnjs (used only when you open a PDF).

## Notes

- Settings and the last sequence are remembered in the browser (localStorage).
- The shared team library (saved strategies, aircraft profiles, wind reports) only works in the claude.ai hosted version; on GitHub Pages that panel shows as unavailable and everything else works.

## License

GPL-3.0. The figure catalog and sequence notation come from [OpenAero](https://openaero.net) by Ringo Massa and contributors (GPLv3), so this project is distributed under the same license. See `LICENSE`.
