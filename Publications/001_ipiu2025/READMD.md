# YOLO Channel Fusion for Grayscale Data  
*IPIU 2025 – 37th Workshop on Image Processing and Image Understanding*  
📅 February 5–7, 2025  
👨‍💻 Authors: Seungwoo Lee*, Seunghyun Yoo, Jongwoong Seo, Hwapyung Baek, Yonghwa Chung  
🔍 Contribution: First Author  
📄 [Download Paper (PDF)](./paper.pdf)

---

## 🧠 Abstract

This study addresses the challenge of applying object detection models to grayscale-only environments such as smart farms. The proposed method enhances YOLOv11 performance by converting single-channel grayscale data into a 3-channel format by assigning:

- **B**: Grayscale image  
- **G**: Depth-based edge image (from *Depth Anything*)  
- **R**: CLAHE-enhanced texture image  

The fused input significantly reduces over-reliance on texture and improves detection in unseen environments without increasing inference time.

---

## 📊 Key Results

- **Baseline YOLOv11 (Grayscale only)**:  
  - AP50: 84.5%  
  - F1-score: 80.4%

- **Proposed Fusion (Gray + Edge + Texture)**:  
  - AP50: 90.8% (+6.3%)  
  - F1-score: 86.6% (+6.2%)

---

## 🖼️ Visual Highlights

- Edge-enhanced depth input allows clearer boundary detection  
- B-channel shows the highest feature separability  
- Feature maps from Layer 3/4 confirm robust generalization

---

## 📎 Resources

- `paper.pdf`: Full manuscript  
- `acceptance.png`: Screenshot of paper acceptance (optional)
