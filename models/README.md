## Models

### MobileNetV2 for Feeding Classification  
We use the MobileNetV2 architecture, pre-trained on ImageNet and fine-tuned on our silkworm feeding dataset. MobileNetV2 employs depthwise separable convolutions and inverted residual blocks with linear bottlenecks, providing a very lightweight model suitable for deployment on resource-constrained devices. In our setup, we replace the final fully-connected layer with a `Linear(1280, 2)` head to perform binary classification (feeding vs. no-feeding).

### Global L₁ Pruning  
To further reduce model size and improve inference efficiency, we apply global unstructured L₁ pruning to both convolutional and linear weights. We experiment with different pruning ratios (0 %, 10 %, 20 %) and measure the drop in validation accuracy. After pruning, we fine-tune the remaining weights for a few epochs at a reduced learning rate to recover any lost performance.

### MobileViT for Feature Extraction  
We also implement a lightweight Vision Transformer block (MobileViT) for unsupervised segmentation. MobileViT combines local convolutions with global self-attention in small patch embeddings, allowing us to extract per-pixel feature vectors that are clustered (KMeans / GMM) to produce pseudo-segmentation masks.
