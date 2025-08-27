# video-to-cryo-ET-data


# Transfer Learning from Video to Cryo-ET Data

This repository demonstrates how to extract meaningful features from Cryo-ET (Cryo-Electron Tomography) data using pre-trained deep learning models trained on video datasets.

## Task Overview
- Extract features from Cryo-ET data using pre-trained **3D Deep Neural Network (DNN)** models.
- Use **3D-ResNet34** and **VideoMAE** as frozen feature extractors (no fine-tuning required).
- Visualize extracted features in 2D using **t-SNE** and cluster them with **K-Means**.
- Compare feature representations of **3D-ResNet34** and **VideoMAE**.

---

## Requirements
- Python 3.x
- Install required dependencies:
  ```bash
  pip install mrcfile scikit-learn matplotlib

