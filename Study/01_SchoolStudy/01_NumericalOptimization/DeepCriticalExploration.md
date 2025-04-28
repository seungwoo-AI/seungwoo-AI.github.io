# DeepCriticalExploration — Numerical Optimization Theory  

> A distilled notebook of the **most critical & research-level questions** (≥ 80 pts) we discussed, together with the explorations, proofs, geometric pictures, and take-home insights that emerged.

---

## 1. Key Questions (≥ 80 pts) & Findings  

| # | Critical Question (user-raised) | Core Exploration | Mathematical Insight | Visual / Geometric Intuition | Final Insight |
|---|---------------------------------|------------------|----------------------|------------------------------|---------------|
| **Q1** | **Gradient Descent(GD)의 수렴성은 어떤 조건에서 보장되는가?** :contentReference[oaicite:0]{index=0} | Examined *L-smooth + µ-strongly-convex* setup; used $$\|\nabla f(x)-\nabla f(y)\|\le L\|x-y\|$$ and $$f(x_{k})-f^{\*}\le(1-\tfrac{µ}{L})^{k}(f(x_{0})-f^{\*})$$. | Convergence rate $$\mathcal O((1-\frac{µ}{L})^{k})$$; proves linear rate when $$0<\eta<2/L$$. | Level-set ellipses shrink homothetically toward the minimizer. | Choice of **step-size** must respect curvature upper bound *(L)* to guarantee descent. |
| **Q2** | **왜 GD의 탐색 방향은 $$-\nabla f(x)$$ 인가?** :contentReference[oaicite:1]{index=1}&#8203;:contentReference[oaicite:2]{index=2} | Linked Taylor 1st-order decrease $$f(x+\Delta)\approx f(x)-\eta\|\nabla f(x)\|^{2}$$. | $$-\nabla f(x)$$ is steepest descent in Euclidean norm; minimizes directional derivative. | Picture the tangent plane—negative gradient points straight “downhill.” | Optimal in first-order sense; other norms give pre-conditioned directions. |
| **Q3** | **Batch GD vs SGD vs Newton: 수렴 속도 차이를 수식으로 비교하면?** :contentReference[oaicite:3]{index=3} | Derived rates: GD linear, SGD sub-linear $$\mathcal O(1/\sqrt{k})$$, Newton quadratic near optimum. | Used expectation bounds for SGD variance term. | Error curve slopes: Newton shoots vertically once close, GD slopes constant, SGD plateaus slowly. | Algorithm choice trades data pass cost vs accuracy. |
| **Q4** | **Momentum과 Nesterov-Accelerated Gradient(NAG)의 근본 차이는?** :contentReference[oaicite:4]{index=4}&#8203;:contentReference[oaicite:5]{index=5} | Unrolled update equations; NAG looks one step ahead giving extra corrective term. | Momentum: $$v_{k+1}=βv_{k}+∇f(x_{k})$$. NAG: $$v_{k+1}=βv_{k}+∇f(x_{k}+βv_{k})$$. | Velocity vector overshoots; NAG “anticipates” curvature. | NAG often converges faster on ravines. |
| **Q5** | **Hessian으로 최소/최대/saddle 판별 방법?** :contentReference[oaicite:6]{index=6}&#8203;:contentReference[oaicite:7]{index=7} | Wrote eigen-analysis: positive-definite ⇒ local min, negative-definite ⇒ local max, indefinite ⇒ saddle. | Sylvester criteria for 2-D; general PD test via Cholesky. | Contour map bends upward/downward along eigen-axes. | Hessian guides second-order methods & curvature-aware step sizes. |
| **Q6** | **Newton’s Method와 GD 비교 (수렴 속도·계산 비용)?** :contentReference[oaicite:8]{index=8}&#8203;:contentReference[oaicite:9]{index=9} | Derived Newton update $$x_{k+1}=x_{k}-H^{-1}\nabla f$$; quadratic rate vs linear. | Cost per step $$\mathcal O(n^{3})$$ for Hessian solve. | Newton “jumps” directly to bottom in quadratic bowl illustration. | Use when dimension moderate or Hessian structure exploitable. |
| **Q7** | **Lipschitz Continuity가 왜 중요하며 어느 알고리즘에 쓰이는가?** :contentReference[oaicite:10]{index=10}&#8203;:contentReference[oaicite:11]{index=11} | Showed it bounds function growth ⇒ guarantees Armijo/Wolfe line search success. | Guarantees $$|f(x)-f(y)|≤L\|x-y\|$$ ⇒ safe step-size upper bound. | Graph curvature bounded by L; prevents “cliffs.” | Key in proofs of GD, Nesterov, Adam convergence. |
| **Q8** | **Backtracking Line Search가 필요한 이유와 알고리즘 흐름?** :contentReference[oaicite:12]{index=12} | Walked through Armijo rule, shrink factor ρ. | Ensures sufficient decrease without knowing L; finds η in finitely many steps. | Visual: progressively shorter jump until touches descent “wedge.” | Makes GD robust to unknown curvature. |
| **Q9** | **Adam Optimizer 수식과 Momentum 방식과의 차이?** :contentReference[oaicite:13]{index=13}&#8203;:contentReference[oaicite:14]{index=14} | Adam keeps first *m* & second *v* moments with bias-correction; update $$\hat m/(√{\hat v}+ε)$$. | Combines RMSProp scaling with Momentum smoothing; adapts per-coordinate step. | Elliptical step sizes shrink in directions with high variance. | Strong on sparse gradients but can diverge without weight decay. |

---

## 2. Cross-Cutting Mathematical Themes  

1. **Taylor Expansion bridges derivatives to step-size choice**; GD is first-order approximation of the minimum path :contentReference[oaicite:15]{index=15}&#8203;:contentReference[oaicite:16]{index=16}.  
2. **Convergence-rate hierarchy:** *Quadratic (Newton) > Linear (GD w/ strong convexity) > Sub-linear (SGD)*.  
3. **Condition numbers (κ = L/µ)** explain why ill-conditioned problems slow GD but not Hessian-scaled methods.  
4. **Variance reduction (SVRG, Adam bias-correction)** tackles stochastic noise, trading memory for stability.  

---

## 3. Visual Intuition Cheatsheet  

- **Gradient Field:** arrows pointing to minima; negative gradient gives steepest descent.  
- **Curvature Ellipses:** eigen-axes of Hessian—long axis = slow direction; Newton rescales to circles.  
- **Loss Landscape Slices:** GD zig-zags in narrow valleys; Momentum smooths; NAG “peeks” ahead.  
- **Line-Search Wedge:** plot of f(x+ηd); Armijo condition is the linear upper bound line.  

*(Sketch these by hand or with matplotlib for presentation.)*

---

## 4. Final Insights & Next Steps  

- Mastering **assumptions (L-smooth, µ-strong)** is as crucial as coding the algorithm.  
- Build **intuition first, proofs second, implementation last**—each layer reinforces the other.  
- Upcoming deep dives: **convex duality proofs, quasi-Newton BFGS derivation, saddle-escape in non-convex nets.**  

---

**License:** CC BY-NC.  
Created 2025-04-29, consolidating all ≥ 80 pt numerical-optimization explorations to date.
