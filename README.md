# 🧊 Volumetric Quantifications and Dynamics of Retrogressive Thaw Slumping (RTS)

**Companion repository for:**  
> **Dai, C. et al. (2025)**  
> *Volumetric quantifications and dynamics of areas undergoing retrogressive thaw slumping in the Northern Hemisphere*  
> *Nature Communications*, 16, Article 62017  
> DOI: [10.1038/s41467-025-62017-0](https://www.nature.com/articles/s41467-025-62017-0)

---

## 🧭 Overview
This repository supports the first **Northern-Hemisphere-scale volumetric quantification** of active *Retrogressive Thaw Slumping (RTS)* using **ArcticDEM** time-series data (2012–2022).  
The work combines *high-resolution digital elevation models (2 m)*, *deep learning (Mask R-CNN)*, and *climate reanalysis (ERA5)* to identify, segment, and quantify thaw-driven terrain deformation in permafrost landscapes.

---

## 🔬 Scientific Context
RTS is a **thaw-driven mass-wasting process** marked by upslope backwasting of ice-rich permafrost.  
When headwalls thaw and collapse, terrain subsides, releasing sediment and organic carbon.  
This study fills a long-standing data gap by quantifying **RTS volumetrics, latitudinal patterns, and carbon release** across the Northern Hemisphere (≥ 60° N).

---

## 🧩 Key Findings

| Metric | Result |
|:--|:--|
| Active RTS sites | **2,747** (≥ 10 000 m²) |
| Total volume loss | **(317.0 ± 0.3) × 10⁶ m³ (2012–2022)** |
| Median volume loss | **62 484 m³** |
| Median subsidence | **−3 m** |
| Median annual yield | **5 013 m³ yr⁻¹** |
| SOC release | **~1.95 × 10⁻³ Pg C yr⁻¹ (~0.2 % of gradual thaw)** |

- Temperature-driven RTS dominates > 71° N  
- Precipitation-driven RTS decreases linearly with latitude  
- Slight positive momentum (**+179 m³ yr⁻²**) indicates accelerating activity  

---

## 🛰️ Data Sources

| Dataset | Description |
|:--|:--|
| **ArcticDEM v4.1** | 2 m DEMs (n = 440 949) across ≥ 60° N |
| **ERA5 Reanalysis** | Temperature & precipitation (0.25° grid) |
| **NCSCD v2.2** | Soil organic carbon database (0–3 m) |

---

## 🧠 Methods Summary

### 1. DEM Co-registration & Change Detection
- Bundle adjustment removes horizontal/vertical bias (σ ≈ 0.3–0.5 m)  
- Sequential DEM differencing isolates elevation drops (retrogressive headwalls)  
- “Rainbow” temporal signature marks thaw-progression zones  

### 2. Threshold Pre-classification
```text
ΔElevation ≤ −1 m  
Area > 2 000 m²  
≥ 1 high-confidence pixel  
σ(time of change) > 1 year
