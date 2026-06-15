# ASVspoof 2019 LA — Feature × Architecture Experiments

Anti-spoofing countermeasure experiments on the ASVspoof 2019 Logical Access dataset.
Trains and evaluates 13 (feature extractor × neural network) combinations, reporting EER and min-tDCF.

## Experiments

| # | Feature | Model |
|---|---------|-------|
| 1–3 | MFCC | CNN / Res2Net / LCNN |
| 4–6 | LFCC | CNN / Res2Net / LCNN |
| 7–9 | CQCC | CNN / Res2Net / LCNN |
| 10–12 | SincConv (learnable front-end) | CNN / Res2Net / LCNN |
| 13 | Raw waveform | RawNet2 |

## Structure

```
notebooks/   — main experiment notebook (run on Kaggle/Colab with GPU)
docs/        — reference notes on features, architectures, and preprocessing options
report/      — Persian-language project report (LaTeX source + compiled PDF)
```

## Quick Start

Open `notebooks/asvspoof_experiments.ipynb` on [Kaggle](https://kaggle.com) with the
[ASVspoof 2019 dataset](https://www.kaggle.com/datasets/awsaf49/asvpoof-2019-dataset) attached,
or on Google Colab after mounting the data manually.

The first cell installs all dependencies. Set flags in **Section 1 (Configuration)** to
enable/disable optional preprocessing (VAD, RawBoost, reverb, denoising).

## Metrics

- **EER** — Equal Error Rate (%)
- **min-tDCF** — normalized minimum tandem Detection Cost Function (CM-only, simplified)

## Requirements

```
librosa soundfile scipy numpy pandas matplotlib scikit-learn tensorflow tqdm
```
