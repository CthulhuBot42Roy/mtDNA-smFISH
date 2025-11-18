# mtDNA Nucleoid Quantification (Fiji/ImageJ)

This repository contains Fiji/ImageJ macros for the analysis of mitochondrial DNA (mtDNA) nucleoids and their colocalization with:
- **CP** (control probe),
- **dP** (deletion probe),
- **T20** (mitochondrial marker, TOMM20),
- **TFAM** (nucleoid protein).

Designed for **2D max-projected** images from confocal or SIM data.

## Main Functions
- Count CP and dP nucleoids
- Mitochondrial retention (CP/dP inside TOMM20 mask)
- CP–dP colocalization (≤ 3 px proximity)
- CP–TFAM and dP–TFAM association

## Requirements
- Fiji/ImageJ (recommended ≥ 1.53f)
- 4‑channel fluorescence image: CP, dP, T20, TFAM
- ROI selection per cell

## Usage
1. Open a max projection in Fiji.
2. Draw ROI (single cell/region).
3. Run chosen macro.
4. When prompted: set thresholds manually.
5. Results appear in the ImageJ Results table.

## Citation
Please cite the related manuscript once available.

## License
To be specified by repository maintainers.
