# CNN-from-Scratch  
**Numerical Optimization (AI Cyber Security) • Final Course Project**

*Graduate School Application Portfolio*

**Author**: Seungwoo Lee, Korea University Sejong  
**Course**: Numerical Optimization (Final replacement project)  
**Date**: June 2025  
**Contact**: rainup4632@gmail.com  

---

## 📘 Project Context

This work was completed as the **final substitute deliverable** for the Numerical Optimization course. Its purpose is to demonstrate—

1. Deep mathematical understanding of gradient-based learning (deriving backpropagation by hand).  
2. Software craftsmanship by implementing a working CNN **from first principles** (no high-level deep-learning frameworks).  
3. Experimental rigor through controlled evaluation on both a custom small-scale dataset and the MNIST benchmark.

---

## 🔬 Objectives

- **Implement** every component of a Convolutional Neural Network—  
  convolutional layers, pooling layers, activation functions (Sigmoid, ReLU, Softmax + cross-entropy), and the SGD optimizer—**using only NumPy**.  
- **Train and evaluate** on:  
  1. A custom 6×6 handwritten-digit dataset (classes “1”, “2”, “3”; 96 samples)  
  2. The standard MNIST dataset (≈ 90 % test accuracy)  
- **Prove** the mathematical equivalence between:  
  - “Flatten → Fully Connected” and  
  - “2×2-Conv → 1×1 output”  
- **Analyze** convergence behavior under different optimizers and initialization schemes.

---

## 📊 Key Results

- **Custom 6×6 dataset**  
  – **100 % training accuracy** achieved with NumPy-only CNN + SGD.  
- **MNIST benchmark**  
  – **≈ 90 % test accuracy**, confirming portability of the implementation.  
- **Optimizer comparison**  
  – SGD vs. Adam vs. RMSprop: Adam converged fastest with lowest variance.  
- **Xavier initialization**  
  – Preserves activation variance across layers, preventing vanishing/exploding gradients.  
- **Layer-design proof**  
  – Formal derivation showing “2×2-Conv → 1×1” produces identical outputs to “Flatten → FC” for small feature maps.

---

## 🗂 Repository Contents

001_cnn-from-scratch/
├── Final Project.pdf # Full written report (theory, code architecture, experiments)
└── README.md # Project summary for portfolio


---

## ⚙️ Technical Highlights

- **Layer implementations** (NumPy only):  
  - **Conv2D**, **MaxPool2D**, **Sigmoid**, **ReLU**, **Softmax + Cross-Entropy**  
- **Optimizers from scratch**:  
  - **SGD**, **RMSprop**, **Adam**  
- **Design proof**:  
  - Equivalence of “Flatten→FC” and “2×2-Conv→1×1”  
- **Training protocol**:  
  - Full-batch training, fixed random seeds, rigorous hyperparameter controls

---

## 🔮 Future Directions

- Add **data augmentation**, **batch normalization**, and **dropout** to guard against overfitting on small datasets.  
- Scale to larger vision tasks (e.g., CIFAR-10) with performance optimization (Cython/Numba/CuPy).  
- Explore advanced optimizers (Adagrad, Nesterov Momentum) and regularization techniques.

---

## 🔍 Further Reading

1. **Code Repository** (NumPy-only CNN implementation) →  
   [https://github.com/seungwoo-AI/cnn-from-scratch
](https://github.com/seungwoo-AI/cnn-from-scratch)

2. **Project Portfolio Page** (screenshots & high-level summary) →  
   [https://github.com/seungwoo-AI/seungwoo-AI.github.io/tree/main/Projects/cnn-from-scratch](https://github.com/seungwoo-AI/seungwoo-AI.github.io/tree/main/Projects/001_cnn-from-scratch)

3. **Full 9-page Project Report (PDF)** (derivations & ablations) →  
   [https://github.com/seungwoo-AI/seungwoo-AI.github.io/blob/main/Projects/cnn-from-scratch/Final%20Project_2025.pdf](https://github.com/seungwoo-AI/seungwoo-AI.github.io/blob/main/Projects/001_cnn-from-scratch/Final%20Project.pdf)

---

## 📜 License

All code in the accompanying GitHub repository is released under the **MIT License**.  
