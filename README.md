# Deep Learning for Out-of-Distribution Digit Recognition

This project addresses the Out-of-Distribution (OOD) detection problem using deep learning on the MNIST dataset. It combines a convolutional neural network (CNN) with clustering-based outlier detection in embedding space to classify known digits and reject unknown or unexpected inputs.

## 🧠 Approach Summary

- **CNN Feature Extractor**: Learns compact representations of digit images.
- **Embedding Space (128D)**: Designed for tight intra-class clustering.
- **Clustering-Based OOD Detection**:
  - Apply K-means (k=1) per class after training.
  - Use the 90th percentile distance to define class boundaries.
  - During inference, embeddings outside all cluster boundaries are classified as **unknown**.

- **Data Augmentation**: Digit-aware transformations (e.g., smart rotation, blur, affine).
- **Two-Phase Training**: Classification followed by clustering-based thresholding.

## 📊 Results

- **Accuracy on MNIST (in-distribution)**: 94.85%
- **Accuracy on OOD data (CIFAR-10, Fashion-MNIST)**: 96.95%
- **Overall Accuracy**: 95.19%
- **t-SNE Embedding**: Shows tight digit clusters and separate OOD groups.
