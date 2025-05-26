# YOLO 학습 성능 향상을 위한 1채널 데이터의 3채널 합성 연구  
*Improving YOLO Performance via 3-Channel Fusion of Single-Channel Input*  
*IPIU 2025 – 37th Workshop on Image Processing and Image Understanding*  
📅 February 5–7, 2025  
👨‍💻 Authors: Seungwoo Lee*, Seunghyun Yoo, Jongwoong Seo, Hwapyung Baek, Yonghwa Chung  
🔍 Contribution: First Author  
📄 [Download Paper (PDF)](./paper.pdf)

---

## 🧠 Abstract

This study addresses the challenge of object detection in grayscale-only environments such as smart farms.  
We propose a novel 3-channel input synthesis method for YOLOv11 by combining:

- **B channel**: Grayscale input  
- **G channel**: Edge-enhanced image generated from Depth Anything  
- **R channel**: Texture-enhanced image using CLAHE  

This fusion significantly improves generalization and reduces texture dependency.

---

## 📊 Key Results

| Metric     | Baseline (Grayscale only) | Proposed Fusion | Improvement |
|------------|----------------------------|------------------|-------------|
| AP50       | 84.5%                      | **90.8%**        | +6.3%       |
| F1-score   | 80.4%                      | **86.6%**        | +6.2%       |

- Best performance achieved with channel mapping: Gray → B, Edge → G, Texture → R  
- Maintains inference speed while improving accuracy on unseen pig farm datasets

---

## 🧪 Method Overview

- **Edge image (G)**: From Depth Anything v2 → surface normal (Z) → invert  
- **Texture image (R)**: CLAHE applied with 9×9 grid and clip limit = 2  
- **Grayscale (B)**: Fixed assignment based on feature map analysis

---

## 🖼️ Poster

> Presented at IPIU 2025 Workshop

📄 [View Poster (PDF)](./poster.pdf)

---

## 📎 Files

- `paper.pdf`: Full camera-ready paper  
- `poster.pdf`: Conference presentation poster  
- `acceptance.png`: Acceptance screenshot (optional)

---

## 🧾 Citation

```bibtex
@inproceedings{lee2025yolo,
  title     = {YOLO 학습 성능 향상을 위한 1채널 데이터의 3채널 합성 연구},
  author    = {Seungwoo Lee and Seunghyun Yoo and Jongwoong Seo and Hwapyung Baek and Yonghwa Chung},
  booktitle = {IPIU 2025 - 37th Workshop on Image Processing and Image Understanding},
  year      = {2025}
}
