# Flower classification model with Transfer Learning

**Title:** Flower Classification using Transfer Learning (MobileNetV2)  
**Author:** OBIBI Oghenofegor Gregory  
**Contact:** oghenofegor.obibi@gmail.com  
**Date:** June 2, 2026  

---

A deep learning project that leverages transfer learning with a pre-trained **MobileNetV2** architecture to accurately classify different species of flowers. The model is built using TensorFlow and Keras, utilizing advanced data augmentation and preprocessing pipelines to achieve high generalization performance on the validation dataset.

---

## Dataset
The model is trained and evaluated on a dataset containing five classes of flowers. Due to large file size limitations on GitHub, the source data can be downloaded directly from the following cloud mirror:

📥 **[Download Dataset from Google Drive](https://drive.google.com/file/d/1xVOWC9OcVPHaA4gWG_ZKHsCSPMbPCJjb/view?usp=drive_link)**

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

## Dataset Structure

The project expects the training images to be organized in a standard directory structure where the parent directory contains subfolders named after each target class. The classification function automatically infers the class labels directly from these folder names.

Organize your dataset folder as follows:

```text
flowers/
├── daisy/
│   ├── image_0001.jpg
│   ├── image_0002.jpg
│   └── ...
├── dandelion/
│   ├── image_0001.jpg
│   ├── image_0002.jpg
│   └── ...
├── roses/
│   ├── image_0001.jpg
│   ├── image_0002.jpg
│   └── ...
├── sunflowers/
│   ├── image_0001.jpg
│   ├── image_0002.jpg
│   └── ...
└── tulips/
    ├── image_0001.jpg
    ├── image_0002.jpg
    └── ...
