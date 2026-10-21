# Two Pointer Technique — Complete Problem List

Organize your DSA notes into the following three categories. I've arranged the problems from beginner to advanced so you can practise them in order.

# 1. Two Pointers in Opposite Direction

One pointer starts at the beginning, and the other starts at the end. They move toward each other or inward according to the problem's conditions.

## Level 1 — Beginner

1. Reverse an Array
2. Reverse a String
3. Check Whether a String Is a Palindrome
4. Valid Palindrome — LeetCode 125
5. Reverse Vowels of a String — LeetCode 345
6. Two Sum II — Input Array Is Sorted — LeetCode 167
7. Find Pair With a Given Sum in a Sorted Array
8. Find Pair With a Given Difference in a Sorted Array
9. Check Whether an Array Is a Palindrome
10. Check Whether a String Is a Valid Palindrome After Removing Non-Alphanumeric Characters

## Level 2 — Intermediate

11. Squares of a Sorted Array — LeetCode 977
12. Remove Duplicates From Sorted Array II — LeetCode 80 (also applicable to same-direction pointers)
13. Container With Most Water — LeetCode 11
14. Valid Palindrome II — LeetCode 680
15. 3Sum — LeetCode 15
16. 3Sum Closest — LeetCode 16
17. Boats to Save People — LeetCode 881
18. Sort Colors — LeetCode 75 (usually same-direction pointers)
19. Find the Pair With Sum Closest to Target in a Sorted Array
20. Find All Unique Pairs With a Given Sum in a Sorted Array

## Level 3 — Advanced

21. 4Sum — LeetCode 18
22. Trapping Rain Water — LeetCode 42
23. 3Sum Smaller
24. Minimum Length of Subarray With Sum at Least Target — usually sliding window, a related pattern
25. Find K-Diff Pairs in an Array — LeetCode 532
26. Count Number of Pairs With Absolute Difference K — LeetCode 2006 (sorting plus two pointers is one possible approach)
27. Find the Number of Valid Triangle Triplets — LeetCode 611
28. Minimum Number of Moves to Make Array Elements Equal — LeetCode 462 (sorting-based approaches)
29. Three Sum With Multiplicity — LeetCode 923
30. Find All Triplets With a Given Sum

# 2. Two Pointers in Same Direction

Both pointers move forward, usually with different responsibilities. This category is particularly useful for in-place array modification, filtering, partitioning, and fast/slow pointer problems.

## Level 1 — Beginner

1. Remove Duplicates From Sorted Array — LeetCode 26
2. Remove Element — LeetCode 27
3. Move Zeroes — LeetCode 283
4. Remove All Occurrences of a Given Element
5. Move All Negative Numbers to the Beginning
6. Separate Even and Odd Numbers
7. Find the Middle of a Linked List — LeetCode 876
8. Detect a Cycle in a Linked List — LeetCode 141
9. Find the Length of a Linked List
10. Find the Nth Node From the Beginning of a Linked List

## Level 2 — Intermediate

11. Remove Duplicates From Sorted Array II — LeetCode 80
12. Partition Array According to a Given Condition
13. Sort Array by Parity — LeetCode 905 (also commonly solved with opposite-direction pointers)
14. Sort Array by Parity II — LeetCode 922
15. Linked List Cycle II — LeetCode 142
16. Find the Starting Point of a Linked List Cycle
17. Find the Nth Node From the End of a Linked List
18. Remove the Nth Node From the End of a Linked List — LeetCode 19
19. Palindrome Linked List — LeetCode 234
20. Reorder List — LeetCode 143 (combines fast/slow pointers, reversal, and merging)
21. Find the Duplicate Number — LeetCode 287 (fast/slow cycle detection)
22. Happy Number — LeetCode 202 (fast/slow cycle detection)

## Level 3 — Advanced

23. Sort List — LeetCode 148 (merge sort with slow/fast pointers)
24. Insertion Sort List — LeetCode 147
25. Rotate List — LeetCode 61
26. Partition List — LeetCode 86
27. Odd Even Linked List — LeetCode 328
28. Split Linked List in Parts — LeetCode 725
29. Maximum Twin Sum of a Linked List — LeetCode 2130
30. Find the Duplicate Number Without Modifying the Array — LeetCode 287

Note: The fast/slow linked-list pattern belongs to the same-direction family, but some linked-list problems combine it with reversal or other techniques.

# 3. Two Pointers Each Pointing to a Different Data Structure

Each pointer tracks its own array, string, or linked list. The pointers advance independently according to the relationship between the current elements.

## Level 1 — Beginner

1. Merge Two Sorted Arrays Into a New Array
2. Merge Sorted Array — LeetCode 88 (the standard in-place solution uses pointers from the ends)
3. Check Whether One String Is a Subsequence of Another — LeetCode 392
4. Find Common Elements in Two Sorted Arrays
5. Find the Intersection of Two Sorted Arrays
6. Find the Union of Two Sorted Arrays
7. Compare Two Strings Character by Character
8. Check Whether Two Strings Are Equal
9. Find the First Matching Element in Two Sorted Arrays
10. Merge Two Sorted Linked Lists — LeetCode 21

## Level 2 — Intermediate

11. Intersection of Two Arrays — LeetCode 349 (sorting plus two pointers is one approach)
12. Intersection of Two Arrays II — LeetCode 350
13. Backspace String Compare — LeetCode 844 (can be solved using pointers from the ends)
14. Append Characters to String to Make Subsequence — LeetCode 2486
15. Isomorphic Strings — LeetCode 205 (usually mapping-based rather than a classic two-pointer problem)
16. Compare Version Numbers — LeetCode 165
17. Find the Longest Common Prefix Between Two Sorted Sequences
18. Check Whether a String Is an Interleaving of Two Strings — LeetCode 97 (usually dynamic programming)
19. Merge Two Sorted Lists — LeetCode 21
20. Merge K Sorted Lists — LeetCode 23 (typically uses a heap or divide and conquer)

## Level 3 — Advanced

21. Shortest Common Supersequence — LeetCode 1092 (typically dynamic programming)
22. Minimum Number of Operations to Make Arrays Similar — LeetCode 2449 (sorting plus matching)
23. Find Common Characters — LeetCode 1002 (frequency counting is more appropriate)
24. Count Pairs From Two Sorted Arrays With a Target Sum
25. Find All Common Elements Across Multiple Sorted Arrays
26. Compare Two Linked Lists for Identical Structure and Values
27. Merge Two Sorted Sequences While Preserving Order
28. Find the Median of Two Sorted Arrays — LeetCode 4 (advanced; binary search is the standard optimal solution)
29. Smallest Range Covering Elements From K Lists — LeetCode 632 (typically a heap or ordered structure)
30. Find the Longest Common Subsequence — LeetCode 1143 (typically dynamic programming)

Some advanced problems in this section are included because they involve comparing or merging two sequences, but their optimal solutions usually require another technique such as dynamic programming, hashing, binary search, or heaps. Treat those as related problems rather than pure two-pointer exercises.

## Recommended practice order

If your goal is to build strong DSA fundamentals for Java interviews, use this order:

| Stage | Focus                                  | Target       |
| ----- | -------------------------------------- | ------------ |
| 1     | Opposite-direction fundamentals        | 8 problems   |
| 2     | Same-direction array manipulation      | 8 problems   |
| 3     | Two different arrays or strings        | 6 problems   |
| 4     | Linked-list fast/slow pointers         | 6 problems   |
| 5     | Intermediate and advanced combinations | 10+ problems |

Important: Sliding window is a related specialized two-pointer pattern, but I've kept it separate from these three categories. Problems such as Longest Substring Without Repeating Characters and Minimum Window Substring should go into your separate Sliding Window notes.