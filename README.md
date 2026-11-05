# Virtual MS

Interactive 3D models of mass spectrometers, built to learn how ions move through each instrument. Each page is a single self-contained HTML file (three.js loaded from a CDN). Open it in a browser; no build step.

| Page | Instrument | What it shows |
|---|---|---|
| [`orbitrap.html`](orbitrap.html) | Q-Orbitrap (Q Exactive / Exploris layout) | ESI → S-lens → bent flatapole → quadrupole → C-trap → HCD → Orbitrap. Quadrupole trajectories integrated live from the Mathieu equation, stability diagram, Orbitrap transient → spectrum, TMT 127N/127C resolution demo |
| [`timstof.html`](timstof.html) | timsTOF | Dual TIMS (parallel accumulation), mobility elution, diaPASEF window scheme (8 scans × 3 windows of 25 Th, m/z 400–1000), mobility-synchronized quad and collision energy, orthogonal TOF with reflectron, m/z × 1/K₀ detector frame |
| [`orbitrap-astral.html`](orbitrap-astral.html) | Orbitrap Astral | Parallel Orbitrap MS1 + DIA MS2 stepping through consecutive windows (selectable 2–20 Th), ion processor, all parts drawn to one true scale (1 unit = 20 mm), Astral analyzer with 24 oscillations and three-piece ion foil, parallel-acquisition timeline |

## View

Open [`index.html`](index.html) and pick an instrument from the selector at the top (or link straight to one with `#orbitrap`, `#timstof` or `#astral`). With GitHub Pages enabled (Settings → Pages → deploy from `main`), that is `https://yingxue-fu.github.io/virtual-ms/`. Each instrument page also works on its own.

## Caveats

These are teaching models, not instrument simulations.

- Timescales are slowed by many orders of magnitude (µs–ms events take seconds).
- Precursor clouds, peptides' fragments and spectra are simulated (the Orbitrap page uses real TMT-labelled peptide masses).
- Only the quadrupole in `orbitrap.html` uses integrated equations of motion; elsewhere motion is scripted to follow the correct physics trends (e.g. TOF ∝ √(m/z), Orbitrap frequency ∝ 1/√(m/z), TIMS elution order).
- The Astral page is drawn to one true scale (1 unit = 20 mm). Published sizes: 350 mm transfer octapole, ion processor r0 = 2 mm, ~335 mm drift, 24 oscillations, 5-electrode mirrors. Estimated sizes (mm): transfer tube 80, funnel 50, beam guide 70, quadrupole 110, C-trap 30, Orbitrap ≈30 × 20, IRM 80, ion processor 70, injection optics 60, mirrors 480 long × 150 thick with faces 240 apart. Other published numbers in its info cards come from Stewart et al. (Anal. Chem. 2023; ChemRxiv 2023/2024) and Thermo ASMS 2023 material; other sizes, and the exact ion foil outline, are estimates.

## Sources

- Stewart et al., *Parallelized Acquisition of Orbitrap and Astral Analyzers Enables High-Throughput Quantitative Analysis*, Anal. Chem. 2023, 95, 15656.
- Stewart et al., *Crowd Control of Ions in the Astral Analyzer*, J. Mass Spectrom. 2024.
- Stewart et al., *A Multi-Reflection Time-of-Flight Analyzer with a Long Focus Lens*, ChemRxiv 2024.
- Meier et al., *diaPASEF: parallel accumulation–serial fragmentation combined with data-independent acquisition*, Nat. Methods 2020.
