# Analyzing EEG Spectra During Anesthesia

**QLS Discovery Day × McGill Initiative in Computational Medicine (MiCM)**  
**Date:** November 20, 2026 · **Instructor:** Ryan Huang · **Format:** 45-min workshop + 15-min Q&A

## Workshop overview

What can EEG tell us about the effects of different anesthetic drugs? We analyze a small open-science-derived set of rat epidural EEG traces labeled with wake, ketamine (low/high), and propofol (low/high) conditions. We estimate their power spectral densities (PSD), identify electrical noise, and use **FOOOF spectral parameterization** to describe 1/f-like aperiodic activity and candidate oscillatory peaks.

## Prerequisites

- No previous neuroscience or signal-processing training required; basic Python helps but is not essential.
- A laptop with a browser and internet access for **Google Colab** (recommended), or Python 3.10+ with Jupyter for local use.
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

## Start here — Google Colab (recommended)

1. Open [`Exercises/scripts/Anesthesia_EEG_Workshop.ipynb`](Exercises/scripts/Anesthesia_EEG_Workshop.ipynb) in GitHub, then select **Open in Colab** (or upload that notebook directly to https://colab.research.google.com/).
2. Download [`Exercises/data/data.mat`](Exercises/data/data.mat) from the repository beforehand. When the notebook asks for it, upload it in Colab (4.5 MB).
3. Run code cells in order. The first setup cell installs the stable `fooof==1.1.1` package if missing. The outputs are generated in a `results/` directory in the notebook's working directory.
4. Try the discussion questions and the extra fit-range challenge.

**Local Jupyter alternative:** from the repository root, run:

```bash
python -m venv .venv
# Activate the environment using the appropriate command for your OS.
python -m pip install -r requirements.txt
python -m jupyter lab
```

Open the same notebook inside `Exercises/scripts/`. The notebook searches both `Exercises/data/data.mat` and `../data/data.mat` automatically. If your Python environment cannot locate the file, copy it beside the notebook. For answers, see [`Exercises/answers/Anesthesia_EEG_Solutions.ipynb`](Exercises/answers/Anesthesia_EEG_Solutions.ipynb).

## Materials / repository map

```text
README.md                         Workshop overview and setup
requirements.txt                  Pinned core FOOOF dependency
Slides/workshopslides.pptx        Editable revised presentation
Slides/workshopslides.pdf         Presentation PDF
Outline/workshopoutline.pdf       Organizer-facing workshop outline
Exercises/data/data.mat           Small teaching subset (rights check required)
Exercises/scripts/               Participant notebook, exercise brief + smoke test
Exercises/answers/               Solutions notebook + sample result plots
DATA_PROVENANCE.md                Sampling, metadata and licensing limits
CITATIONS.md                     References and publication notes
REVIEW_NOTES.md                  Scientific and code review details
```

## Important limitations

The supplied MATLAB file holds only 10 small traces. It lacks original calibration, actual doses, animal pairing, channel descriptions, and independent confirmation of sampling rate. The notebook follows the prior instructor's **assumption** of 10,000 Hz and uses native signal units; the 50 Hz artifact makes 1–45 Hz a prudent main fit band. This is a **teaching demonstration**, not a direct replication of Colombo et al.'s human EEG study nor a test of consciousness. See [`DATA_PROVENANCE.md`](DATA_PROVENANCE.md).

## Preparation before publishing

- [ ] Obtain the **actual workshop feedback QR image from MiCM**; replace the placeholder on the final slide. The organizer specifically requests it.
- [ ] Confirm that the teaching subset may legally be redistributed; see `DATA_PROVENANCE.md`.
- [ ] Check reuse permissions for third-party figures already in the instructor's original slides; see `CITATIONS.md`.
- [ ] Confirm the sampling rate, channel units, rat identities and actual doses against the source's recording metadata.
- [ ] Test a clean Colab session with the notebook and the uploaded data, then fill the actual GitHub/Colab link in the shared participant materials.

## Citations

Arena & Storm (2018), data: https://doi.org/10.25493/4SPM-V00. Donoghue et al. (2020), FOOOF: https://doi.org/10.1038/s41593-020-00744-x. Additional scientific references in [`CITATIONS.md`](CITATIONS.md).

## Submission to QLS-MiCM

Follow the [QLS-MiCM Workshop Template](https://github.com/QLS-MiCM/Workshop_Template): use its **“Use this template”** command to create a new repository, transfer these files while preserving the `Exercises`, `Slides`, and `Outline` folders, and submit an issue to the **Workshop_Template** issue tracker titled with the workshop name and date for academic review. A reviewer should approve materials before their public release under the QLS-MiCM organization.
