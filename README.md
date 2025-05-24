# Multi-Speaker-Speech-Separation


# 🎧 Multi-Speaker Speech Separation using Spatial and Acoustic Audio Features

This project implements a deep learning system for **multi-speaker speech separation** by combining both spatial features (ITD, ILD, DOA) and acoustic features (Mel-spectrogram). The objective is to separate overlapping speech signals recorded via stereo microphones using spatial cues and spectral patterns.

## 🚀 Features

* Spatial feature extraction (ITD, ILD, DOA)
* Mel-spectrogram acoustic feature processing
* Custom PyTorch `Dataset` class to handle stereo audio mixtures
* Model training using **SI-SDR loss**
* Performance evaluation using **SDR, SIR, SAR, STOI** metrics
* Preprocessing pipeline with optional wavelet denoising

## 🧠 Model Overview

The model architecture is built on a hybrid deep learning system combining:

* **Superformer**: For temporal modeling of spectrograms
* **SpaRSep**: For spatial reasoning from binaural cues

These are fused to predict masks that are applied to the mixture signal to reconstruct the separated sources.

## 📁 Dataset

The dataset used in this project is a synthetic multi-speaker mixture dataset generated with spatial annotations. You can download the dataset from the link below:

📦 **[Download Dataset](https://www.kaggle.com/datasets/iamsainikhil/multispeaker-stereo-mixtures)**

The dataset contains:

* Stereo audio mixtures (`.wav`)
* Individual source signals
* Ground truth DOA, ILD, ITD values
* Sampling rate: 16kHz

## 📚 Installation

Clone the repository and install dependencies:

```bash
git clone https://github.com/yourusername/multi-speaker-separation.git
cd multi-speaker-separation
pip install -r requirements.txt
```

## 📝 Usage

```bash
# Train the model
python train.py --config configs/default.yaml

# Evaluate the model
python evaluate.py --checkpoint checkpoints/best_model.pth
```

## 🧪 Evaluation Metrics

* SDR (Signal-to-Distortion Ratio)
* SIR (Signal-to-Interference Ratio)
* SAR (Signal-to-Artifacts Ratio)
* STOI (Short-Time Objective Intelligibility)

These metrics provide a comprehensive assessment of the quality of separation.

## 📊 System Diagram

The pipeline consists of:

1. **Preprocessing** stereo signals
2. **Extracting spatial and acoustic features**
3. **Training a hybrid neural network**
4. **Reconstructing separated audio sources**
5. **Evaluating separation performance**

## 🙋 Authors

* Charan

## 📄 License

This project is licensed under the MIT License.
