# CLEANED Batch Emissions Calculator (Venture37)

This repository provides an automated workflow to estimate livestock greenhouse gas (GHG) emissions using the **CLEANED** (Comprehensive Livestock Environmental Assessment) framework.  
It was developed for Venture37 Kenya data and is designed to scale to large farm datasets.

---

## 🧩 Overview

The script automates the CLEANED modeling workflow to:
- Import and harmonize farm-level Excel data collected through interviews.  
- Construct standardized CLEANED input objects per farm and livestock type.  
- Run core CLEANED modules for feed quality, energy, land, soil, nitrogen, and emissions.  
- Generate results as both Excel workbooks and JSON outputs.  
- Compute enteric methane (CH₄) intensity per kilogram of Fat- and Protein-Corrected Milk (FPCM).

This allows comparison of baseline versus improved feed basket scenarios and quantifies changes in emissions efficiency across 230+ farms.

---

## ⚙️ Key Features

- **Automated Processing**: Loops through multiple Excel input files.  
- **Standardized Outputs**: Writes full CLEANED result tables (Excel + JSON).  
- **FPCM Normalization**: Calculates CH₄ intensity (kg CH₄ · kg⁻¹ FPCM).  
- **Integrated Parameters**: Pulls reference data and emission factors from the CLEANED package.  
- **Scalable Design**: Reusable for national or program-level livestock mitigation assessments.

---

## 📁 File Structure

| File | Description |
|------|--------------|
| `cleaned_batch_emissions_fpcm.R` | Main script to execute full workflow. |
| `R/` | CLEANED component scripts (feed quality, energy, land, nitrogen, etc.). |
| `data/v37/` | Input Excel data (baseline and improved feed scenarios). |
| `outputs/` | Generated Excel and JSON results. |

---

## 🧮 Dependencies

- R ≥ 4.2  
- Packages: `cleaned`, `readxl`, `jsonlite`, `tidyr`, `dplyr`, `miceadds`, `data.table`, `openxlsx`, `s3fs`, `pacman`

Install dependencies:
```r
pacman::p_load(readxl, cleaned, jsonlite, tidyr, dplyr, miceadds, data.table, openxlsx, s3fs)
