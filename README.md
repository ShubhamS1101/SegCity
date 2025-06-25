# SegCity

**SegCity** is a semantic segmentation pipeline designed for self-driving applications on Indian roads. It leverages polygon-based annotations to train a TensorFlow model using transfer learning, enabling pixel-level scene understanding for autonomous navigation.

## Project Highlights

- Transfer learning-based semantic segmentation using a pretrained SegFormer model
- Fine-tuned on Indian road scenes from real-world driving datasets
- Processes polygonal JSON annotations and label masks
- Handles class imbalance by selecting top-N samples for rare classes (e.g., animals, tunnels, parking)
- Built with TensorFlow, Shapely, OpenCV, and PIL

## Pipeline Overview

1. **Data Loading**  
   Loads input images along with their corresponding segmentation masks and polygon annotations in JSON format.

2. **Polygon to Mask Conversion**  
   Converts JSON-encoded polygon coordinates into pixel-wise mask images suitable for model training.

3. **Rare Class Detection**  
   Computes the area coverage of rare semantic classes (like `animal`, `parking`, etc.).  
   Selects the top-N samples with the highest label coverage to handle class imbalance.

4. **Model Training**  
   Uses transfer learning with the [NVIDIA SegFormer-B0 model](https://huggingface.co/nvidia/segformer-b0-finetuned-ade-512-512) pretrained on ADE20K.  
   Fine-tunes the model on Indian road scenes using the prepared masks.

## Tech Stack

- Python
- TensorFlow
- Hugging Face Transformers
- Shapely (for polygon area computation)
- OpenCV, PIL (image processing)
- Matplotlib (visualization)

## Dataset

This project is based on data from the IIT Guwahati AI Overnight Hackathon 2024.  
Kaggle Competition: [Dataset Link](https://www.kaggle.com/competitions/iitg-ai-overnight-hackathon-2024/data)

Dataset structure follows a Cityscapes-style format:

