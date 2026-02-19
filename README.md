# Multi-Modal Social Behaviour Analysis

This repository contains the codebase for the **Multi-Modal Social Behaviour Analysis** project at the **Georgian Artificial Intelligence Association (GAIA)**. Under the supervision of **Dr. Philipp Müller** and PhD candidate **Beso Mikaberidze**, our team is exploring behavioral personalization using high-fidelity multi-modal datasets.

## Project Overview

The project focuses on predicting and analyzing social behavior - specifically centered on **personalization** - in dyadic and group interactions. We utilize the datasets provided by the [MultiMediate Challenge](https://multimediate-challenge.org/), which involve expert-novice dynamics across diverse cultural and linguistic backgrounds.

### Datasets Description

We utilize three primary corpora from the MultiMediate series:

* **MPIIGroupInteraction:** A dataset focused on group dynamics (MultiMediate '21-'25), used for tasks like eye contact detection and bodily behavior recognition.
* **NoXi (NOvice eXpert Interaction):** A large-scale multilingual corpus of screen-mediated dyadic interactions. It features "experts" and "novices" discussing various topics, recorded in France, England, and Germany. It includes rich annotations for engagement and high-dimensional audio-visual features.
* **NoXi+J:** An expansion of the NoXi protocol into East Asia, featuring sessions recorded in Ishikawa, Japan, with Japanese and Chinese speakers. This dataset is critical for analyzing cross-cultural behavioral differences and personalization.

### Data Access

To obtain the data, you must follow the official MultiMediate procedures:

1. Visit the [MultiMediate Dataset Page](https://multimediate-challenge.org/Dataset/).
2. Download the relevant End User License Agreement (EULA).
3. Contact the dataset owners to request access:
* **MPIIGroupInteraction:** Victor Oei (`victor.oei@vis.uni-stuttgart.de`)
* **NoXi:** Daksitha Withanage Don (`noxi@hcai.eu`)
* **NoXi+J:** Marius Funk (`noxi+j@hcai.eu`)

## Features & Streams

The datasets provide the following multi-modal streams:

* **Audio:** eGeMaps v2 (openSMILE), W2v-BERT 2.0 (1024-dim), and XLM-RoBERTa (768-dim) embeddings.
* **Video:** OpenFace2 landmarks, OpenPose (139-dim: body [x, y, confidence] + 2x hands [x, y]), and CLIP (512-dim) visual embeddings.
* **Text:** Audio transcripts with start/end timestamps and confidence scores.
* **Annotations:** Continuous 25Hz frame-wise engagement scores (for Train/Val sets).

## Environment Setup

This project uses **Python 3.14**. Use the following instructions to set up the dedicated virtual environment and install necessary dependencies.

### 1. Create the Virtual Environment

```bash
# Create the environment with the Python 3.14
python3.14 -m venv MutliModalSocialAnalysisBehaviour_venv

# Activate the environment
source MutliModalSocialAnalysisBehaviour_venv/bin/activate  # On Linux/macOS
.\MutliModalSocialAnalysisBehaviour_venv\Scripts\activate   # On Windows
```

### 2. Install Dependencies

Once the environment is active, install the required packages for data handling and feature processing.

```bash
# Upgrade pip to the latest version
pip install --upgrade pip

# Install core data science and ML libraries
pip install numpy pandas matplotlib scipy tqdm torch torchvision torchaudio transformers

# Install DISCOVER tool (Required for reading .stream and .stream~ files)
pip install git+https://github.com/hcmlab/discover
```

> **Note for Windows Users:** To use the **NOVA** tool for manual session annotation and visualization, please refer to the [NOVA repository](https://github.com/hcmlab/nova).

## Repository Structure (Might Change)

```text
├── data/                                    # Dataset root (gitignored)
│   ├── NoXi/
│   ├── NoXi+J/
│   └── MPII/
├── MutliModalSocialAnalysisBehaviour_venv/  # Python 3.14 Venv
├── notebooks/                               # Data exploration and analysis
├── README.md
└── src/                                     # Source code for prediction models
```

## 👥 Contributors

* **Research Team:** Lado Turmanidze, Luka Javakhisvhili, Mariam Gadelia, Keso Chikhladze
* **Supervisors:** Dr. Philipp Müller, Beso Mikaberidze
* **Institution:** Georgian Artificial Intelligence Association (GAIA)
