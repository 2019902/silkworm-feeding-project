# RUGGERI RICCARDO, VENNERI ROBERTA

# Efficient Computer Vision Models for Silkworm Feeding Prediction and Habitat Analysis

Efficient silkworm rearing is crucial for sustainable silk production, and it relies on accurate monitoring of feeding conditions. Traditional observation methods are labor-intensive and prone to human error, which makes automation a valid alternative. 
This project explores the use of lightweight neural network architectures for automating two key tasks:
- **Binary Classification** ('feeding' vs. 'no feeding'): The objective is to automatically determine whether or not worms need to be fed
- **Unsupervised Segmentation** : To distinguish between worms, leaves and background, an unsupervised **clustering** approach was implemented

## Methods & Implementation Details

### Binary Classification

The classification task is handled using a **pretrained MobileNet_v2** architecture, chosen for its lightweight design and good performance. The training process includes:

- **Early stopping**, to prevent overfitting by monitoring validation loss.
- **Pruning**, to reduce the size of the final model and optimize inference efficiency.

### Unsupervised Segmentation

For segmentation, the approach is entirely unsupervised. A custom model based on **MobileViT** — a hybrid architecture that combines CNNs with lightweight Transformer blocks was implemented.

After feature extraction, **clustering algorithms** are applied to separate the image into silkworms, mulberry leaves, and background:

- **K-Means**, for its simplicity and speed.
- **Gaussian Mixture Models (GMM)**, to capture more complex cluster distributions.

## Dataset

The dataset used for this project is provided in the `/data` folder.  
Please refer to `/data/README.md` for detailed instructions on how to download and prepare the data.

---
## Code Structure
The code is divided into modules to ensure clarity and modularity:
- **Imports**: packages needed to run the notebook
- **Globals**: global variables and parameters
- **Utils**: reusable support functions
- **Data**: Loading, preprocessing and augmentation of data
- **Network**: definition of network architectures (MobileNetV2 for classification, MobileViT for clustering)
- **Train**: training cycle for classification
- **Evaluation**: evaluation of results using quantitative metrics and qualitative visualisations

## How to run the project

This project is designed to run in Google Colab. To execute it properly, follow these steps in order:

1. **Install section**: Installs dependencies and downloads the dataset using `gdown`.
2. **Setup**: Run the following sections sequentially: `Imports`, `Globals`, `Utils`, and `Data`.
3. **Network section**: You'll find two alternative models:
   - `MobileNet_v2` for **binary classification**
   - `MobileViT` for **unsupervised segmentation**

You can choose which task to run first — **classification or segmentation** — as they are completely independent.  
However, to avoid potential conflicts, it's recommended **not to run both model cells at the same time**. Run only one model at a time.

4. **Training & Evaluation**:
   - If you're working on classification, continue with the `Train` section and then run the `Pruning Evaluation` cell.
   - If you're working on segmentation, you can skip training and go directly to the `Clustering Evaluation` cell.

If you want to run both tasks consecutively, that's totally fine — just make sure you **run only one model definition at a time**, in either order.

This sequential approach ensures both tasks can be executed independently without conflicts.

## Repository Structure

```markdown
silkworm-feeding-project/
│
├── README.md
│
├── data/
│ ├──README.md
│
├── notebooks/
│ └── feeding_classification.ipynb
│     Interactive Colab notebook for training & pruning
│
├── src/
│ ├── dataset.py
│ ├── mobilenet.py
│ ├── utils.py
│ ├── train.py
│ └── evaluate.py
│
├── models/
│ ├── README.md
│
├── reports/
│ ├── presentation.pdf
