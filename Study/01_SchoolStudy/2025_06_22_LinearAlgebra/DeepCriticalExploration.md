# DeepCriticalExploration.md  
*— Concise Q ↔ A list (score ≥ 80) —*

---

## 1. Orthogonal Complement vs. Row Space  
**Q.** Why does \( \ker A^{\perp} = \mathrm{Row}(A) \)?  

**A.** If \(x \in \ker A\), then \(r_i \!\cdot x = 0\) for every row vector \(r_i\).  
Thus \(x\) is orthogonal to every row vector, i.e.\ to their span.  
That span **is** the row-space, hence the orthogonal complement of \(\ker A\) is \(\mathrm{Row}(A)\).

---

## 2. Why \(P^{-1}AP\) Becomes Diagonal / Jordan  
**Q.** Given a (generalized) eigenbasis \(P\), why does \(P^{-1}AP\) turn into a diagonal or Jordan block matrix?  

**A.** For each eigenvector \(p_i\): \(A p_i = \lambda_i p_i\) (or \(\lambda_i p_i + p_{i-1}\) for a Jordan chain).  
In the new coordinates, each basis vector is scaled by \(\lambda_i\) (plus a single “1” above the diagonal in a chain), so the matrix shows only diagonal \(\lambda_i\) and possible super-diagonal 1’s → diagonal or upper-triangular Jordan form.

---

## 3. Why \(P\) Is Invertible  
**Q.** Even with repeated eigenvalues, why must the eigenvector matrix \(P\) be invertible?  

**A.** Within one eigenspace we choose a **basis**, hence vectors are independent; eigenspaces for distinct eigenvalues intersect only at 0.  
Therefore all columns are linearly independent → \(\det P \neq 0\) → \(P\) is invertible.

---

## 4. Wronskian Test Rules  
**Q.** Why use derivatives to build a square matrix (Wronskian) and evaluate its determinant?  
Must the determinant vanish for **all** \(x\) to declare dependence?  

**A.** Differentiating \(k-1\) times yields a \(k \times k\) square matrix; its determinant \(W(x)\) is a single scalar test.  
If \(W(x_0) \neq 0\) at **one** point, the functions are independent on that interval (sufficient).  
If the functions are dependent, then \(W(x)\equiv 0\) for **every** \(x\) (necessary).

---

## 5. Rank–Nullity Reference Frame  
**Q.** Is the Rank–Nullity theorem based on row vectors?  

**A.** It is based on **columns**.  
\(\mathrm{rank}\,A\) = number of independent columns (dimension of the column-space);  
\(\mathrm{nullity}\,A\) = dimension of \(\ker A\).  
Their sum equals the number of columns \(n\).

---

## 6. Meaning of “Spanned Subspace”  
**Q.** What exactly is a “spanned (펼쳐진) subspace”?  

**A.** \(\displaystyle \Span S = \{\sum_i c_i v_i\}\): all linear combinations of vectors in \(S\).  
If \(\Span S = V\), then \(S\) **spans** \(V\).  
If \(S\) also is linearly independent, it forms a **basis** of \(V\).
