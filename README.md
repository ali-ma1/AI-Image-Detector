# AI-Image-Detector

This project aims to accurately classify images as either AI-generated or real using the CoAtNet-2 architecture. The classifier was trained on a labeled image dataset sourced from a Kaggle competition. It achieved exceptional performance on both validation and test sets.

## Project Overview

This project focuses on deep learning-based binary classification to detect whether an image is AI-generated or real. It utilizes the CoAtNet-2 model, which combines convolutional and self-attention mechanisms for efficient and scalable vision learning.

The dataset includes a large collection of labeled images from a Kaggle-hosted competition. The classifier was trained from scratch using PyTorch with a focus on generalization and performance under realistic image diversity.

## Dataset

- **Source**: Kaggle competition (Real vs AI-generated images)
- **Labels**: Binary (real vs AI-generated)
- **Preprocessing**: Resizing, normalization, and basic augmentations (e.g., random crop and horizontal flip)

## Model

- **Architecture**: CoAtNet-2 (hybrid of convolutional and attention layers)
- **Framework**: PyTorch
- **Loss Function**: CrossEntropyLoss
- **Optimizer**: LAMB (Layer-wise Adaptive Moments optimizer)
- **Learning Rate Scheduler**: CosineAnnealingLR
- **Training Duration**: 15 epochs

## Training Results

| Epoch | Validation Accuracy | Validation Loss |
|-------|---------------------|-----------------|
| 1     | 98.82%              | 0.0631          |
| 5     | 94.13%              | 0.3898          |
| 10    | 99.62%              | 0.0310          |
| 15    | 99.75%              | 0.0223          |

Final evaluation on the test set:

- **Test Accuracy**: 99.76%
- **Test F1 Score**: 0.9976
- **Test Loss**: 0.0216

## Training Notes

- During training, a warning was encountered regarding the order of `optimizer.step()` and `scheduler.step()` in PyTorch. This did not impact the final model performance.
- The model converged steadily, with minor fluctuations in validation accuracy around epochs 3–5, followed by significant improvements afterward.
