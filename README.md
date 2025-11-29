# Deepfake Video Detection Using ResNeXt + LSTM
---

## 🚀 Project Overview

This project introduces a **hybrid deep learning model** that detects deepfake videos by analyzing both spatial and temporal inconsistencies. It integrates:

* **ResNeXt-50** for frame‑level spatial feature extraction.
* **LSTM** for temporal sequence modeling and anomaly detection.

The goal is to create a reliable and high‑recall system to identify manipulated videos, particularly those difficult to distinguish by the human eye.

---

## 🔍 Motivation

Deepfake technology is rapidly evolving, making video manipulation more convincing than ever. These forgeries pose serious threats, including misinformation, identity abuse, and digital fraud. This project aims to introduce a model that:

* Detects fake videos with high reliability
* Minimizes false negatives through a **Security‑First approach**
* Uses modern deep learning architectures optimized with transfer learning

---

## 🧠 Model Architecture

The hybrid model operates in two primary phases:

### 1. **ResNeXt‑50 (CNN Feature Extractor)**

* Processes each video frame independently
* Extracts **2048‑dimensional spatial feature vectors**
* Captures texture anomalies, blending artifacts, lighting inconsistencies
* Uses **ImageNet pretrained weights** for transfer learning

### 2. **LSTM (Sequence Learner)**

* Reads ordered ResNeXt feature vectors
* Detects temporal inconsistencies such as:

  * Irregular blinking
  * Unnatural lip movements
  * Timing distortions
* Outputs final classification: **Real vs Fake**

---

## 📊 Experimental Results

**Dataset:** Celeb‑DF (v2)

| Metric           | Value      |
| ---------------- | ---------- |
| Accuracy         | **78.33%** |
| Recall (Fake)    | **90.00%** |
| Precision (Fake) | **73.00%** |
| F1‑Score (Fake)  | **81.00%** |

### 🔐 Interpretation

The model follows a **"Security First / Paranoid"** detection strategy:

* ⚠️ May raise **false positives** (flagging real videos as fake)
* ✔️ Extremely low **false negatives** (rarely misses a fake video)

### Confusion Matrix Summary

* Correctly detected **27 / 30** fake videos.

---

## 🛠️ Technologies Used

| Technology   | Purpose                                 |
| ------------ | --------------------------------------- |
| Python 3.10  | Main programming language               |
| PyTorch      | Deep learning framework                 |
| ResNeXt‑50   | CNN architecture for feature extraction |
| LSTM         | Sequence modeling                       |
| OpenCV       | Frame extraction and preprocessing      |
| MTCNN        | Face detection & cropping               |
| Google Colab | GPU‑based training environment          |

---

## ⚙️ Installation & Usage

Follow these steps to run the project locally or in Google Colab.

### 1. Install Required Packages

```bash
pip install torch torchvision opencv-python mtcnn matplotlib seaborn scikit-learn
```

### 2. Prepare the Dataset

Create a folder structure:

```
Mini_Dataset/
├── Real/
└── Fake/
```

Place unprocessed videos inside.

### 3. Preprocessing

The notebook will:

* Read each video
* Detect and crop faces using **MTCNN**
* Save frames into `Processed_Dataset/`

### 4. Training

Run the training cells inside `Deepfake_Detection.ipynb`.
The model will train using:

* ResNeXt‑based frame embedding
* LSTM classification

### 5. Testing

After training, run test cells to generate:

* Prediction scores
* Confusion matrix
* Performance metrics

---

## Future Improvements

* Add **audio‑based deepfake detection** for multimodal analysis
* Reduce false positives using larger datasets (e.g., **DFDC**)
* Implement **real‑time mobile integration**
* Explore **Vision Transformers (ViT)** or **ConvLSTM** architectures

---

## 📄 License

This project is developed for academic and educational purposes.
The dataset used (Celeb‑DF) is subject to its own licensing terms.

---

## 📬 Contact

For inquiries or improvements, feel free to reach out:

* **Eda Vural** – Software Engineering, OSTİM Technical University

---

This README is prepared based on the analysis of your project and is ready for direct use on GitHub or any documentation platform.
