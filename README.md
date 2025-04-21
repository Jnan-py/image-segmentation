# Human Segmentation using PyTorch

This repository contains a deep learning pipeline for human image segmentation using PyTorch. It uses a U-Net architecture with an EfficientNet encoder for binary segmentation of humans in images.

## 📁 Dataset

The dataset used is **Human Segmentation Dataset**, which includes paired image and mask files. A `train.csv` file lists the paths to all image-mask pairs.

Make sure to download the dataset and place the zipped file as:

```
Ground_Truth.zip
Training_Images.zip
```

The script will extract and use it automatically.

## 🧠 Model Architecture

- Model: U-Net
- Encoder: `timm-efficientnet-b5` pretrained on ImageNet
- Loss Functions:
  - Dice Loss
  - BCEWithLogitsLoss
- Optimizer: RMSProp

## 🔧 Data Augmentation

- Resize (320x320)
- Random Horizontal Flip
- Random Vertical Flip
- Random Rotation

Implemented using **Albumentations** library.

## 📦 Requirements

See [`requirements.txt`](./requirements.txt) for all dependencies.

## 🚀 How to Run

1. **Clone the repository:**

   ```bash
   git clone https://github.com/Jnan-py/image-segmentation.git
   cd image-segmentation
   ```

2. **Create and activate a virtual environment (recommended):**

   ```bash
   python -m venv venv
   source venv/bin/activate   # On Windows: venv\Scripts\activate
   ```

3. Ensure that zip files are in the root directory.

4. **Install required dependencies:**

   ```bash
   pip install -r requirements.txt
   ```

## 🖼️ Visualization

The script includes functions to:

- Visualize original images and ground truth masks
- Visualize predicted masks
- Save predicted masks to PNG

## 📌 Notes

- This project uses a custom PyTorch `Dataset` for loading and preprocessing images and masks.
- Training progress is shown using `tqdm`.
- The model is trained for 25 epochs with a batch size of 16.

---

## 📂 File Structure

```
.
├── Ground_Truth.zip
├── Training_Images.zip
├── Image_Segmentation.ipynb
├── Ground_Truth
├── Training_Images
├── README.md
└── requirements.txt
```

## ✨ Sample Output

| Input Image         | Ground Truth Mask  | Predicted Mask     |
| ------------------- | ------------------ | ------------------ |
| ![](sample_img.png) | ![](sample_gt.png) | ![](pred_mask.png) |
