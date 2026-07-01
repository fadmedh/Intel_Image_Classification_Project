# Image Classification: Custom CNN (From Scratch) vs. ResNet50

This repository contains a comprehensive, end-to-end Deep Learning project for multi-class Image Classification (6 classes). The core objective of this project was to establish a solid baseline by designing, troubleshooting, and optimizing a custom Convolutional Neural Network (CNN) from scratch, and then evaluating the performance boost achieved by leveraging Transfer Learning with a state-of-the-art pretrained architecture (**ResNet50**).

## 📊 Dataset Summary
- **Train Images:** 12,632
- **Validation Images:** 1,402
- **Test Images:** 3,000
- **Number of Classes:** 6

## 🛠️ Performance Comparison

| Model | Parameters | Test Accuracy | Test Loss |
|--- |--- |--- |--- |
| **Custom CNN (From Scratch)** | ~1.5M - 5M | 89.03% | 0.3572 |
| **ResNet50 (Transfer Learning)** | ~23M+ | 92.3%+ | 0.2396 |

## 🚀 Optimization Steps Taken

* **Hardware Acceleration:** Successfully diagnosed a hardware bottleneck, transitioning the training pipeline from CPU to a **T4 GPU** runtime, which dramatically slashed the epoch step time from **28 minutes to ~400ms**.
* **Architecture Tuning:** Optimized the custom CNN's parameter efficiency by inserting critical `MaxPooling2D` layers prior to flattening and downsizing the bottleneck layer to `Dense(128)`. This strategic reduction in parameters significantly reduced computational overhead while mitigating overfitting.
* **Overfitting Mitigation & Regularization:** Effectively handled potential overfitting by implementing aggressive **Data Augmentation** (rotation, width/height shifts, zoom, and horizontal flips) alongside a **Dropout (0.5)** layer.
* **Transfer Learning Integration:** Utilized **ResNet50** with frozen base weights and native `preprocess_input` scaling, accelerating convergence and boosting the final validation metrics right from the very first epoch.

## 💻 How to Run

1. Open the repository on GitHub.
2. Click on the **"Open in Colab"** button at the top of the notebook.
3. Make sure to change your runtime to **T4 GPU** (`Runtime` -> `Change runtime type` -> `T4 GPU`).
4. Run all cells to replicate the results!

## 📜 License
This project is licensed under the MIT License - see the LICENSE file for details.
