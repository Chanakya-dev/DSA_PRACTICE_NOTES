# 1. Frequency Counting

Concept: Use `HashMap` to store each element and its frequency.

Beginner:

1. Count the frequency of each element in an array.
2. Count the frequency of each character in a string.
3. Find the most frequent element in an array.
4. Find the least frequent element in an array.
5. Find the character with the highest frequency in a string.
6. Find the character with the lowest frequency in a string.
7. Sort elements by their frequency.
8. Sort characters by their frequency.

Intermediate: 

1. Find the first non-repeating character in a string. 
2. Find the first repeating character in a string. 
3. Find all elements that appear more than `n/2` times. 
4. Find all elements that appear more than `n/3` times. 
5. Find the top `k` frequent elements.
6. Find the top `k` frequent words. 
7. Find the element with the frequency closest to a given value.

# 2. Duplicate Detection and Unique Elements

Concept: Use `HashSet` for membership checks or `HashMap` for frequency information.

1. Check whether an array contains duplicates.
2. Find all duplicate elements in an array.
3. Find all duplicate characters in a string.
4. Remove duplicates from an array.
5. Remove duplicate characters from a string.
6. Find the first duplicate element.
7. Find the first unique element in an array.
8. Find the intersection of two arrays.
9. Find the union of two arrays.
10. Find the symmetric difference of two arrays.
11. Check whether two arrays contain the same elements with the same frequencies.
12. Find missing elements between two arrays.

# 3. Two Sum and Pair Problems

Concept: Store previously seen values in a hash-based collection to find matching values efficiently.

1. Two Sum — find two elements whose sum equals a target.
2. Find whether a pair with a given sum exists.
3. Find all pairs with a given sum.
4. Count pairs with a given sum.
5. Find a pair with a given difference.
6. Find all pairs with a given difference.
7. Find pairs whose product equals a target.
8. Find two numbers whose sum is closest to a target.
9. Find whether two arrays contain a pair with a given sum.
10. Find four elements whose sum equals a target (4Sum).
11. Count pairs with a given XOR.
12. Find two elements whose sum is divisible by `k`.

# 4. Prefix Sum + HashMap

Concept: Store prefix sums and their frequencies or earliest indices to solve subarray problems.

1. Find a subarray with sum zero.
2. Count subarrays with sum zero.
3. Find the number of subarrays with sum equal to `k`.
4. Find the longest subarray with sum equal to `k`.
5. Find the longest subarray with sum zero.
6. Find whether an array contains a zero-sum subarray.
7. Find the longest subarray with an equal number of zeros and ones.
8. Count subarrays with an equal number of zeros and ones.
9. Find the longest subarray with an equal number of even and odd numbers.
10. Count subarrays whose sum is divisible by `k`.
11. Find the longest subarray whose sum is divisible by `k`.
12. Count subarrays with a given XOR.
13. Find the longest subarray with a given XOR.
14. Count binary subarrays with a given sum.

# 5. String Hashing and Anagram Problems

Concept: Represent strings using character frequencies or normalized keys.

1. Check whether two strings are anagrams.
2. Group anagrams together.
3. Find all anagrams of a pattern in a string.
4. Check whether one string is a permutation of another.
5. Find the minimum window substring.
6. Find the longest substring without repeating characters.
7. Find the longest substring with exactly `k` distinct characters.
8. Find the longest substring with at most `k` distinct characters.
9. Find the smallest substring containing all distinct characters of a string.
10. Check whether two strings are isomorphic.
11. Check whether two strings are word-pattern matches.
12. Find all common characters among multiple strings.
13. Find the longest palindrome that can be built using the characters of a string.
14. Find the minimum number of character replacements needed to make two strings anagrams.
15. Find duplicate strings in a list.

Note: Problems 3–9 also use sliding-window techniques; they are useful examples of combining hashing with another pattern.

# 6. Grouping and Mapping Problems

Concept: Map a calculated key to a collection of matching elements.

1. Group anagrams.
2. Group words by their character frequencies.
3. Group numbers by frequency.
4. Group strings that are equivalent under character rearrangement.
5. Find all pairs of indices whose values have a particular relationship.
6. Find employees or records with duplicate identifiers.
7. Find the intersection of multiple arrays.
8. Group elements by their remainder when divided by `k`.
9. Group words by their length.
10. Find all groups of numbers that have the same frequency pattern.

# 7. HashSet-Based Problems

Concept: Use a set when you need fast membership checks and uniqueness.

1. Find the longest consecutive sequence in an unsorted array.
2. Check whether an array is a subset of another array.
3. Find the intersection of two arrays.
4. Find the union of two arrays.
5. Find the missing number in an array.
6. Find the first missing positive integer.
7. Find the number of distinct elements in every window of size `k`.
8. Check whether two arrays are disjoint.
9. Find unique elements common to three sorted arrays.
10. Find the length of the longest chain of consecutive integers.
11. Find whether any two elements differ by a given value.
12. Find the number of distinct elements in an array.

# 8. Advanced Hashing Problems

1. LRU Cache — combine a hash map with a doubly linked list.
2. LFU Cache — track frequency and recency.
3. Design a data structure that supports insert, delete, and random selection in average `O(1)` time.
4. Find all four-element combinations with a target sum.
5. Find the longest duplicate substring.
6. Find repeated DNA sequences.
7. Find the number of matching pairs of songs whose total duration is divisible by 60.
8. Find the maximum number of points on a line using slope-based hashing.
9. Count equivalent domino pairs.
10. Find the number of tuples that sum to zero.
11. Design a frequency stack.
12. Find the longest arithmetic subsequence with a given difference.
13. Find the number of subarrays with a given sum and XOR condition.
14. Find the longest subarray with equal counts of multiple categories.
15. Find distinct echo substrings.

# 9. Java Hashing Internals — Interview Questions

These are conceptual exercises rather than standard DSA coding problems.

1. Explain how `HashMap` works internally.
2. Explain the relationship between `hashCode()` and `equals()`.
3. What happens when two keys have the same hash?
4. How does `HashMap` handle collisions?
5. What is the load factor?
6. When does `HashMap` resize?
7. Why should keys generally be immutable?
8. What happens when a mutable object is used as a map key?
9. Compare `HashMap`, `Hashtable`, and `ConcurrentHashMap`.
10. Compare `HashSet` and `TreeSet`.
11. Why does `HashMap` allow one null key?
12. Why is `HashMap` not thread-safe?
13. How does `ConcurrentHashMap` support concurrent access?
14. What is the difference between a hash collision and two keys being equal?
15. What happens when many keys collide in a Java `HashMap`?

## Recommended order for solving

| Stage | Focus             | Suggested starting problems                          |
| ----- | ----------------- | ---------------------------------------------------- |
| 1     | Fundamentals      | Frequency counting, duplicates, first unique element |
| 2     | Lookup            | Two Sum, pair with a given difference                |
| 3     | Sets              | Longest consecutive sequence, array intersection     |
| 4     | Prefix sum        | Subarray sum equals `k`, longest zero-sum subarray   |
| 5     | Strings           | Valid anagram, group anagrams                        |
| 6     | Combined patterns | Sliding window + hashing, prefix sum + hashing       |
| 7     | Advanced          | LRU Cache, frequency stack, 4Sum                     |
| 8     | Java internals    | `hashCode()`, `equals()`, collisions, resizing       |