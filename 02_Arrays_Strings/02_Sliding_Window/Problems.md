# 1. Fixed-Size Sliding Window

Concept: The window size `k` remains constant.

## Beginner

1. Find the maximum sum of any subarray of size `k`.
2. Find the minimum sum of any subarray of size `k`.
3. Find the average of every subarray of size `k`.
4. Count the number of subarrays of size `k` whose sum equals a target.
5. Find the first negative number in every window of size `k`.
6. Find the maximum number in every window of size `k`.
7. Find the minimum number in every window of size `k`.

## Intermediate

8. Find the first non-repeating character in every window of size `k`.
9. Count distinct elements in every window of size `k`.
10. Find the sum of elements at every window position and return the maximum.
11. Find the maximum number of vowels in any substring of length `k`.
12. Find the number of anagrams of a pattern in a string.
13. Find all starting indices of anagrams of a given string.
14. Check whether any permutation of a pattern exists in a string.
15. Find the maximum sum of a subarray of size `k` containing exactly `k` distinct elements.

# 2. Variable-Size Sliding Window

Concept: Expand the window by moving `right` and shrink it by moving `left` when necessary.

## Beginner

1. Find the smallest subarray with a sum greater than or equal to a target (positive numbers).
2. Find the longest subarray with a sum less than or equal to a target (positive numbers).
3. Find the longest substring without repeating characters.
4. Find the longest substring containing only a limited number of distinct characters.
5. Find the length of the longest substring containing at most `k` distinct characters.

## Intermediate

6. Find the minimum-size subarray with sum greater than or equal to a target.
7. Find the longest subarray containing at most `k` zeros when you can flip zeros to ones.
8. Find the longest sequence of ones after flipping at most `k` zeros.
9. Find the longest repeating-character replacement substring.
10. Find the longest substring with at most two distinct characters.
11. Find the number of subarrays with at most `k` distinct integers.
12. Find the number of subarrays with exactly `k` distinct integers.
13. Find the longest subarray with at most `k` different elements.
14. Find the maximum number of fruits collected using two baskets.
15. Find the longest subarray after deleting one element to obtain only ones.

## Advanced

16. Find the minimum window substring containing all characters of a target.
17. Find the shortest substring containing all distinct characters present in the original string.
18. Find the minimum window subsequence.
19. Find the longest substring with at most `k` replacements to make all characters equal.
20. Count subarrays whose product is less than `k` (positive integers).
21. Count subarrays with exactly `k` odd numbers.
22. Count binary subarrays with a given sum.
23. Find the number of subarrays with exactly `k` distinct integers using the `atMost(k) - atMost(k-1)` technique.

# 3. Sliding Window with Frequency Maps

Concept: Maintain character or element frequencies as the window expands and shrinks.

1. Find all anagrams of a string in another string.
2. Check whether a string contains a permutation of another string.
3. Find the minimum window substring.
4. Find the longest substring without repeating characters.
5. Find the longest substring with at most `k` distinct characters.
6. Find the number of substrings containing all three characters `a`, `b`, and `c`.
7. Find the longest substring where every character appears at least `k` times.
8. Find the smallest substring containing all distinct characters of a string.
9. Find the number of subarrays with exactly `k` distinct elements.
10. Find the longest substring that can be formed by replacing at most `k` characters.

# 4. Sliding Window with Deque

Concept: Use a deque to maintain candidate maximum or minimum values efficiently.

1. Sliding Window Maximum.
2. Sliding Window Minimum.
3. Find the maximum of every window of size `k`.
4. Find the minimum of every window of size `k`.
5. Find the maximum value in each window and calculate the sum of those maximums.
6. Find the shortest subarray with sum at least `k` — advanced; supports negative values with a monotonic deque.
7. Find the maximum of each sliding window using a monotonic queue.

# 5. Advanced Sliding Window Variations

1. Maximum points you can obtain from cards.
2. Maximum consecutive ones III.
3. Longest continuous subarray with absolute difference less than or equal to a limit.
4. Subarrays with K different integers.
5. Count number of nice subarrays.
6. Binary subarrays with sum.
7. Minimum operations to reduce `x` to zero.
8. Frequency of the most frequent element.
9. Maximum sum of two non-overlapping subarrays.
10. Minimum swaps to group all ones together.
11. Minimum swaps to group all ones together II — circular array variation.
12. Maximum sum of distinct subarrays with length `k`.
13. Maximum erasure value.
14. Count complete subarrays in an array.
15. Count subarrays where the maximum element appears at least `k` times.