# CP–TFAM Association (TFAM_user_thresh_spot_quant_CP_Quant_22_09.ijm)

## Purpose
This macro quantifies **association of control mtDNA (CP) nucleoids with TFAM** within the mitochondrial network.

A CP spot is considered TFAM‑associated when it lies inside the binary intersection:
```
CP ∩ T20 ∩ TFAM
```

## Required Image Channels
| Channel | Signal |
|--------|--------|
| 1 | CP |
| 2 | dP (not used here) |
| 3 | TOMM20 / T20 mitochondrial mask |
| 4 | TFAM mask |

## TFAM Mask Generation
- Background subtraction (rolling ball 20 px)  
- Contrast enhancement and Gaussian blur (σ = 2)  
- **Otsu thresholding** to generate TFAM binary mask

## CP Spot Detection
Prominence threshold: **15**  

## Output Metrics
```
% CP_TFAM+ = (CP in T20 ∩ TFAM) / (CP in T20) × 100
```
Reports include:
- Total CP nucleoids in mitochondria
- CP–TFAM positive nucleoid count
- % CP–TFAM association
- Overlay image for QC

---
