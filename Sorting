# DSA Sorting Algorithms Cheat Sheet

## What is Sorting?

Sorting is the process of arranging data in a specific order (Ascending or Descending).

Example:

```text
Unsorted: 5 2 8 1 4
Sorted:   1 2 4 5 8
```

---

# Sorting Algorithms Overview

| Algorithm      | Definition                         | Time Complexity | Space    | Stable  | Interview Importance |
| -------------- | ---------------------------------- | --------------- | -------- | ------- | -------------------- |
| Bubble Sort    | Swap adjacent elements repeatedly  | O(n²)           | O(1)     | Yes     | ⭐                    |
| Selection Sort | Select minimum and place correctly | O(n²)           | O(1)     | No      | ⭐                    |
| Insertion Sort | Insert element into sorted portion | O(n²)           | O(1)     | Yes     | ⭐⭐                   |
| Merge Sort     | Divide, Sort, Merge                | O(n log n)      | O(n)     | Yes     | ⭐⭐⭐                  |
| Quick Sort     | Pivot-based partitioning           | O(n log n) Avg  | O(log n) | No      | ⭐⭐⭐                  |
| Heap Sort      | Use Heap data structure            | O(n log n)      | O(1)     | No      | ⭐⭐⭐                  |
| Counting Sort  | Count occurrences                  | O(n+k)          | O(k)     | Yes     | ⭐⭐                   |
| Radix Sort     | Sort digit by digit                | O(nk)           | O(n+k)   | Yes     | ⭐⭐                   |
| Bucket Sort    | Distribute into buckets            | O(n+k) Avg      | O(n)     | Depends | ⭐                    |

---

# 1. Bubble Sort

## Definition

Repeatedly compare adjacent elements and swap if they are in the wrong order.

## Example

```text
5 3 4

5 > 3 → Swap
3 5 4

5 > 4 → Swap
3 4 5
```

## Complexity

```text
Best    : O(n)
Average : O(n²)
Worst   : O(n²)
Space   : O(1)
```

---

# 2. Selection Sort

## Definition

Find the minimum element and place it at its correct position.

## Example

```text
5 3 4 1

Minimum = 1

1 3 4 5
```

## Complexity

```text
Best    : O(n²)
Average : O(n²)
Worst   : O(n²)
Space   : O(1)
```

---

# 3. Insertion Sort

## Definition

Insert each element into the correct position of the already sorted part.

## Example

```text
5

3 5

3 4 5
```

## Complexity

```text
Best    : O(n)
Average : O(n²)
Worst   : O(n²)
Space   : O(1)
```

---

# 4. Merge Sort

## Definition

Divide the array into halves, sort them recursively, then merge.

## Example

```text
8 4 2 6

8 4 | 2 6

8 | 4
2 | 6

4 8
2 6

2 4 6 8
```

## Complexity

```text
Best    : O(n log n)
Average : O(n log n)
Worst   : O(n log n)
Space   : O(n)
```

## Advantages

* Stable
* Guaranteed O(n log n)

---

# 5. Quick Sort

## Definition

Choose a pivot and partition elements around it.

## Example

```text
4 7 2 9 1

Pivot = 4

2 1 | 4 | 7 9
```

## Complexity

```text
Best    : O(n log n)
Average : O(n log n)
Worst   : O(n²)
Space   : O(log n)
```

## Advantages

* Fastest in practice
* Most asked in interviews

---

# 6. Heap Sort

## Definition

Build a heap and repeatedly remove the root element.

## Example

```text
8
/ \
5 3
/
1
```

## Complexity

```text
Best    : O(n log n)
Average : O(n log n)
Worst   : O(n log n)
Space   : O(1)
```

## Advantages

* In-place
* Useful for Top-K problems

---

# 7. Counting Sort

## Definition

Count frequency of each number.

## Example

```text
1 4 2 1 3

Count:

1 → 2
2 → 1
3 → 1
4 → 1
```

## Complexity

```text
O(n + k)
```

where k = range of numbers.

---

# 8. Radix Sort

## Definition

Sort numbers digit by digit.

## Example

```text
170
45
75
90

Sort by:
1's digit
10's digit
100's digit
```

## Complexity

```text
O(nk)
```

---

# 9. Bucket Sort

## Definition

Distribute elements into buckets and sort each bucket.

## Example

```text
0.12
0.44
0.87
0.23

Bucket 1
Bucket 2
Bucket 3
```

## Complexity

```text
Average: O(n+k)
Worst  : O(n²)
```

---

# Quick Recognition Table

| Requirement           | Best Algorithm |
| --------------------- | -------------- |
| General Purpose       | Quick Sort     |
| Guaranteed O(n log n) | Merge Sort     |
| Stable Sorting        | Merge Sort     |
| Top K Elements        | Heap Sort      |
| Nearly Sorted Data    | Insertion Sort |
| Small Integer Range   | Counting Sort  |
| Large Integer Digits  | Radix Sort     |

---

# Interview Priority

## Must Know

1. Merge Sort
2. Quick Sort
3. Heap Sort

## Good To Know

4. Insertion Sort
5. Counting Sort
6. Radix Sort

## Basic Knowledge

7. Bubble Sort
8. Selection Sort
9. Bucket Sort

---

# Memory Trick

```text
Bubble     → Swap Neighbors
Selection  → Select Minimum
Insertion  → Insert Correct Position
Merge      → Divide and Merge
Quick      → Pivot Partition
Heap       → Heap Structure
Counting   → Count Frequencies
Radix      → Digit by Digit
Bucket     → Group into Buckets
```
