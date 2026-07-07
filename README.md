
# Wound Area Analysis using  Deep Learning Model U-Net (MobileNetV2 Encoder)

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
| **Dice Score** | 0.6655 | 0.7446 |
| **IoU Score** | 0.4987 | 0.5921 |

|**Precision**|  0.84542   |
|**Recall**|   0.6374   |
|**F1 Score**|   0.7497 |

* **Configuration**: Batch size = 1.
* **Analysis**: Doubling the training epochs resulted in a significant increase in the Dice Score ($\approx 16.4\%$) and IoU ($\approx 26.7\%$), confirming that the model effectively learns to distinguish complex wound boundaries from healthy skin.

![Original vs Predicted](https://github.com/Vibhav11Krishna/Wound-area-analysis/blob/main/output%20image.png)

[Dataset Availability](https://www.kaggle.com/datasets/rollas/wound-segmentation-dataset)


