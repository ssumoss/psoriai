# PsoriAI – Skin Disease Image Classification

PsoriAI is an AI-based image classification project developed to classify skin diseases using deep learning and transfer learning techniques.

The project uses a pre-trained **EfficientNet-B0** model to classify skin images into five different categories. The model is trained using PyTorch, and its performance is evaluated with various classification metrics.

## Project Overview

The main objective of this project is to develop a deep learning model that can recognize different skin disease categories from images.

The workflow includes:
- Dataset preparation and preprocessing
- Image transformation and augmentation
- Transfer learning with EfficientNet-B0
- Model training and fine-tuning
- Performance evaluation and visualization

## Dataset

The dataset consists of **3,000 images** distributed across five classes.

| Skin Disease Class | Total Images | Training | Testing |
|---|---:|---:|---:|
| Eczema Photos | 600 | 420 | 180 |
| Lichen Planus | 600 | 420 | 180 |
| Rose Disease (`gül_hast`) | 600 | 420 | 180 |
| Fungal Infection (`mantar`) | 600 | 420 | 180 |
| Psoriasis (`sedef`) | 600 | 420 | 180 |
| **Total** | **3,000** | **2,100** | **900** |

The dataset is split into:
- 70% Training
- 30% Testing

A random state of 42 is used during dataset preparation.

## Technologies & Libraries

- Python
- PyTorch
- Torchvision
- NumPy
- Pandas
- Scikit-learn
- Matplotlib
- Seaborn
- Google Colab

## Model Architecture

The project uses **EfficientNet-B0**, a pre-trained convolutional neural network architecture with ImageNet weights.

Transfer learning is applied in two stages:

**1. Feature Extraction**
- Pre-trained model weights are frozen.
- The classifier layer is replaced for 5-class classification.
- Dropout (0.2) is applied.
- Adam optimizer is used with a learning rate of 0.001.
- Training is performed for 25 epochs.

**2. Full Fine-Tuning**
- All model layers are unfrozen.
- The entire network is fine-tuned.
- Adam optimizer is used with a learning rate of 0.00001.
- Additional training is performed for 10 epochs.

**Loss Function:** CrossEntropyLoss

## Image Preprocessing

Images are resized to 256 pixels and cropped to 224 × 224.

Training transformations:
- Random Crop
- Random Horizontal Flip
- Tensor Conversion
- ImageNet Normalization

Testing transformations:
- Center Crop
- Tensor Conversion
- ImageNet Normalization

Batch Size: 32

## Model Evaluation

The model is evaluated using the test dataset.

Evaluation metrics include:
- Accuracy
- Precision
- Recall
- F1-Score
- Confusion Matrix
- Class-wise Accuracy
- Multi-class ROC Curve and AUC

Matplotlib and Seaborn are used to visualize model performance.

## Project Structure

```text
psoriai/
│
├── veriseti_600.ipynb
├── README.md
└── .gitignore
```

The notebook includes dataset preparation, preprocessing, model training, fine-tuning and evaluation stages.

## How to Run

1. Open the notebook using Google Colab.
2. Mount your Google Drive.
3. Upload or connect the dataset to your Google Drive.
4. Update the dataset path in the notebook if necessary.
5. Run the notebook cells sequentially.

Required dataset path in the notebook:

```python
dataset_path = "/content/drive/MyDrive/dernet4"
```

## Disclaimer

PsoriAI is an educational and research-oriented project. It is not intended to provide medical diagnoses or replace professional medical advice.

