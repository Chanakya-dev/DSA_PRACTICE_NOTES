# Searching in DSA — Introduction

## 1. What is Searching?

Searching is a fundamental operation in Data Structures and Algorithms (DSA) used to find a specific element or determine whether an element exists in a collection of data.

The collection may be an array, string, linked list, tree, or another data structure.

For example, consider this array:

```
int[] arr = {10, 25, 30, 45, 50};
int target = 30;
```

Our task is to find whether `30` exists in the array and, if it does, return its index.

Output:

```
Element found at index 2
```

Searching algorithms help us perform this operation efficiently.

## 2. Why do we need Searching?

- To find an element in a collection.
- To check whether a particular value exists.
- To locate the index or position of an element.
- To reduce the time required to find data in large collections.
- To build efficient applications such as databases, search engines, and information retrieval systems.

## 3. Types of Searching Algorithms

Searching algorithms can be organized into the following categories.

[What Is Linear Search? Algorithm, Complexity & Code Examples // Unstop](https://images.openai.com/static-rsc-4/EPZzdyC-VMxlHCeDrNDK_zIYwjO-mK_VqrUUIBk4mVa4kd3MPiEFa2JzF_iZfOTbcaYzmBAuYDPWr1K3xUjO-VEkILoqs4_haEd0UUZLMNNcjAYdQShkrsGkLrk2xFa047nUl0GmXlzrZYw-bRAUaMxTUyhTq_f7GGpni4LaMZU?purpose=inline)

1\. Linear Search

Checks elements one by one until the target is found or the collection ends.

- Works on sorted and unsorted arrays.
- Time complexity: \\(O(n)\\) in the worst case.

[Binary Search Algorithm - Data Structure](https://images.openai.com/static-rsc-4/TprEfDvF_m66eckFZ32rqu64BnicfjtRLQk_z0HRSmlE6fbsSeIo942tqjQxd8AQ_G2QZlFl0KWzoIJR7TWjZqXyNvWXs-9YyUOyFWPkTKwVvVVSUZYlwkn9mzVfF7SRKldgOCZd6Q0zCNtcofbw8xHQt8scJ7julWaqL1wTY84?purpose=inline)

2\. Binary Search

Repeatedly divides the search range in half by comparing the target with the middle element.

- Requires sorted data for the standard array implementation.
- Time complexity: \\(O(\log n)\\).

[Praktikum Algoritma: Interpolation Search dengan Python 🚀⚡ - DEV Community](https://images.openai.com/static-rsc-4/UQD1bezE07vH2JL8lAnSvrBV1Zhwkco_H6cNkvBGFZDe1ZV3fc5YcGKwzwagcLVTAK5QCCRPBFNhHoH23By8_2zr2h1NDX9Y-gDBXkU0M-NxuGElIbfMvhdVVPJXpeR450oaTByelQOQwKGUR_BLbNfG_7pH13tUc82n3CsR5IE?purpose=inline)

3\. Interpolation Search

Estimates the likely position of the target based on its value.

- Best suited to sorted numeric data with approximately uniform distribution.
- Average time can be \\(O(\log\log n)\\) under suitable assumptions; worst case is \\(O(n)\\).

[Jump Search in Python](https://images.openai.com/static-rsc-4/UQJu5gx-ANhEyiYlkNDLWlI8Tz44zOaCaJOa_44bdpgGS3hdXw8HEa0DVJI8P37LAL6AidcPuHv7fkAzLYxTck_y0SBihumRON56VgFlm8JKR9NeEa5bwn8qfBAkS-bsiFw0mLbwY752VT5STQckN2YpMMKHbPK7NH9f7i6ivmk?purpose=inline)

4\. Jump Search

Jumps across blocks of a sorted array, then performs a linear search within the relevant block.

- Requires sorted data.
- Time complexity: \\(O(\sqrt n)\\) with an optimal block size.

Other specialized approaches include exponential search, ternary search, and searching in rotated sorted arrays.

## 4. Linear Search vs. Binary Search

| Feature          | Linear Search      | Binary Search                      |
| ---------------- | ------------------ | ---------------------------------- |
| Data requirement | Sorted or unsorted | Sorted for standard implementation |
| Approach         | Check sequentially | Eliminate half the range           |
| Worst-case time  | \\(O(n)\\)         | \\(O(\log n)\\)                    |
| Best case        | \\(O(1)\\)         | \\(O(1)\\)                         |
| Implementation   | Simple             | Requires careful boundary handling |

## 5. Important concepts to learn before Searching

1. Array indexing and traversal.
2. `for` and `while` loops.
3. Conditional statements.
4. Returning an index or a special value such as `-1`.
5. Understanding time complexity.
6. Understanding why sorted data enables more efficient searching.

## 6. Recommended learning order

For your Java DSA preparation, I recommend following this sequence:

1. Linear Search
2. Search for the first and last occurrence of an element
3. Count occurrences of an element
4. Binary Search fundamentals
5. First and last occurrence using Binary Search
6. Lower Bound and Upper Bound
7. Search in a rotated sorted array
8. Binary Search on Answer
9. Advanced searching problems