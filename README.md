# SegCity

**SegCity** is a semantic segmentation pipeline tailored for self-driving applications on Indian roads. It uses polygon-based annotations to train a TensorFlow model through transfer learning, enabling pixel-level scene understanding for autonomous vehicles.

## 🚗 Project Highlights

- ✅ Transfer learning-based semantic segmentation
- 🇮🇳 Trained on Indian road scenes
- 🧠 Uses polygonal JSON annotations and label masks
- 📉 Class imbalance handling by selecting top-N rare class samples
- 🧰 TensorFlow + Shapely + OpenCV + PIL-based data processing

## 🧩 Pipeline Overview

1. **Data Loading**
   - Loads image paths, corresponding masks, and JSON polygon annotations

2. **Polygon to Mask Processing**
   - Converts JSON-encoded polygon annotations into training masks

3. **Rare Class Detection**
   - Calculates area coverage of rare classes like `animal`, `parking`
   - Selects top-N samples with highest label percentage to balance the dataset

4. **Model Training**
   - Uses transfer learning to fine-tune a pre-trained segmentation model

5. **Evaluation**
   - Visualizes and evaluates model predictions on Indian road images

## 🛠️ Tech Stack

- Python, TensorFlow
- Shapely (for polygon processing)
- OpenCV, PIL, Matplotlib
- Structured dataset with JSON polygon annotations

## 📁 Dataset : https://www.kaggle.com/competitions/iitg-ai-overnight-hackathon-2024/data

 
