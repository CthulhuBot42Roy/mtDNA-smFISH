# dP–TFAM Association (TFAM_user_thresh_spot_quant_dP_Quant_22_09.ijm)

## Purpose
This macro quantifies **association of deletion-bearing mtDNA (dP) nucleoids with TFAM** within mitochondria using logical mask intersection:

```
dP_TFAM+ = dP ∩ T20 ∩ TFAM
```

## Required Image Channels
Same structure as the CP–TFAM pipeline:

| Channel | Signal |
|--------|--------|
| 1 | CP (not used) |
| 2 | dP |
| 3 | TOMM20 / T20 |
| 4 | TFAM |

## dP Spot Detection
Prominence threshold: **12** (lower to accommodate weaker deletion-probe signal)

## Output Metrics
```
% dP_TFAM+ = (dP in T20 ∩ TFAM) / (dP in T20) × 100
```
Reports:
- Total dP nucleoids in mitochondria
- dP–TFAM positive nucleoids
- % dP–TFAM association
- Optional overlays for QC

---
