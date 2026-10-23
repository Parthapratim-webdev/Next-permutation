# 🔄 Next Permutation

## 📌 Overview

This solution finds the next lexicographically greater permutation of an integer array using an in-place algorithm.

If the array is already in descending order, it reverses the array to produce the smallest possible permutation.

## ⚙️ Workflow

1. **Find the Pivot:** Traverse the array from right to left and find the first index where `A[i] < A[i + 1]`.
2. **Handle No Pivot:** If no pivot exists, reverse the entire array and return.
3. **Find the Next Greater Element:** Search from the right for the first element greater than the pivot.
4. **Swap Elements:** Swap the pivot with the next greater element.
5. **Reverse the Suffix:** Reverse the elements after the pivot to obtain the next permutation.
6. **Finish:** The array now contains the next permutation.

## 🔀 Flowchart

```mermaid
flowchart TD
    A([Start]) --> B[Initialize pivot = -1]
    B --> C[Scan array from right to left]
    C --> D{A[i] < A[i+1]?}
    D -- Yes --> E[Set pivot = i]
    D -- No --> F{More elements to check?}
    F -- Yes --> C
    F -- No --> G{Pivot == -1?}
    E --> G
    G -- Yes --> H[Reverse entire array]
    H --> K([End])
    G -- No --> I[Find rightmost element greater than pivot]
    I --> J[Swap pivot and that element]
    J --> L[Reverse suffix after pivot]
    L --> K
```

## 💻 Example

**Input:**

```text
[1, 2, 3]
```

**Output:**

```text
[1, 3, 2]
```

**Explanation:**

* The pivot is `2`.
* The next greater element is `3`.
* Swap `2` and `3`.
* Reverse the suffix to obtain `[1, 3, 2]`.

## ⏱️ Complexity Analysis

* **Time Complexity:** `O(n)` — The algorithm scans and rearranges the array in linear time.
* **Space Complexity:** `O(1)` — The array is modified in place using constant extra space.

## 🛠️ Technologies Used

* C++
* STL (`vector`, `algorithm`)

## 🎯 Key Concepts

* Array Manipulation
* Two Pointers
* Greedy Algorithm
* In-place Operations
* Lexicographical Ordering
