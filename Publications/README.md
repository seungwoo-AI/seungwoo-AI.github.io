# 📄 Publications

This directory contains peer-reviewed papers accepted to academic conferences and journals in AI and computer vision.

---

## 📝 Publications List

1. **YOLO Channel Fusion for Grayscale Data**  
   *IPIU 2025 – 37th Workshop on Image Processing and Image Understanding*  
   🔗 [PDF](./001_ipiu2025/paper.pdf) · [Details](./001_ipiu2025/README.md)

---

## 📁 Folder Structure

- `001_ipiu2025/`  
  YOLOv11 performance enhancement via grayscale-to-RGB fusion using Edge and Texture channels. Includes paper PDF and detailed summary.

---

## ⚙️ Add New Publication (GPT Prompt Template)

To add a new peer-reviewed paper, upload the paper PDF and paste the following prompt into ChatGPT:

````markdown
Based on the uploaded paper PDF, create a new subfolder inside the `publications/` directory.

1. Name the folder using the format: `00X_keyword`, for example: `002_cvpr2026`.
2. Inside the folder, generate a `README.md` that includes the following:
   - Paper title
   - Conference/journal name
   - Presentation or acceptance date
   - Co-authors and your contribution (e.g., First Author)
   - Abstract (extracted or summarized from the paper)
   - Key performance results or improvements (if available)
   - Relative PDF path: ./00X_keyword/paper.pdf
3. Update the main `publications/README.md` by adding this paper to the "Publications List" section using relative links.
4. Also add one line to the "Folder Structure" section describing the folder contents.
5. If the abstract is too long, summarize it. If the paper doesn’t include an abstract, it can be omitted.

I'll upload the PDF now — please complete the steps above based on the paper.
