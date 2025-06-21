# Course Summary — Data Structures

---

## 1. Foundational Complexity

| Notation       | Meaning       | Typical Example          |
| -------------- | ------------- | ------------------------ |
| **O(1)**       | Constant time | Hash table lookup (avg.) |
| **O(log n)**   | Logarithmic   | Balanced BST search      |
| **O(n)**       | Linear        | Unordered array scan     |
| **O(n log n)** | Log‑linear    | MergeSort                |
| **O(n²)**      | Quadratic     | Bubble/Selection sort    |

---

## 2. Linear Structures

### 2.1 Arrays & Linked Lists

* **Array** — random access O(1); costly inserts/deletes
* **Singly Linked List** — sequential access; inserts/deletes O(1)

### 2.2 Stacks & Queues

| Structure | Principle | Key Ops                       |
| --------- | --------- | ----------------------------- |
| **Stack** | LIFO      | `push`, `pop`, `top`          |
| **Queue** | FIFO      | `enqueue`, `dequeue`, `front` |

---

## 3. Trees

### 3.1 Binary Search Tree (BST)

* Rule: left `<` root `<` right
* Avg.: **O(log n)**; Worst: **O(n)**

### 3.2 AVL Tree

* Balance factor ∈ {‑1,0,1}; rotations keep height Θ(log n)

### 3.3 Heap (Binary)

* Complete tree + heap property (max/min)
* Ops: `insert`, `deleteMax/Min` → **O(log n)**

---

## 4. Priority Queue

* ADT supporting `insert`, `findMin/Max`, `deleteMin/Max`
* Heap implementation is standard (in‑place, log height)

---

## 5. Hashing

| Component         | Details                                                     |
| ----------------- | ----------------------------------------------------------- |
| **Hash Fn**       | Division: `k mod m`; Multiplication: `⌊m(kA mod 1)⌋`        |
| **Load Factor α** | α = n/m; keep ≤ 0.7                                         |
| **Collisions**    | Separate Chaining, Linear/Quadratic Probing, Double Hashing |
| **Rehash**        | Grow table when α high or probe length spikes               |

---

## 6. Sorting Algorithms

### 6.1 Simple

| Algo      | Idea                      | Best | Avg | Worst | Stable |
| --------- | ------------------------- | ---- | --- | ----- | ------ |
| Selection | Select min each pass      | n²   | n²  | n²    | ✘      |
| Bubble    | Adjacent swaps            | n    | n²  | n²    | ✔      |
| Insertion | Insert into sorted prefix | n    | n²  | n²    | ✔      |

### 6.2 Efficient Comparison Sorts

| Algo  | Strategy        | Best/Avg/Worst | Stable       |
| ----- | --------------- | -------------- | ------------ |
| Merge | Divide‑merge    | n log n        | ✔            |
| Quick | Pivot partition | n log n / n²   | ✘ (standard) |
| Heap  | Heap property   | n log n        | ✘            |
| Shell | Gap sequence    | \~n^1.3        | ✘            |

### 6.3 Non‑comparison

| Algo     | Use‑case               | Time          |
| -------- | ---------------------- | ------------- |
| Counting | Small integer keys (k) | O(n + k)      |
| Radix    | Fixed‑length keys      | O(k·n)        |
| Bucket   | Uniform \[0,1)         | Expected O(n) |

---

## 7. Graph Algorithms

### 7.1 Representation

* **Adjacency List** — O(V+E) memory, sparse graphs
* **Adjacency Matrix** — O(V²) memory, dense graphs

### 7.2 Traversal

| Algo | Structure       | Use                                     |
| ---- | --------------- | --------------------------------------- |
| BFS  | Queue           | Shortest path (unweighted), level order |
| DFS  | Stack/Recursion | Topological sort, connectivity          |

### 7.3 Minimum Spanning Tree

| Algo    | Core Idea               | Complexity |
| ------- | ----------------------- | ---------- |
| Kruskal | Sort edges + Union‑Find | O(E log E) |
| Prim    | Grow tree via PQ        | O(E log V) |

### 7.4 Shortest Path (SSSP)

| Algo             | Edge Weights | Notes               |
| ---------------- | ------------ | ------------------- |
| **Dijkstra**     | ≥0           | Heap PQ, O(E log V) |
| **Bellman‑Ford** | neg. allowed | O(VE)               |

---

## 8. Search & Selection

* **Binary Search** (sorted array) — O(log n)
* **Interpolation Search** — O(log log n) average
* **QuickSelect** (partial QuickSort) — O(n) average, O(n²) worst

---

## 9. Paradigms Quick‑View

| Paradigm            | Examples                         |
| ------------------- | -------------------------------- |
| Divide & Conquer    | MergeSort, QuickSort             |
| Greedy              | Kruskal, Prim                    |
| Dynamic Programming | (Knapsack, not covered in depth) |

---

## 10. Complexity Cheat‑Sheet

| Operation / Algo    | Best    | Avg     | Worst   |
| ------------------- | ------- | ------- | ------- |
| BST Search          | log n   | log n   | n       |
| AVL Search          | log n   | log n   | log n   |
| Heap Insert/Delete  | log n   | log n   | log n   |
| Hash Search (α≈0.7) | 1       | 1       | n       |
| QuickSort           | n log n | n log n | n²      |
| MergeSort           | n log n | n log n | n log n |
| Heapsort            | n log n | n log n | n log n |
| BFS/DFS             | V+E     | V+E     | V+E     |
| Dijkstra (PQ)       | —       | E log V | —       |

---

### End of `CourseSummary.md`
