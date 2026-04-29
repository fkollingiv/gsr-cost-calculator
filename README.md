# GSR Cost Estimator

A self-contained, browser-based cost estimator for the **Dartmouth Genomics and Molecular Biology Shared Resource (GMBSR)**. This interactive wizard helps researchers quickly estimate the cost of genomics experiments using current FY27 internal Dartmouth rates.

## Features

- **Multi-step wizard interface** — guides users through experiment configuration with a progress bar and intuitive card-based selections
- **Four experiment categories:**
  - **Bulk DNA/RNA Sequencing** — RNA-seq (Ribo-depletion, 3\'-End), TCR-seq, DNA-seq with configurable reads-per-sample and sequencing run selection
  - **Single Cell Genomics** — 10x Chromium (3\'/5\' RNA-seq, ATAC-seq, Multiome, Flex) and Honeycomb HIVE with cells-per-sample and reads-per-cell controls
  - **Spatial Genomics** — Visium HD and Xenium (Standard and 5K panels) with per-slide pricing
  - **Illumina Arrays** — EPIC Human Methylation and Infinium Mouse Methylation with batch-based labor calculation
- **Smart sequencing run recommendations** — calculates optimal run type based on total reads needed and recommends the most cost-effective option
- **Automatic labor estimation** — computes labor hours based on batch sizes and sample counts for each assay type
- **Optional add-ons** — nucleic acid extraction, QC (Qubit + Fragment Analyzer), FFPE processing, tissue/cell preparation, sample fixation
- **Detailed cost summary** — itemized breakdown with per-unit pricing, quantities, subtotals, and a grand total
- **Print-friendly** — built-in print stylesheet hides navigation elements for clean printouts
- **Zero dependencies** — entirely self-contained HTML/CSS/JavaScript, no external libraries required

## Files

| File | Description |
|------|-------------|
| `gsr-estimator.html` | The estimator — served via GitHub Pages and embedded into the public sites with an iframe |
| `website-setup-instructions.md` | Step-by-step guide for embedding the calculator on omics.dartmouth.edu and geiselmed.dartmouth.edu/gsr |
| `FY27 GENOMICS RATE WORKSHEET 4.9.26.xlsx` | Source rate worksheet used to derive the pricing data |

## Getting Started

1. Open `gsr-estimator.html` in any modern browser
2. Select an experiment category
3. Configure your assay, sample count, and add-ons
4. Review the itemized cost estimate
5. Print or share the estimate with your collaborators

## Deployment

`gsr-estimator.html` is served via GitHub Pages and embedded on the WordPress sites using an auto-resizing iframe. See `website-setup-instructions.md` for the iframe snippet and step-by-step instructions covering:

1. Creating the calculator page on `omics.dartmouth.edu`
2. Adding a navigation button to the Genomics and Molecular Biology page
3. Adding a link on the GSR homepage at `geiselmed.dartmouth.edu/gsr`

## Updating Rates

Pricing data is stored in the JavaScript `P` object near the top of the script. When rates change for a new fiscal year, update the values in that object and push to `main` — GitHub Pages will publish the new version automatically and every embedding page picks it up on next load.

## Tech Stack

- **HTML5 / CSS3 / Vanilla JavaScript** — no frameworks or build tools
- **CSS Custom Properties** — Dartmouth green color scheme (`#006845`)
- **Responsive design** — works on desktop and mobile
- **Print media queries** — clean printable output

## License

Internal use — Dartmouth College / Geisel School of Medicine.
