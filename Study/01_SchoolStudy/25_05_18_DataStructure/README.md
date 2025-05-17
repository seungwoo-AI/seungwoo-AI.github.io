# Data Structure

## 📘 Project: Inversion Count with Advanced Data Structures

This project was developed as part of a university **Data Structures** course assignment.  
While the assignment simply required solving [BOJ Problem 1517 - Bubble Sort](https://www.acmicpc.net/problem/1517),  
I used it as an opportunity to study inversion counting more deeply and organize my understanding of the topic.

This repository documents both the **core concepts** I learned while solving the problem, and the **deeper questions and explorations** that emerged during the process.

---

## 📌 Problem Summary

> 🔗 [BOJ Problem 1517 - Bubble Sort](https://www.acmicpc.net/problem/1517)  
> Count the number of swaps needed to sort an array using bubble sort.  
> Equivalent to counting all inversion pairs:  
> \((i < j) \land A[i] > A[j]\)

- Naive solution: \(O(N^2)\) → not feasible for large N
- Optimized solution: \(O(N \log N)\) using **Fenwick Tree + Coordinate Compression**

---

## 📂 Files

| File | Description |
|------|-------------|
| `README.md` | This project overview |
| `summary.md` | Organized study of inversion count algorithms and key data structures |
| `DeepCriticalExploration.md` | Deeper questions, explorations, and insights during problem solving |
| `solution_fenwick.java` | Clean Java implementation of optimized inversion count |

---

## 🧠 Techniques Explored

- ✅ **Fenwick Tree (Binary Indexed Tree)**  
  Efficient prefix sum and frequency counting in \(O(\log N)\)

- 🧩 **Coordinate Compression**  
  Remap large/sparse values to compact ranks to enable tree-based indexing

- 🔁 **Right-to-left traversal**  
  For each element, count smaller elements that appeared later

- ⚖️ **Comparative Analysis**  
  Discussed trade-offs with Segment Tree and Merge Sort approaches

---

## 💻 Sample Implementation Highlight

```java
fenwick.update(rank, 1);             // Mark current element as seen
inversionCount += fenwick.query(rank - 1); // Count smaller elements seen so far
```

---

## ✅ Outcome

- Solved the problem with an \(O(N \log N)\) algorithm
- Reviewed and compared multiple data structures
- Created a clear summary and exploratory documentation for learning record

---

## 📝 Note

Although the original assignment only required solving the problem,  
this project expands on it by including conceptual notes (`summary.md`) and critical thinking (`DeepCriticalExploration.md`).

---
