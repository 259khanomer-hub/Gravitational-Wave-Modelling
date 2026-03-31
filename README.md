# Gravitational Wave Matched Filtering Notebooks

This repository contains two Jupyter notebooks that demonstrate simplified gravitational-wave data analysis using **public LIGO data** and **PyCBC**. The notebooks focus on recovering signals from real detector data using matched filtering.

These notebooks are **pedagogical demonstrations**, not full LIGO–Virgo–KAGRA (LVK) pipeline analyses.

---

# Notebook 1 — GW170817 Matched Filter (Manual Template Placement)

**Purpose**
Recover the binary neutron star event **GW170817** from real detector data using a simplified matched-filter pipeline.

**Key steps implemented**
1. Download real strain data from the **LIGO Hanford detector (H1)** using GWOSC.
2. Convert the data into a PyCBC time series.
3. Estimate the detector **power spectral density (PSD)**.
4. Generate a **theoretical inspiral waveform template** using `TaylorT4`.
5. Explicitly place the template onto the detector's **absolute GPS time grid**.
6. Compute the matched-filter signal-to-noise ratio (SNR).
7. Plot:
   - raw detector strain
   - detector PSD
   - theoretical waveform
   - matched-filter SNR

**Expected result**
The notebook typically recovers a strong signal with

SNR ≈ 30–50

The recovered time may differ from the catalog coalescence time by roughly a second because:

- the waveform parameters are approximate
- a simplified waveform model is used
- only one detector is analyzed
- full LVK calibration and parameter estimation are not included

This notebook demonstrates the **core principle of matched filtering** used in gravitational-wave searches.

---

# Notebook 2 — Baseline Matched Filter Pipeline

**Purpose**
Provide a minimal matched-filter pipeline for gravitational-wave data using:

- PyCBC
- GWOSC public data
- basic waveform models

This notebook serves as a **reference implementation** showing the core components required to detect compact binary coalescence signals.

**Steps**
1. Import scientific libraries
2. Define event parameters
3. Download detector strain data
4. Estimate the detector PSD
5. Generate waveform templates
6. Perform matched filtering
7. Inspect the recovered SNR peak

This notebook focuses on **clarity and reproducibility** rather than reproducing the full LVK analysis pipeline.

---

# Requirements

Python packages used:

numpy  
scipy  
matplotlib  
gwpy  
pycbc  
astropy  
h5py  
pandas  

Install core dependencies:

pip install pycbc gwpy

---

# Notes

They  notebooks illustrate:

- how real interferometer strain data is accessed
- how detector noise is characterized
- how theoretical waveforms are compared to real data
- how matched filtering recovers weak signals buried in noise

They demonstrate the underlying physics and data-analysis concepts, not reproducing offical LVK results

---

# References

LIGO Scientific Collaboration & Virgo Collaboration  
GW170817: Observation of Gravitational Waves from a Binary Neutron Star Inspiral  
Phys. Rev. Lett. 119, 161101 (2017)

Public data provided by:

Gravitational Wave Open Science Center (GWOSC)  
https://www.gw-openscience.org
