# Film Impurity Removal - Python ML Pipeline

> **Privacy notice:** This repository is a public placeholder with a reduced, high-level
> description of the work for public presentation. The full source code remains
> private as this is an ongoing freelancing engagement. I am happy to walk through the
> architecture and code in a private session upon request - feel free to reach out at
> pr@paulruesing.de.

---

## What this project is

A Python machine learning pipeline for **automated detection of physical impurities**,
developed end-to-end as a freelance project for an imaging technology client.

The pipeline covers the full model lifecycle - from training data generation through
model training and validation to deployment-ready export - and feeds directly into a
companion native Rust application that handles real-time inference and inpainting.

---

## Key ingredients

### Data preparation
- **Synthetic data augmentation** - training data is generated programmatically from
  clean source material, eliminating the need for manual annotation

### Model training & validation
- **Deep learning segmentation** - multiple models trained for joint pixel-wise artefact detection
- **Structured model selection** - checkpoints are evaluated systematically; results
  are exported to CSV for comparison and selection

### Export & deployment
- **ONNX export** - models are exported to ONNX format for cross-platform consumption
  by the Rust inference backend
- **CoreML export** - on macOS, models are additionally converted to CoreML
  `.mlpackage` format for Apple Silicon runtime optimisation
- **Optional quantisation** - post-training quantisation supported for reduced model
  size and faster inference

---

## Stack

| Layer | Technology |
|---|---|
| Language | Python |
| ML framework | PyTorch |
| Export | ONNX, CoreML (coremltools, macOS) |
| Data / utilities | Pandas, Pillow, NumPy |
| Environment | Conda |

---

## Companion repository

The exported models are consumed by a companion native Rust desktop application
(also private) that handles real-time inference, adaptive filtering, and deterministic
inpainting. A public placeholder for that repository is available separately.

---

## Authors

Paul Rüsing - [pr@paulruesing.de](mailto:pr@paulruesing.de) - sole contributor  
Developed for an imaging technology client (ongoing engagement).

## License

All rights reserved by the client. Source code not included in this repository.
