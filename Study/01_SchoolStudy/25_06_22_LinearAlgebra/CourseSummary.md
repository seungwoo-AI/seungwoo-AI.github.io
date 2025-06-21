# CourseSummary.md  
*A structured outline of key Linear-Algebra topics & concepts (per the conversation)*  

---

## 1. Vector Spaces & Subspaces
- Definition of a vector space over a field 𝔽  
- Subspace test (zero vector, closure under addition & scalar-mult)  
- Spanned subspace `Span S`  
- Basis vs. spanning set  
- Dimension

---

## 2. Linear Independence & Basis Construction
- Linear independence / dependence  
- Method: form matrix of vectors → perform RREF → pivot columns ↔ basis  
- Coordinate vectors relative to an **ordered basis**

---

## 3. Row, Column, and Null Spaces
| Space | Definition | Notes |
|-------|------------|-------|
| Row space `Row(A)` | span of row vectors | orthogonal complement of `ker A` |
| Column space `Col(A)` | span of columns | image of the linear map |
| Null space `ker A` | solutions of `A x = 0` | dimension = **nullity** |

### Rank–Nullity Theorem  
`rank A + nullity A = number of columns`

---

## 4. Orthogonality & Complements
- Inner product (dot product in ℝⁿ)  
- Orthogonal complement `W^{⊥}`  
- Relation: `ker A^{⊥} = Row(A)`

---

## 5. Linear Transformations & Matrices
- Matrix representation of a linear map  
- Similarity (`P⁻¹AP`): same map in a new basis  
- Change-of-basis matrices

---

## 6. Eigenvalues, Eigenvectors, and Eigenspaces
- Characteristic polynomial `det(λI − A)`  
- Eigenvalue λ: non-trivial solution of `A v = λ v`  
- Eigenspace `E_λ = { v | A v = λ v }`  
- Constructing matrix `P` from eigenvectors → `P⁻¹AP` diagonal/Jordan (if possible)

---

## 7. Jordan & Rational Canonical Forms
- Motivation: simplest form under similarity  
- Jordan blocks (λ on diagonal, 1’s on super-diagonal)  
- Rational (Frobenius) form for arbitrary fields

---

## 8. Wronskian & Independence of Functions
- Wronskian determinant \( W(f_1,\dots,f_k;x) \)  
- `W(x₀) ≠ 0` ⇒ functions independent on interval  
- Application to linear ODE solution spaces

---

## 9. Determinants & Minors
- Determinant properties  
- Cofactor expansion; minors  
- Role in invertibility (`det A ≠ 0`) and volume interpretation

---

## 10. Rank Estimation Techniques
- Gaussian elimination / RREF  
- Pivot count = rank  
- Connection to number of free variables (nullity)

---

## 11. Projection & Least Squares (preview)
- Projection of a vector onto a subspace  
- Normal equations `AᵀA x = Aᵀb`

---

## 12. Miscellany
- Cayley–Hamilton Theorem: `p_A(A)=0` where `p_A` is the characteristic polynomial  
- Direct sums and complementary subspaces  
- Inner-product spaces vs. normed spaces (brief distinction)

---

**End of CourseSummary.md**
****
