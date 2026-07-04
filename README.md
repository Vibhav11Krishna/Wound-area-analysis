# Wound-area-analysis
# Wound Area Analysis using U-Net (MobileNetV2 Encoder)

## Project Overview
This project implements an advanced semantic segmentation pipeline designed to identify and isolate wound areas from medical images. By utilizing a **MobileNetV2 encoder** paired with a **U-Net decoder**, the model balances high-speed feature extraction with precise spatial reconstruction.

## Pipeline Architecture
The workflow follows a structured path from raw input to final segmentation mask:

Input RGB Image
       ↓
**Preprocessing** (Resizing, Normalization, Augmentation)
       ↓
**MobileNetV2 Encoder** (Deep Feature Extraction)
       ↓
**Skip Connections** (Preserving spatial information from encoder to decoder)
       ↓
**U-Net Decoder** (Feature Reconstruction)
       ↓
**1×1 Convolution + Sigmoid** (Generating pixel-wise probability map)
       ↓
**Binary Segmentation Mask**
       ↓
**Evaluation** (Accuracy, Dice Coefficient, IoU)



## Experimental Results
We conducted performance evaluations across different training durations. The MobileNetV2 backbone provided robust feature extraction, leading to the following improvements:

| Metric | 10 Epochs | 20 Epochs |
| :--- | :--- | :--- |
| **Test Accuracy** | 0.9742 | 0.9804 |
| **Dice Score** | 0.6655 | 0.7746 |
| **IoU Score** | 0.4987 | 0.6321 |

* **Configuration**: Batch size = 1.
* **Analysis**: Doubling the training epochs resulted in a significant increase in the Dice Score ($\approx 16.4\%$) and IoU ($\approx 26.7\%$), confirming that the model effectively learns to distinguish complex wound boundaries from healthy skin.

## How to add your own visualization
To demonstrate your model's 0.77 Dice score, create a comparison figure showing the **Original Image**, **Ground Truth**, and **Predicted Mask**. Add it to this README using this syntax:


