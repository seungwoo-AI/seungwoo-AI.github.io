# CourseSummary.md

## 📘 Course Title: Efficient Swap Counting and Data Structures for Inversion Problems

---

## 📚 Overview

This course covers efficient techniques to count swap operations (inversions) in arrays, particularly in the context of sorting algorithms like bubble sort. The focus is on applying advanced data structures like **Fenwick Trees** (Binary Indexed Trees), **Segment Trees**, **Merge Sort**, and **coordinate compression**, while understanding computational complexity and optimization trade-offs.

---

## 📂 Module 1: Problem Statement and Motivation

- Definition of **swap operation** in sorting
- Understanding **inversions**: pairs \((i < j) \land A[i] > A[j]\)
- Why counting swaps matters (e.g., simulation of bubble sort)

---

## 📂 Module 2: Naive Approaches

- **Bubble sort-based** swap counting (\(O(N^2)\))
- Brute-force nested loop to count inversions

---

## 📂 Module 3: Efficient Inversion Counting Algorithms

### 🔸 3.1 Merge Sort Method

- Modified merge sort to count inversions during merge phase
- If right[j] < left[i], count += (len(left) - i)
- Time complexity: **O(N log N)**
- Recursion and array copying introduce overhead

### 🔸 3.2 Fenwick Tree Method

- Binary Indexed Tree structure
- Prefix sum queries and updates in **O(log N)**
- Inversion counting via right-to-left traversal:
  - `query(rank - 1)` → number of smaller elements seen so far
  - `update(rank, 1)` → mark current value as seen
- Time complexity: **O(N log N)**
- Lower constant factor; cache-friendly; iterative

### 🔸 3.3 Segment Tree Method

- Tree-based structure for range sum queries and updates
- Suitable for more flexible range operations
- Time complexity: **O(N log N)**
- Higher constant factor and complexity than Fenwick Tree

---

## 📂 Module 4: Coordinate Compression

- Goal: transform large/sparse input into compact indexable ranks
- Steps:
  1. Copy and sort array
  2. Assign incremental ranks to unique values
  3. Map original values to ranks using a hash map
- Enables safe index use in Fenwick and Segment Trees

---

## 📂 Module 5: Optimization Trade-offs

| Method        | Time Complexity | Recursion | Memory Overhead | Speed (Practical) |
|---------------|------------------|-----------|------------------|--------------------|
| Bubble Sort   | O(N²)            | No        | Low              | ❌ Too slow        |
| Merge Sort    | O(N log N)       | ✅ Yes     | ✅ High           | ⚠️ Moderate        |
| Segment Tree  | O(N log N)       | ⚠️ Maybe   | ⚠️ Moderate       | ⚠️ Medium          |
| Fenwick Tree  | O(N log N)       | ❌ None    | ✅ Low            | ✅ Fastest         |

---

## 📂 Module 6: Applications

- Competitive programming (e.g., BOJ 1517)
- Online inversion tracking
- Frequency and prefix-sum management in compressed domains

---

## 📂 Module 7: Visualization & Intuition

- Fenwick Tree visualized as partial sum intervals
- Index updates via `i += (i & -i)`
- Queries via `i -= (i & -i)`
- Compact and efficient binary structure

---

## 📂 Module 8: Practice Problems

- Implement merge-sort-based inversion count
- Build Fenwick Tree from scratch
- Use coordinate compression with Fenwick Tree
- Analyze swap count with test inputs

---

## 📂 Module 9: Final Review

- Best method: **Fenwick Tree + Coordinate Compression**
- Key formula:
  - Inversions = \(\sum \text{query(rank - 1)}\) (right to left)
- Merge Sort and Segment Tree are valid but less optimal in practice

---

## 📂 Module 10: Code Implementation (Java)

The following Java implementation uses a **clean, modular structure** to solve the inversion count problem using a **Fenwick Tree + coordinate compression**:

```java
import java.io.*;
import java.util.*;

public class Main {

    static class FenwickTree {
        private final int[] tree;

        FenwickTree(int size) {
            tree = new int[size + 1];
        }

        void update(int index, int delta) {
            while (index < tree.length) {
                tree[index] += delta;
                index += index & -index;
            }
        }

        int query(int index) {
            int result = 0;
            while (index > 0) {
                result += tree[index];
                index -= index & -index;
            }
            return result;
        }
    }

    public static void main(String[] args) throws IOException {
        BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
        int n = Integer.parseInt(br.readLine());
        int[] original = new int[n];
        int[] compressed = new int[n];

        StringTokenizer st = new StringTokenizer(br.readLine());
        for (int i = 0; i < n; i++) {
            original[i] = Integer.parseInt(st.nextToken());
            compressed[i] = original[i];
        }

        // Coordinate Compression
        Arrays.sort(compressed);
        Map<Integer, Integer> rankMap = new HashMap<>();
        int rank = 1;
        for (int val : compressed) {
            if (!rankMap.containsKey(val)) {
                rankMap.put(val, rank++);
            }
        }

        FenwickTree fenwick = new FenwickTree(rankMap.size());
        long inversionCount = 0;

        for (int i = n - 1; i >= 0; i--) {
            int r = rankMap.get(original[i]);
            inversionCount += fenwick.query(r - 1);
            fenwick.update(r, 1);
        }

        System.out.println(inversionCount);
    }
}
```

---

## 🧠 Key Concepts Recap

- Inversion = \((i < j) \land A[i] > A[j]\)
- Fenwick Tree = Fast prefix sum + update
- Coordinate compression = Index remapping
- Swap count = Total number of inversions

---

## ✅ Prerequisites

- Understanding of arrays and sorting
- Binary operations (e.g., `i & -i`)
- Basic trees and hash maps

---

## 🛠 Suggested Tools

- Java or Python for implementation
- Debugger to trace tree updates
- Visualization tools for prefix sum trees

---
