# CourseSummary.md  
*Systematic overview of the three supplied chapters (7 – 9).*

---

## 7 Data Visualization

### 7.1  Core Purposes  
| Goal | Brief Description |
|------|------------------|
| **EDA** | Detect patterns, clusters, outliers. |
| **Error Detection** | Reveal data-entry / sensor faults. |
| **Communication** | Deliver insights visually to non-experts. |

### 7.2  Tufte-Style Design Rules  
| Principle | Action Point |
|-----------|--------------|
| **Maximise Data-Ink** | Strip 3-D, heavy grids, clip-art. |
| **Minimise Lie Factor** | Align visual change with numeric change; set axes properly. |
| **Remove Data-Junk** | Delete decorative clutter and redundant legends. |
| **Clear Scales & Labels** | Axes span data range; units and captions explicit. |
| **Colour for Meaning** | Use palettes for class or magnitude; colour-blind safe. |
| **Repetition for Consistency** | Re-use fonts, hues, layout modules. |

### 7.3  Chart Reference & Tips  
| Chart Type | Good For | Best Practice |
|------------|----------|---------------|
| **Table** | Exact numeric comparison | Align decimals; highlight key rows. |
| **Line / Dot** | Trends vs ordered x | Plot raw dots + fit; CI shading. |
| **Scatter** | Numeric–numeric | Tune dot size & jitter; encode extra dims via colour/size. |
| **Bar** | Categorical counts | Uniform widths; sorted order. |
| **Pie** | Parts-of-whole (< 6) | Direct labels; avoid small slices. |
| **Histogram** | Distribution shape | Reasonable bin width; density option for unequal *n*. |

---

## 8 Machine Learning (Supervised)

### 8.1  Regression  
| Model | Formulation | Loss |
|-------|-------------|------|
| Linear | `y = wᵀx + b` | MSE; closed-form or GD |
| Logistic | `p = σ(wᵀx)` | Cross-entropy |

### 8.2  Multi-class  
- **One-vs-All** — *K* separate logistic models.  
- **Softmax Regression** — `P(y=k|x)=exp(w_kᵀx)/Σ_j exp(w_jᵀx)`.

### 8.3  Naïve Bayes  
Probabilistic classifier:  
`ŷ = argmax_k P(C_k) × ∏_j P(x_j | C_k)`  (conditional independence).  

### 8.4  Further Classifiers  
| Family | Algorithm | Key Point |
|--------|-----------|-----------|
| Distance | **k-NN** | Majority vote of *k* nearest samples. |
| Tree | **Decision Tree** | Greedy impurity split; interpretable. |
| Ensemble | **Random Forest** | Bagging + random features; high accuracy. |
| Margin | **SVM** | Maximum-margin hyperplane; kernel trick. |

---

## 9 Unsupervised Learning & Pattern Discovery

### 9.1  Clustering  
| Method | Essence | Notes |
|--------|---------|-------|
| **k-Means** | Iteratively assign ↔ re-centre | Requires *k*, sensitive to scale/outliers. |
| **Hierarchical** | Build tree of merges or splits | Dendrogram visual, no pre-set *k*. |
| **DBSCAN** | Density-based | Finds arbitrary shapes; rejects noise points. |

### 9.2  Dimensionality Reduction (Review)  
| Technique | Goal | Output |
|-----------|------|--------|
| **PCA** | Max-variance axes | Principal components; scree plot. |
| **t-SNE / UMAP** | Non-linear manifold display | 2-D embedding for visual clusters. |

### 9.3  Association Analysis  
| Algorithm | Purpose | Metrics |
|-----------|---------|---------|
| **Apriori** | Mine frequent itemsets | Support, confidence, lift |
| **FP-Growth** | Tree-based, faster on dense data | Same metrics as above |

### 9.4  Clustering Evaluation  
| Measure | Interpretation |
|---------|----------------|
| **Silhouette** | Cohesion vs separation (-1 … 1). |
| **Davies–Bouldin** | Lower = better cluster separation. |
| **Elbow / Gap** | Heuristics for selecting *k*. |

---

## Key Formula Snapshot  
- Gradient of least-squares `∇w‖b – Aw‖² = –2Aᵀ(b – Aw)`  
- Softmax `softmax(z)_k = exp(z_k)/Σ_j exp(z_j)`  
- Multi-class cross-entropy `J = –Σ_i Σ_k y_ik log p_ik`  
- Naïve Bayes (log form) `log P(C_k)+Σ_j log P(x_j|C_k)`

---
