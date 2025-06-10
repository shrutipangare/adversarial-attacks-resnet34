# Adversarial Attacks on Deep Learning Models
A comprehensive evaluation of adversarial attack methods on ImageNet-trained neural networks, comparing the robustness of ResNet-34 and DenseNet-121 architectures.

This project explores the vulnerability of deep neural networks to **adversarial attacks** using a set of pixel-wise and patch-based perturbation methods. We evaluate the robustness of two popular image classification models—**ResNet-34** and **DenseNet-121**—against various attacks on a subset of the ImageNet-1K dataset.

## Objective

The goal is to:
- Generate adversarial examples using **FGSM**, **PGD**, **Momentum PGD**, and **Targeted PGD**
- Apply a localized **patch attack**
- Evaluate top-1 and top-5 accuracy on both clean and adversarial data
- Analyze **transferability** of attacks from ResNet-34 to DenseNet-121

## Methods Implemented

### ✅ Pixel-wise Attacks
- **FGSM (Fast Gradient Sign Method)**  
- **PGD (Projected Gradient Descent)**  
- **Momentum PGD (MIM)**  
- **Targeted PGD**

### ✅ Patch-based Attack
- **Localized PGD with 32×32 patch**

### ✅ Evaluation Metrics
- **Top-1 Accuracy**
- **Top-5 Accuracy**
- **L∞ distance** (perturbation constraint)
- **Cross-model Transferability**

##  Sample Results

| Model         | Clean | FGSM | Best Adv | Patch |
|---------------|-------|------|----------|--------|
| **ResNet-34** | 70.4% Top-1 / 94.2% Top-5 | 5.0% / 30.0% | 0.0% / 8.0% | 53.0% / 76.0% |
| **DenseNet-121** | 70.8% / 91.8% | 59.0% / 85.2% | 58.4% / 87.0% | 69.0% / 90.0% |

## Visualizations

<img src="/top1_accuracy_comparison.png" width="600" />
<img src="/top5_accuracy_comparison.png" width="600" />

##  Key Findings

- **ResNet-34** is highly vulnerable to even simple attacks like FGSM.
- **DenseNet-121** shows much better resilience, especially in Top-5 accuracy.
- Localized patch attacks are less destructive than global pixel-wise attacks.
- Adversarial examples often transfer across models, but DenseNet’s architecture dampens the impact.

##  Requirements

- Python 3.8+
- PyTorch
- torchvision
- NumPy, Matplotlib
- tqdm, requests, PIL

Install via:

```bash
pip install -r requirements.txt
