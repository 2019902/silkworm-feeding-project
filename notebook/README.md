# Notebooks
This directory contains the Jupyter notebooks used for interactive exploration, model training, evaluation and visualization in the Silkworm Feeding Classification project.

Notebook link: https://colab.research.google.com/drive/1DHWKm0laMCYVhewcoq3PdYTbzSSEo1Dm?usp=sharing

## Contents

- **`feeding_silkworm_Ruggeri_Venneri.ipynb`**
- **`feeding_silkworm_Ruggeri_Venneri.py`**  
  An end-to-end Colab notebook that shows how to:
  1. Mount Google Drive and prepare the dataset  
  2. Define the `SilkwormDataset` and data loaders  
  3. Load and fine-tune a pre-trained MobileNetV2 for binary feeding vs. no-feeding classification  
  4. Apply early stopping and plot training/validation loss & accuracy curves  
  5. Perform global L₁ pruning at different sparsity levels (0%, 10%, 20%)  
  6. Plot “Prune Amount vs. Validation Accuracy” and interpret the trade-off
