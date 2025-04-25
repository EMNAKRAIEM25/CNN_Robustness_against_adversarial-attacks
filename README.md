# 🛡️ Robustness Against Adversarial Attacks with CNN and ResNet

This project explores the vulnerability of deep learning models to adversarial attacks and implements multiple defense mechanisms to enhance robustness. The simulations are performed using both a **custom CNN built from scratch** and a **pre-trained ResNet18** model on the **CIFAR-10** dataset.

All simulations are centralized in `initial.py`.

## 📁 Repository Structure

- `data/`: Contains the **CIFAR-10** dataset.
- `real_samples/`: Real-world images for evaluation on ResNet and adversarial scenarios.
- `adversarial_samples/`: Adversarial versions of test images (`frog.png`, `avion.png`, `avion1.png`, `chat.png`, `chien.jpg`, `swatch.png`, `voiture.png`).
- `FGSM_adversarial_samples/`: Adversarial images generated using the **FGSM** method.
- `pgd_adversarial_samples/`: Samples generated using the **Projected Gradient Descent (PGD)** attack.
- `bim_adversarial_samples/`: Adversarial samples generated with the **Basic Iterative Method (BIM)**.
- `gan_adversarial_images/`: Images after applying **GAN-based adversarial attack** on the real images.


## 🧠 Models Used

- **Custom CNN**: Trained from scratch on CIFAR-10 and evaluated against various attacks.
- **Pre-trained ResNet18**: Used for benchmarking and tested under similar adversarial conditions.

## 🏋️ Model Checkpoints

- `model_cifar10.pth`: Initial CNN trained on CIFAR-10.
- `adversarially_trained_model.pth`: CNN retrained using adversarial examples (adversarial training).
- `adversarially_trained_model_with_masking.pth`: CNN with **gradient masking** applied.
- `adversarially_trained_model_with_defenses.pth`: CNN with the full suite of **defense mechanisms**.
- `model2_weights.pth`: Weights for **ResNet18**.
- `resnet18_adversarial_trained_with_defenses.pth`: ResNet18 after adversarial training and **combined defenses**.

## 🧪 Attacks Implemented

- **FGSM (Fast Gradient Sign Method)**
- **PGD (Projected Gradient Descent)**
- **BIM (Basic Iterative Method)**
- **GAN-based Adversarial Examples**
- **DeepFool Attack**


## 🛡️ Defenses Implemented

A **combined pipeline** was created to increase robustness:

- **Feature Squeezing**
- **JPEG Compression**
- **Total Variation Denoising (TVD)**
- **Randomized Smoothing**
- **Clipping & Saturation**
- **Gaussian Blur**

Each defense is applied sequentially to the input image, and results are averaged to obtain the final defended image.

## 📊 Results

Performance before and after applying attacks and defenses are visualized through saved images and summarized in result tables inside the report (IEEE format).

## 🚀 How to Run

```bash
# Setup your environment
pip install -r requirements.txt

# Run the simulation
python initial.py
```

