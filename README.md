# mtDNA-smFISH

Code and reproducible analysis for:

> **"Single-molecule mitochondrial DNA imaging reveals heteroplasmy dynamics shaped by developmental bottlenecks and selection in different organs in vivo"**
> [bioRxiv preprint](https://www.biorxiv.org/content/10.1101/2025.01.24.634671v1)

## Analyses

| Analysis | Description | Report | Source |
|----------|-------------|--------|--------|
| Heteroplasmy variance | NSC progeny heteroplasmy inheritance | [HTML](https://jvdalab.github.io/mtDNA-smFISH/smFISH_heteroplasmy_analysis.html) | [heteroplasmy_analysis/](heteroplasmy_analysis/) |

## Repository Structure

```
mtDNA-smFISH/
├── heteroplasmy_analysis/      # NSC progeny heteroplasmy analysis
│   ├── data/                   # Raw data files
│   ├── smFISH_heteroplasmy_analysis.qmd
│   └── README.md               # Detailed instructions
└── docs/                       # GitHub Pages rendered reports
```

## Requirements

- **R** ≥ 4.4.2
- **Quarto** (included in RStudio ≥ 2022.07)

See individual analysis directories for specific package dependencies.