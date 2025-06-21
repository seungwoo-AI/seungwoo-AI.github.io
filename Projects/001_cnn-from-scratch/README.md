# CNN-from-Scratch: Final Project Report

> **Graduate School Portfolio**  
> A self-implemented Convolutional Neural Network (CNN) from first principles, using only NumPy, for classifying handwritten digits.

---

## 📖 Project Overview

- **Course**: Numerical Optimization (Final Project)  
- **Objective**:  
  1. Implement every component of a CNN—convolution, activation, pooling, backpropagation and SGD optimizer—**without** any deep-learning framework.  
  2. Train and evaluate on a custom **6×6 handwritten digit** dataset (classes “1”, “2”, “3”, 96 samples total).  
  3. Demonstrate mathematical understanding by deriving backpropagation formulas and proving the equivalence of “Flatten→FC” vs. “2×2-Conv→1×1” layers.  
  4. Validate portability by transferring the same code to MNIST (achieving ≈90% accuracy).

---

## 🚀 Key Results

- **100% training accuracy** on the 6×6 digit dataset.  
- Verified **signal‐preserving Xavier initialization** (𝒩(0, 1/fan_in)) stabilized training.  
- Proved **“2×2 Conv → 1×1 output”** is mathematically identical to **“Flatten → Fully-Connected”** for small feature maps.  
- Successfully applied the same pure-NumPy CNN to MNIST, achieving **≈90% test accuracy**.  

---

## 📄 Report PDF

You can download the full project report here (includes theory derivations, code architecture, experiments, graphs and future work):

[Final Project Report (PDF)](./Final Project.pdf)

---

## 🔗 Code Repository

The complete implementation is available on GitHub:

> **seungwoo-AI / cnn-from-scratch**  
> https://github.com/seungwoo-AI/cnn-from-scratch

---

## 📂 Repository Structure

