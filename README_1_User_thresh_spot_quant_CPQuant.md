# CP–dP Nucleoid Colocalization (User_thresh_spot_quant_CPQuant_22_09.ijm)

## Purpose
This macro quantifies **colocalization between control mtDNA (CP) and deletion-bearing mtDNA (dP)** within the mitochondrial network using TOMM20 masking and a centroid proximity rule.

It reports the proportion of **dP nucleoid spots** located within **3 pixels** of CP nucleoid spots, reflecting potential coexistence of deleted and wild‑type genomes within shared nucleoids.

## Required Image Channels
| Channel | Signal |
|--------|--------|
| 1 | CP (control mtDNA probe) |
| 2 | dP (deletion mtDNA probe) |
| 3 | TOMM20 / T20 mitochondrial mask |
| 4 | TFAM (not used in this workflow) |

Images must be **2D maximum‑intensity projections**.

## Processing Summary
Spot signals (CP and dP) are enhanced through:

1) Rolling ball background subtraction (radius 50 px)  
2) Gaussian blur (σ = 2)  
3) Laplacian deconvolution (5×5 kernel; center weight 24, surrounding −1)  
4) Minimum filter (radius = 2)  
5) Gaussian blur (σ = 2)

## Mitochondrial Mask
Generated from TOMM20 via:  
- Background subtraction (50 px)  
- Contrast enhancement (0.35% saturation)  
- Gaussian blur (σ = 2)  
- **Otsu thresholding** → binary T20 mask

## Spot Detection Parameters
| Channel | Prominence |
|--------|------------|
| CP | 15 |
| dP | 12 |

## Colocalization Rule
A dP spot is defined as colocalized when:

```
distance(centroid_dP, centroid_CP) ≤ 3 pixels
```

## Outputs
- Total CP nucleoids
- Total dP nucleoids
- Colocalized dP spots
- % dP–CP colocalization
- Optional ratio estimates of deletion burden
- Spot overlays for visual QC

---
