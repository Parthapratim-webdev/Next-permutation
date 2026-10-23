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

```mermaid
flowchart TD
    A([Start]) --> B[Initialize pivot = -1]
    B --> C[Set i = n - 2]
    C --> D{i >= 0?}
    D -- Yes --> E{A[i] < A[i + 1]?}
    E -- Yes --> F[Set pivot = i]
    F --> I{pivot == -1?}
    E -- No --> G[Decrement i]
    G --> D
    D -- No --> I

    I -- Yes --> J[Reverse entire array]
    J --> Z([End])

    I -- No --> K[Set i = n - 1]
    K --> L{i > pivot?}
    L -- Yes --> M{A[i] > A[pivot]?}
    M -- No --> N[Decrement i]
    N --> L
    M -- Yes --> O[Swap A[i] and A[pivot]]
    O --> R[Set i = pivot + 1 and j = n - 1]

    L -- No --> R
    R --> S{i < j?}
    S -- Yes --> T[Swap A[i] and A[j]]
    T --> U[Increment i and decrement j]
    U --> S
    S -- No --> Z
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
