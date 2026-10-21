# Sliding Window Technique — Introduction

## 1. What is the Sliding Window Technique?

The Sliding Window Technique is an algorithmic technique used to solve problems involving a contiguous sequence of elements in an array or string.

A window represents a continuous range of elements. Instead of repeatedly processing the entire range for every possible subarray or substring, we move the window across the input and update the result efficiently.

The window is usually controlled by two pointers:

- `left` — represents the starting boundary of the window.
- `right` — represents the ending boundary of the window.

The window can expand, shrink, or move forward depending on the problem's conditions.

### Example

Consider the array:

```
int[] arr = {2, 4, 6, 8, 10};
```

Suppose we need to find the sum of every three consecutive elements.

The window size is `k = 3`.

Window 1: Elements at indices 0–2

## 2

0

## 4

1

## 6

2

## 8

3

## 10

4

Sum = 2 + 4 + 6 = 12

Window 2: Move one position to the right

## 2

0

## 4

1

## 6

2

## 8

3

## 10

4

Sum = 4 + 6 + 8 = 18

Window 3: Move one more position

## 2

0

## 4

1

## 6

2

## 8

3

## 10

4

Sum = 6 + 8 + 10 = 24

Instead of calculating each sum from scratch, we can subtract the element leaving the window and add the element entering it.

For example:

\\[ \text{New Sum}=\text{Old Sum}-\text{Outgoing Element}+\text{Incoming Element} \\]

Therefore:

\\[ 18=12-2+8 \\]

This is the fundamental idea behind the sliding window technique.

## 2. Why do we need Sliding Window?

Consider an array of `n` elements. We need to find the maximum sum of any three consecutive elements.

### Approach 1: Brute force

Calculate the sum of every group of three elements independently.

```
int[] arr = {2, 4, 6, 8, 10};
int k = 3;

int maxSum = Integer.MIN_VALUE;

for (int i = 0; i <= arr.length - k; i++) {
    int sum = 0;

    for (int j = i; j < i + k; j++) {
        sum += arr[j];
    }

    maxSum = Math.max(maxSum, sum);
}

System.out.println(maxSum); // 24
```

Time complexity: \\(O(nk)\\), where `k` is the window size. If `k` grows proportionally with `n`, this becomes \\(O(n^2)\\).

### Approach 2: Sliding window

```
int[] arr = {2, 4, 6, 8, 10};
int k = 3;

int windowSum = 0;

for (int i = 0; i < k; i++) {
    windowSum += arr[i];
}

int maxSum = windowSum;

for (int right = k; right < arr.length; right++) {
    windowSum += arr[right];
    windowSum -= arr[right - k];

    maxSum = Math.max(maxSum, windowSum);
}

System.out.println(maxSum); // 24
```

Time complexity: \\(O(n)\\)

Extra space: \\(O(1)\\)

The optimization works because we reuse the sum calculated for the previous window instead of processing every element again.

## 3. Main Categories of Sliding Window

For your DSA notes, organize the Sliding Window Technique into these two main categories.

### Category 1: Fixed-Size Sliding Window

The window size remains constant throughout the algorithm.

For example, if `k = 3`, every window contains exactly three consecutive elements.

Typical problems:

- Maximum sum of a subarray of size `k`.
- Minimum sum of a subarray of size `k`.
- Average of every subarray of size `k`.
- First negative number in every window of size `k`.
- Count occurrences of an element in every window of size `k`.
- Find the maximum of every sliding window.

### Category 2: Variable-Size Sliding Window

The window expands or shrinks according to a condition. Its size is not fixed.

Typical problems:

- Longest substring without repeating characters.
- Minimum size subarray sum.
- Longest subarray satisfying a given constraint.
- Longest substring containing at most `k` distinct characters.
- Minimum window substring.
- Longest substring after replacing at most `k` characters.

Variable-size sliding windows often maintain a property such as a sum limit, character frequency, or number of distinct elements.

Important: The common expand-and-shrink approach works only when the condition supports those movements. For example, a simple sum-based window does not generally work for finding a target sum when negative numbers are allowed.

## 4. When should you identify a Sliding Window problem?

Look for these clues in a problem statement:

- It asks about a contiguous subarray or substring.
- It asks for the maximum or minimum sum over consecutive elements.
- It asks for a longest or shortest valid substring.
- It asks about every group of `k` consecutive elements.
- It involves character frequencies inside a substring.
- It requires finding a continuous range satisfying a condition.

Remember the difference:

- Subarray/substring: Elements must be contiguous.
- Subsequence: Elements must preserve their order, but they do not need to be contiguous.

Sliding window is generally designed for contiguous ranges.

## 5. Sliding Window vs. Two Pointer Technique

| Feature                    | Two Pointer Technique                      | Sliding Window Technique                     |
| -------------------------- | ------------------------------------------ | -------------------------------------------- |
| Purpose                    | Tracks two positions to solve a problem    | Maintains and processes a contiguous range   |
| Pointer movement           | May move inward, forward, or independently | Usually uses left and right boundaries       |
| Contiguous range required? | No                                         | Yes, for the standard sliding window pattern |
| Common example             | Two Sum in a sorted array                  | Maximum sum of `k` consecutive elements      |
| Relationship               | General family of techniques               | Specialized two-pointer pattern              |

## Final takeaway

The Sliding Window Technique reduces unnecessary repeated calculations by maintaining a contiguous range and updating it as the boundaries move.

Start by mastering fixed-size sliding window, where the update rule is straightforward. Then learn variable-size sliding window, where you must determine when to expand and when to shrink the window.