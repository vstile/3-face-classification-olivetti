# 3-face-classification-olivetti

Short description: Classical face classification on the Olivetti dataset with a clean, reproducible baseline. Loads the AT&T/ORL faces, builds a simple pipeline, and reports accuracy and per-class metrics. Useful for teaching, quick benchmarking, and extending to stronger feature extractors.

---

## Overview

This repository provides a compact, end to end baseline for multi class face classification on the Olivetti Faces dataset. The goal is clarity and reproducibility, not leaderboard scores. It is suitable as a teaching example or as a starting point for rapid prototyping.

**Key points**
- Dataset: AT&T ORL (Olivetti) Faces, 400 images, 40 identities, 10 images per subject, 64×64 grayscale  
  Source: University of Cambridge Computer Laboratory  
  https://www.cl.cam.ac.uk/research/dtg/attarchive/facedatabase.html
- Split: 75% train, 25% test with a fixed random seed
- Features: raw flattened pixels (no alignment, no augmentation) for maximal transparency
- Model: `RandomForestClassifier` baseline
- Metrics: accuracy, macro precision, macro recall, macro F1, confusion matrix

**Why this repo**
- Minimal code and clear structure
- Reproducible results with fixed seeds
- Easy to replace the feature stage or the classifier to test improvements

---

## Results

On the 25% held out test split:

- Accuracy ≈ **88%**
- Macro precision ≈ **0.88**
- Macro recall ≈ **0.90**
- Macro F1 ≈ **0.87**

Typical errors arise from low contrast faces and subtle illumination changes. These results form a reasonable reference for future enhancements such as alignment, PCA, HOG, or CNN features.

---

The work and its intermediate findings were presented during PwC “Tech Wednesday” on 20 March 2024, which prompted active discussion among colleagues and helped steer subsequent experiments. A detailed account is provided in the author’s PhD thesis for the industrial doctoral programme in Big Data and Artificial Intelligence.

## Quickstart

### 1) Environment
```bash
python -m venv .venv
source .venv/bin/activate   # Windows: .venv\Scripts\activate
pip install -r requirements.txt
```

---
Privacy and reuse policy

* This repository contains code and model. No personal data are included.
* **Reuse is permitted provided that you cite the author and this work.**
* Recommended license: **Creative Commons Attribution 4.0 International (CC BY 4.0)**. You are free to share and adapt the material for any purpose, even commercially, as long as appropriate credit is given, a link to the license is provided, and any changes are indicated.

Short attribution text you can include in derivative works:

```
This material reuses data and methods from this Ph.D. Dissertation:
Stile, V. (2026). “AI-generated Deepfakes: Detection and Bias Analysis”. Ph.D. dissertation, Universitas Mercatorum, Roma, Italy.
© 2026 Vittorio Stile - Licensed under CC BY 4.0.
```
