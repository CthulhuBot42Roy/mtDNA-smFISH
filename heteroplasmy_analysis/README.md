# smFISH Heteroplasmy Analysis

Quantitative analysis of mitochondrial DNA heteroplasmy inheritance from NSCs to progeny cells from single-molecule FISH data.

## View Report

The rendered analysis report is available online via [GitHub Pages](https://JvdAlab.github.io/smFISH_heteroplasmy_analysis.html):

## Structure

The directory structure is as follows:
```
heteroplasmy_analysis
    ├── data
    │   ├── NSC-progeny cell volume.xlsx
    │   └── NSC-progeny FISH mtDNA number.xlsx
    ├── cell.csl
    ├── README.md
    ├── smFISH_heteroplasmy_analysis_refs.bib
    ├── smFISH_heteroplasmy_analysis.html
    └── smFISH_heteroplasmy_analysis.qmd
```

## Data Description

`NSC-progeny FISH mtDNA number.xlsx`:
Contains mtDNA copy number measurements from single-molecule FISH experiments, including counts of total and mutant mtDNA molecules for NSCs and their progeny cells.

`NSC-progeny cell volume.xlsx`:
Contains cell volume measurements for NSCs and progeny cells, used for normalization and analysis of mtDNA density.

## Analysis Overview

The analysis includes:
  - Mixed-effects models for heirarchical data
  - Monte Carlo simulations
   - Approximate Bayesian Computation (ABC) analysis

### Prerequisites

To re-run this analysis, you need:

- **R** ≥ 4.4.2
- **RStudio** ≥ 2022.07 (includes Quarto)

### R Package Dependencies

Install the required R packages using the following code snippet:
```r
packages <- c(
   "here", "readxl", "janitor", "tidyverse","conflicted", "ggsci", "ggsignif", "ggridges", "RColorBrewer", "car", "nlme", "MASS", "EasyABC", "abc", "abcrf", "moments","kableExtra"
)

install.packages(packages)
```

## Usage

**RStudio**:
Open smFISH_heteroplasmy_analysis.qmd → Click "Render"

**Command Line**:
```bash
quarto render smFISH_heteroplasmy_analysis.qmd
```
