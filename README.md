<h1 align="center">AI-Gen-AI — GANs on MNIST</h1>
<p align="center">
  Generating handwritten digits using Generative Adversarial Networks
</p>



![Python](https://img.shields.io/badge/Python-3.9+-blue.svg)
![TensorFlow](https://img.shields.io/badge/TensorFlow-2.x-orange.svg)
![Status](https://img.shields.io/badge/Status-Completed-success.svg)

A simple implementation of a **Generative Adversarial Network (GAN)** using TensorFlow to generate handwritten digits similar to the MNIST dataset.

---

## Objective
The objective of this assignment is to implement a simple GAN using TensorFlow and the MNIST dataset to generate synthetic handwritten digit images.

---

## What is a GAN?
A Generative Adversarial Network consists of two neural networks:

### Generator
- Takes random noise as input
- Produces synthetic images
- Goal: fool the discriminator

### Discriminator
- Receives real and fake images
- Classifies them as real (1) or fake (0)
- Goal: correctly detect fake images

Both networks compete in a **minimax game**.

---

## Architecture

### Generator
- Dense
- Batch Normalization
- LeakyReLU
- Conv2DTranspose
- Output: 28×28 grayscale image (Tanh)

### Discriminator
- Conv2D
- LeakyReLU
- Dropout
- Flatten
- Dense (Sigmoid)

---

## Training Details
- Dataset: MNIST
- Normalization: [-1, 1]
- Loss: Binary Cross-Entropy
- Optimizer: Adam (lr = 0.0002, β1 = 0.5)
- Epochs: 20

---

## Loss Curve

<img width="691" height="470" alt="image" src="https://github.com/user-attachments/assets/7e0d8f83-9e1a-481a-92dc-bbe380a53de1" />

**Observation:**
- Generator loss stabilizes around 0.75–0.82
- Discriminator loss stabilizes around 1.28–1.33
- Indicates balanced adversarial training

---

## Generated Digits

<img width="329" height="368" alt="image" src="https://github.com/user-attachments/assets/c5fbc005-bb59-46fc-a6a8-3d4626c46d4c" />
<img width="329" height="368" alt="image" src="https://github.com/user-attachments/assets/a349d7d8-7e8c-4cf7-91dc-7f38703680b9" />
<img width="329" height="368" alt="image" src="https://github.com/user-attachments/assets/249d82fe-ef6a-4146-a43d-b0c42852425c" />
<img width="329" height="368" alt="image" src="https://github.com/user-attachments/assets/72817198-e767-4333-8d73-664a4623a7db" />

**Observation:**
- Early epochs: noisy shapes
- Later epochs: clearer digits
- Generator improves realism over time

---

## Challenges Faced
- Training instability in GANs
- Fluctuating loss values
- Balancing generator and discriminator

---

## Conclusion
The GAN successfully generated handwritten digits similar to the MNIST dataset.  
The adversarial training helped the generator improve progressively across epochs.

---
