# Analyzing EEG Spectra During Anesthesia

**QLS Discovery Day × McGill Initiative in Computational Medicine (MiCM)**  
**Date:** November 20, 2026 · **Instructor:** Ryan Huang · **Format:** 45-min workshop + 15-min Q&A

## Workshop overview

What can EEG tell us about the effects of different anesthetic drugs? We analyze a small open-science-derived set of rat epidural EEG traces labeled with wake, ketamine (low/high), and propofol (low/high) conditions. We estimate their power spectral densities (PSD), identify electrical noise, and use **FOOOF spectral parameterization** to describe 1/f-like aperiodic activity and candidate oscillatory peaks.

## Prerequisites

- No previous neuroscience or signal-processing training required; basic Python helps but is not essential.
- A laptop with a browser and internet access for **Google Colab**, or Python 3.10+ with Jupyter for local use.
- Basic familiarity with running a notebook cell is helpful. No GPU needed.
- Dataset and code are small (~5 MB plus dependencies).

## Learning objectives

By the end, participants can (1) visualize an EEG-like time series, (2) calculate and explain a Welch PSD, (3) identify line-noise contamination, and (4) estimate aperiodic spectral exponent and candidate oscillatory peaks with FOOOF.

## 45-minute outline

| Minutes | Topic |
|---|---|
| 0–20 | What do we know about anesthesia and EEG? Time vs frequency |
| 20–30 | Raw traces, Welch PSD, powerline artifact |
| 30–40 | Spectral parameterization and model fit |
| 40–45 | Drug comparison, alpha bandpower vs alpha peak |
| 45–60 | Q&A |

## Start here

1. Open [`Exercise/EEG_FOOOF_Workshop.ipynb`](Exercise/EEG_FOOOF_Workshop.ipynb) in GitHub, then upload that notebook directly to https://colab.research.google.com.
2. Download [`Exercise/data.mat`](Exercise/data.mat) from the repository beforehand. When the notebook asks for it, upload it in Colab (4.5 MB). If running locally, put the data file and the ipynb file in the same folder.
3. Run code cells in order. The first setup cell installs the stable `fooof==1.1.1` package if missing. The outputs are generated in a `results/` directory in the notebook's working directory.

## Citations

Arena & Storm (2018), data: https://doi.org/10.25493/4SPM-V00. 
Donoghue et al. (2020), FOOOF: https://doi.org/10.1038/s41593-020-00744-x. 
Additional scientific references in last slide of PowerPoint.
