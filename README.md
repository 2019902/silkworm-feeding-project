# silkworm-feeding-project
# RUGGERI RICCARDO, VENNERI ROBERTA

# Silkworm Feeding Classification

A PyTorch project to classify silkworm images into “feeding” vs. “no feeding,” optimize the model for edge deployment via global L₁ pruning, and evaluate the performance–efficiency trade-off.

---

## Repository Structure

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
