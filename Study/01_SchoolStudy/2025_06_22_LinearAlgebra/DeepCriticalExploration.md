# DeepCriticalExploration.md  
*Concise Q – A list (score ≥ 80)*  

---

## 1. Orthogonal Complement vs. Row Space
**Q.** Why does  `ker A^{⊥} = Row(A)` hold?  

**A.** If `x ∈ ker A`, then every row vector `r_i` satisfies `r_i · x = 0`.  
Hence `x` is orthogonal to each `r_i` and to their span.  
That span **is** the row-space, so `ker A^{⊥} = Row(A)`.

---

## 2. Why `P⁻¹ A P` Becomes Diagonal / Jordan
**Q.** Given a (generalized) eigenbasis `P`, why does `P⁻¹ A P` turn into a diagonal or Jordan block matrix?  

**A.** For an eigenvector `p_i` we have `A p_i = λ_i p_i` (or `λ_i p_i + p_{i−1}` in a Jordan chain).  
In the new coordinates, each basis vector is merely scaled by `λ_i` (plus a single “1” above the diagonal for a chain), so the matrix shows only diagonal `λ_i` and possible super-diagonal 1’s → diagonal or upper-triangular Jordan form.

---

## 3. Why `P` Is Invertible
**Q.** Even with repeated eigenvalues, why must the eigenvector matrix `P` be invertible?  

**A.** Within one eigenspace we choose a basis, hence the vectors are independent; eigenspaces for distinct eigenvalues intersect only at 0.  
All columns are therefore linearly independent, `det P ≠ 0`, so `P` is invertible.

---

## 4. Wronskian Test Rules
**Q.** Why build a square matrix (Wronskian) with derivatives and take its determinant?  
  Must the determinant vanish for *all* `x` to claim dependence?  

**A.** Differentiating `k − 1` times yields a `k × k` square matrix; its determinant `W(x)` is a single scalar test.  
If `W(x₀) ≠ 0` at *one* point, the functions are independent on that interval (sufficient).  
If the functions are dependent, then `W(x) ≡ 0` for *every* `x` (necessary).

---

## 5. Rank–Nullity Reference Frame
**Q.** Is the Rank–Nullity theorem based on row vectors?  

**A.** No — its dimension count is column-based.  
`rank A` = number of independent **columns** (column-space dimension),  
`nullity A` = `dim ker A`; their sum equals the number of columns `n`.

---

## 6. Meaning of “Spanned Subspace”
**Q.** What exactly is a “spanned” subspace?  

**A.** `Span S = { Σ c_i v_i }`: all linear combinations of vectors in `S`.  
If `Span S = V`, then `S` **spans** `V`.  
If `S` is also linearly independent, it forms a **basis** of `V`.
