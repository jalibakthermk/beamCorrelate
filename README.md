# beamCorrelate

Simulation vs. goniometer measurement correlation for automotive lamps.

beamCorrelate puts a simulated and a measured luminous intensity distribution on one H-V grid, lines them up, and shows where and by how much they differ. It runs entirely in the browser: files are read locally and never uploaded.

## Features

- **Import:** IES LM-63 (Type A, B and C, including symmetric files), EULUMDAT (LDT), and CSV (matrix or H, V, cd columns; comma, semicolon or tab separated).
- **Lamp functions:** low beam (RHT/LHT), high beam, front fog, cornering, DRL, position, stop, direction indicator, rear fog and reversing. Each function sets its own comparison window, grid step, test points and demo data.
- **Alignment:** best fit (log cross-correlation), hot-spot centroid, manual offset or none.
- **Scaling:** match flux in the window, match Imax, manual factor or absolute values.
- **Ratio map:** measured ÷ simulated on a log₂ colour scale, masked below a chosen % of Imax, with RMS deviation, bias, share of cells within tolerance and correlation.
- **Isocandela and contour overlay:** side-by-side false-colour plots and solid/dashed contour overlay.
- **Scans:** horizontal and vertical intensity scans.
- **Cut-off analysis** (low beam, front fog): sharpness G = log₁₀ I(β) − log₁₀ I(β+0.1°) from vertical scans in 0.05° steps, cut-off position β at each scan, linearity, elbow position and shoulder angle, with a warning when the data resolution limits G.
- **Test points:** per-point measured vs simulated values with pass/fail for both, using absolute limits (`min`, `max` in cd) or limits relative to Imax (`minRel`, `maxRel`).
- **Exports:** HTML report with plots, test-point CSV and ratio-grid CSV.

## Usage

Open `index.html` in a browser, or serve the repository with GitHub Pages. A synthetic demo pair loads on start; choose a lamp function and load your own measured and simulated files.

## Conventions

- H is positive to the right (R), V positive upward (U), seen from behind the lamp.
- ΔH/ΔV is the shift applied to the simulation so it lines up with the measurement.
- Type A/B IES files and CSV grids are read as H-V angles directly. Type C (IES/LDT) assumes the optical axis at C0/γ90 with C90 to the right; use "Mirror left/right" if a beam comes out flipped.
- Cut-off position β is the centre of the gradient peak (inflection of log I); linearity is the spread of β across the scan positions.

## Regulation values

Preset limits (ECE R112 class B low-beam points, high-beam points, cut-off G ≥ 0.13 and linearity ≤ 0.2°) are included for convenience. Check them against the regulation revision you are working to. Fog, cornering and signal-lamp presets contain grid positions only; add limits in the test-point editor.

## Dependencies

[Plotly.js](https://plotly.com/javascript/) 2.35.2 from cdnjs and IBM Plex fonts from Google Fonts. No build step.

© 2026 Jalib Akther
