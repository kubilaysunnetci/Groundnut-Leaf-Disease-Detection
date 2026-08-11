# Deep Learning Model Comparison for 5-Class Image Classification

This repository contains the official MATLAB implementation for training, fine-tuning, and evaluating multiple Convolutional Neural Network (CNN) architectures on a 5-class image dataset. 

The evaluation framework consists of a multi-seed benchmark using an 80/10/10 split followed by a 3-Fold Cross-Validation on the top-performing architecture.

---

## 📌 Key Features

* **Compared Architectures:** Benchmarks 6 different models:
  * `DarkNet-19`
  * `ResNet-18`
  * `InceptionV3`
  * `AlexNet`
  * `SqueezeNet`
  * `Normal-CNN` (Custom baseline architecture)
* **Multi-Seed Benchmark (80/10/10 Split):** Trains and tests each model across three random seeds (`20`, `30`, `40`) to calculate reliable mean and standard deviation metrics.
* **Automated Layer Freezing:** Automatically freezes the bottom 50% of learnable layers in pre-trained models to prevent overfitting and accelerate fine-tuning.
* **Unbiased Model Selection:** Selects the champion model based strictly on **Mean Validation Accuracy** (keeping the Test set reserved strictly for final reporting).
* **3-Fold Cross-Validation:** Re-trains the selected best model from scratch across 3 cross-validation folds with dedicated early-stopping validation partitions.

---

## 📁 Repository Structure

```text
.
├── Data/                          # Root folder for image dataset
│   ├── Class_1/
│   ├── Class_2/
│   ├── Class_3/
│   ├── Class_4/
│   └── Class_5/
├── Results/                       # Output directory (created automatically)
│   └── Networks/                  # Saved .mat trained models (if enabled)
├── main_evaluation.m             # Main MATLAB benchmark & evaluation script
├── README.md                      # Documentation
└── LICENSE                        # License file

Data availability
	The data that support the findings of this study are openly available in Mendeley Data at https://data.mendeley.com/datasets/x6x5jkk873/2. The dataset is described in detail and cited as: Sasmal, B., et al. (2024), "A novel groundnut leaf dataset for detection and classification of groundnut leaf diseases", Data in Brief, 55, 110763.
