# Terranet50 Hackathon

This repository contains my notebook code, trained model, and `submission.csv` results for a Kaggle-based semantic segmentation competition organized by Google Developers Group, Prayagraj and sponsored by TensorFlow Prayagraj.

## Competition Overview

**Challenge:**  
Segment terrain of interest from RGB images of off-road environments, using semantic segmentation.  
You are provided with training images and their grayscale masks indicating terrain vs background, and the test set masks are withheld for leaderboard evaluation. Submission masks must be binary and encoded via Run-Length Encoding (RLE).

- **Evaluation Metric:** Mean Intersection over Union (IoU)
- **Leaderboard:** Public and Private; final ranking is based on the private leaderboard

## Problem Context

Off-road segmentation is critical for autonomous navigation and robotics—where terrain types, lighting, and textures are highly variable and less structured than urban scenes. The main challenges include:

- Wide variability in terrain appearance, lighting, and textures
- Imbalanced terrain/background pixel distribution
- Generalization to unseen environments

## My Approach

### 1. Data Preparation & Preprocessing

- Converted provided grayscale masks to binary masks using thresholding.
- Applied data augmentation (such as flipping, rotation, or color jittering) to build model generalization.

### 2. Model Architecture


- I chose U-Net with a ResNet50 encoder backbone for its proven effectiveness in semantic segmentation. The model was implemented using TensorFlow/Keras.

### 3. Training Strategy

- Used weighted loss (e.g., Dice, BCE, or combination) to handle class imbalance.
- Employed early stopping and validation IoU metric to monitor overfitting.

### 4. Prediction & Submission

- Predicted masks were thresholded to obtain binary outputs.
- Converted binary masks to RLE using provided scripts, and generated `submission.csv` per competition guidelines.

### 5. Results

- The best model achieved a **mean IoU score of 0.6116** on the competition leaderboard.

## Files included

- `notebook.ipynb`: Contains all code for data loading, preprocessing, model training, evaluation, and mask-to-RLE conversion.
- `final_model.keras`: Trained model weights for reproducibility.
- `submission.csv`: Final RLE-encoded binary mask predictions for the test set.
---

### Try it yourself!
Clone the repo and run the notebook to reproduce results or improve the segmentation performance further.
