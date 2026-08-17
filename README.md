# Hypoxia Tissue Metabolomics

Interactive portal for polar metabolite abundances across seven mouse tissues under graded hypoxia
and HIF stabilization.

**Live site: https://jain-lab-ucsf.github.io/hypoxia-metabolomics/**

## Contents

| File | Description |
|---|---|
| `index.html` | The portal. A single self-contained file with the dataset embedded &mdash; open it locally or use the link above. |

## Study design

Metabolon performed global metabolic profiling (HD4 platform) on brain, heart, liver, lung, muscle,
plasma, and epididymal white adipose tissue (eWAT) from mice exposed to varying oxygen tensions,
durations, and pharmacological treatment. The portal presents the ten conditions profiled in all
seven tissues, so every tissue panel spans the same axis:

| Group | Timepoints |
|---|---|
| 21% O&#8322; (control) | Room-air control |
| 8% O&#8322; | 3 h, 24 h, 1 week, 3 weeks |
| 11% O&#8322; | 3 h, 24 h, 1 week, 3 weeks |
| FG-4592 (HIF prolyl-hydroxylase inhibitor) | 24 h |

Most conditions comprise 6 animals.

## Features

- **Time Courses** &mdash; per-replicate abundances by condition, for one tissue or all seven at once
- **Volcano Plot** &mdash; all quantified metabolites by fold change and p-value for any pair of conditions
- **Heat Map** &mdash; log&#8322; fold change across tissues and conditions for a single metabolite
- **Info** &mdash; study design, analysis methods, and key terms
- Every tab exports a figure and a CSV of the underlying numbers

## Methods notes

- Abundances are median-scaled, imputed values on a linear scale. Plasma is normalized to volume
  extracted and eWAT to mass extracted; the remaining tissues use batch-normalized values. Because
  each tissue is scaled independently, compare abundances within a tissue and fold changes across
  tissues.
- Statistics are unpaired, two-sided Welch's t-tests on the linear values. **P-values are not
  corrected for multiple testing** &mdash; apply your own correction before drawing conclusions from a
  whole-metabolome comparison.
- The 8% and 11% O&#8322; 1-week liver samples were profiled in a separate run with its own control
  group. Because each run is median-scaled independently, these values are anchored to the main liver
  control (scaled per metabolite by the ratio of the two control means) so their fold change relative
  to control matches the value computed within their own run. They cover 787 of 1,043 liver
  metabolites; `n.d.` marks conditions where a metabolite was not detected.

## Citation

Jain Lab, Cardiovascular Research Institute, UCSF.
