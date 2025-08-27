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

## Problem Statement

Your task involves taking important features from cryo-ET data using a pre-trained 3D DNN model. Even though the model was trained on different types of data, that's okay because you're only interested in extracting the features, not making them better.

Please use 3D-ResNet34 in this [code repo](https://github.com/kenshohara/video-classification-3d-cnn-pytorch/tree/master) as the model, and get the pre-trained weights (resnet-34-kinetics-cpu.pth) from this [link](https://drive.google.com/drive/folders/1zvl89AgFAApbH0At-gMuZSeQB_LpNP-M). The cryo-ET data can be downloaded [here](https://drive.google.com/file/d/1UFOmHnLXnYo6JH3wlwqcfFcvmuoaIoR0/view?usp=sharing). You need to install the package mrcfile (e.g., pip install mrcfile) and use x = mrcfile.open(‘tomotarget10.mrc’) to read a file. Then the 3D data can be accessed using x.data. 

It's important to know that you can't directly use the original 3D-ResNet34 meant for video classification with our cryo-ET data because their shapes don't match. You'll need to make reasonable adjustments to make them work together. Afterward, take these features and show them in a 2D way using methods like t-SNE for dimension reduction. Then, use K-Means to group the 2D data points into different clusters. Please annotate the corresponding tomotarget id (e.g., 101 for tomotarget101.mrc) near each point. You don't need a GPU for this task since it doesn't involve training the model.

Then please replace the 3D-ResNet model with pre-trained VideoMAE and do the same thing. We don’t need to finetune the [VideoMAE](https://github.com/MCG-NJU/VideoMAE) model or apply any masking on input. Just use the frozen VideoMAE model as a feature extractor for the input subtomograms. Compare the t-SNE features of 3D-ResNet and VideoMAE. 


