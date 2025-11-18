# mtDNA Nucleoid Colocalization & Spot Quantification (Fiji/ImageJ Macros)

## 🔬 Overview
This repository contains a set of **Fiji/ImageJ macros** developed for quantifying mitochondrial DNA (mtDNA) nucleoids and their spatial relationships within the mitochondrial network. The workflows support detection and colocalization analysis of:

- **CP** — Control mtDNA probe
- **dP** — Deletion mtDNA probe
- **T20** — TOMM20 mitochondrial network marker
- **TFAM** — Mitochondrial transcription factor A (nucleoid-associated protein)

All analyses are performed on **2D maximum-intensity projections** to consolidate near-diffraction-limited nucleoids into a single quantifiable plane.

These macros were developed as part of ongoing research into **mtDNA deletion dynamics and nucleoid organization**.

---

## 📜 Included Macros

| Macro filename | Purpose |
|----------------|---------|
| `1. User thresh_spot_quant_CPQuant_22_09.ijm` | CP–dP colocalization within TOMM20⁺ mitochondrial regions |
| `2. TFAM_user thresh_spot_quant_CP_Quant_22_09.ijm` | CP–TFAM colocalization within the mitochondrial network |
| `3. TFAM_user thresh_spot_quant_dP_Quant_22_09.ijm` | dP–TFAM colocalization within the mitochondrial network |
| `4. count cp_dp_within_t20 mask.ijm` | CP/dP nucleoid distribution: total cellular count vs. mitochondrial retention |

A detailed methods description is provided in:  
`For methods section_v3.docx`

---

## 🧬 Biological Rationale

Mitochondrial nucleoids contain mtDNA and associated proteins. Alterations in nucleoid number, distribution, and TFAM association are hallmarks of disrupted mitochondrial genetics.

This analysis enables quantification of:

- mtDNA deletion probe localization,
- CP vs. dP colocalization,
- TFAM association with nucleoids,
- proportion of nucleoids retained within mitochondria.

---

## 📸 Image Requirements

Input images must be:

- **4-channel fluorescence** images containing:  
  1. **Channel 1:** CP  
  2. **Channel 2:** dP  
  3. **Channel 3:** TOMM20 / T20  
  4. **Channel 4:** TFAM  

- Acquired as **z-stacks** and then **maximum-intensity projected**.

- Regions of interest (ROIs) drawn manually to isolate either a **cell** or **mitochondrial network**.

---

## ⚙️ Software Requirements

- **Fiji / ImageJ**
- Built-in functions only (no external plugins required)
- Suggested Fiji version: `1.53f` or newer

---

## 🧪 Processing & Analysis Summary

All pipelines share a common preprocessing strategy:

### **Signal preprocessing (CP and dP)**

- Background subtraction (rolling ball radius = 50 px)
- Gaussian blur (σ = 2)
- Laplacian deconvolution (5×5 kernel, center weight 24, surrounding -1)
- Minimum filter (radius = 2 px)
- Final Gaussian blur (σ = 2)

### **T20 mitochondrial masking**

- Background subtraction (50 px rolling ball)
- Contrast enhancement (0.35% saturation)
- Gaussian blur (σ = 2)
- Otsu thresholding to create mitochondrial mask

### **TFAM mask**

- Background subtraction (20 px rolling ball)
- Contrast enhancement and Gaussian blur (σ = 2)
- Otsu thresholding

### **Spot detection**

| Channel | Detection method |
|--------|------------------|
| CP     | Find Maxima (prominence = 15) |
| dP     | Find Maxima (prominence = 12) |
| TFAM   | Mask-based membership only |

### **Colocalization logic**

- CP–dP: **dP spot ≤ 3 pixels from CP spot**
- CP/dP–TFAM: **spot inside TFAM ∩ T20 mask**

---

## 📊 Output Metrics

| Metric | Meaning |
|--------|--------|
| Total CP/dP spot counts | Total nucleoids per image |
| Mitochondrial retention % | Spots located within T20 mask |
| CP–dP colocalization % | dP within 3 px of CP |
| CP–TFAM or dP–TFAM % | Spots within TFAM⁺ mitochondrial subregions |

Spot overlays are generated for **quality control**.

---

## ▶️ Running the Macros

1. Open a **maximum projected 4-channel image** in Fiji.
2. Draw ROI(s) to isolate a cell or mitochondrial region.
3. Run the desired macro.
4. When prompted, **adjust thresholds manually** for each channel.
5. Results will appear in the ImageJ Results table.

---

## 📤 Suggested Repository Structure

```
project/
│
├── macros/
│   ├── CP-dP_coloc.ijm
│   ├── CP-TFAM_coloc.ijm
│   ├── dP-TFAM_coloc.ijm
│   └── CPdP_mito_retention.ijm
│
├── example_data/   (optional)
├── results/        (auto-saved macros output)
└── For methods section_v3.docx
```

---

## 🧾 Citation

If you use or adapt these macros in published work, please acknowledge the developers and cite the associated research article when available.

> Citation text will be added here once finalized by the authors.

---

## ⚖️ License

This repository's maintainers will define the license at publication.

---

## 🤝 Contributions

Contributions, improvements, and validations across different imaging platforms are welcome.

To report issues or propose enhancements, please open a GitHub Issue or Pull Request.

---

## 📬 Contact

For scientific or technical correspondence, contact the repository maintainers.
