# Flower classification model with Transfer Learning

**Title:** Flower Classification using Transfer Learning (MobileNetV2)  
**Author:** OBIBI Oghenofegor Gregory  
**Contact:** oghenofegor.obibi@gmail.com  
**Date:** June 2, 2026  

---

A deep learning project that leverages transfer learning with a pre-trained **MobileNetV2** architecture to accurately classify different species of flowers. The model is built using TensorFlow and Keras, utilizing advanced data augmentation and preprocessing pipelines to achieve high generalization performance on the validation dataset.

---

## 🚀 Features & Workflow

* **Data Pipeline:** Automated image loading, resizing ($224 \times 224$), and batching using TensorFlow's `image_dataset_from_directory`.
* **Transfer Learning:** Utilizing **MobileNetV2** weights pre-trained on ImageNet as a frozen feature extractor, appended with custom dense classification layers.
* **Optimization:** Compiled with the Adam optimizer and tracking sparse categorical accuracy.
* **Evaluation:** Monitored training performance using loss/accuracy metrics.

---

## 📊 Model Architecture

The network utilizes a feature extraction pipeline followed by a fully connected classification head:

1. **Input Layer:** Accepts $224 \times 224 \times 3$ RGB images.
2. **Base Model:** Pre-trained **MobileNetV2** (Weights: `ImageNet`, include_top=`False`).
3. **Global Average Pooling:** Reduces the spatial dimensions of the feature maps.
4. **Output Layer:** Dense layer with a Softmax/Linear activation corresponding to the total number of flower target classes.

---

## 🛠️ Repository & Dataset Structure

The tree below shows the required file structure for the notebook to run successfully. The `image_dataset_from_directory()` function automatically infers target labels from the explicit subdirectory names inside `train/` and `validation/`.

```text
├── Flower_model.ipynb       # Main training and evaluation notebook
└── flower_dataset/          # Root dataset directory
    ├── train/               # Dataset used for model training
    │   ├── class_a/         # Images belonging to Class A (e.g., roses)
    │   └── class_b/         # Images belonging to Class B (e.g., sunflowers)
    └── validation/          # Dataset used for model validation
        ├── class_a/         # Images belonging to Class A
        └── class_b/         # Images belonging to Class B
