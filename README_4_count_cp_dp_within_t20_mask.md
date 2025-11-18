# CP/dP Mitochondrial Retention (count_cp_dp_within_t20_mask.ijm)

## Purpose
This macro quantifies **whole-cell vs. mitochondrial distribution** of CP and dP nucleoids. It measures whether mtDNA deletions are retained inside mitochondria or disproportionately present outside the network.

## Required Image Channels
| Channel | Signal |
|--------|--------|
| 1 | CP |
| 2 | dP |
| 3 | TOMM20 / T20 |
| 4 | TFAM (not used) |

## Metrics
Retention is defined as:

```
% CP_mito = (CP in T20) / (total CP) × 100
% dP_mito = (dP in T20) / (total dP) × 100
```

## Outputs
- Total CP spots
- CP spots within mitochondrial mask
- Total dP spots
- dP spots within mitochondrial mask
- Mitochondrial retention % for each channel

Useful for assessing nucleoid mislocalization or mitochondrial genome instability.

---
