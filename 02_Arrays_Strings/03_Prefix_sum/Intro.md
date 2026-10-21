# Prefix Sum — Introduction

## 1. What is Prefix Sum?

Prefix Sum is a technique used to calculate the sum of a range of elements efficiently by storing cumulative sums.

Instead of repeatedly adding elements for every range query, we calculate running sums once and reuse them.

Consider this array:

```
int[] arr = {2, 4, 6, 8, 10};
```

Its prefix sum array is:

```
Original Array:  2   4   6   8   10
Prefix Sum:      2   6  12  20   30
```

Each prefix sum represents the sum of all elements from index `0` to the current index.

For example:

- `prefix[0] = 2`
- `prefix[1] = 2 + 4 = 6`
- `prefix[2] = 2 + 4 + 6 = 12`
- `prefix[3] = 2 + 4 + 6 + 8 = 20`
- `prefix[4] = 2 + 4 + 6 + 8 + 10 = 30`

## 2. Why do we need Prefix Sum?

Suppose you need to calculate the sum from index `1` to index `3` repeatedly.

The array is:

```
int[] arr = {2, 4, 6, 8, 10};
```

The required sum is:

\\[ 4+6+8=18 \\]

Without prefix sum, you add the elements in the requested range each time.

With prefix sum, you can calculate the result using:

\\[ \text{sum}(L,R)=prefix[R]-prefix[L-1] \\]

Therefore:

\\[ \text{sum}(1,3)=20-2=18 \\]

We subtract the sum before index `1` from the cumulative sum ending at index `3`.

## 3. How to construct a Prefix Sum array in Java

```
import java.util.*;

public class Main {
    public static void main(String[] args) {
        int[] arr = {2, 4, 6, 8, 10};
        int n = arr.length;

        int[] prefix = new int[n];

        prefix[0] = arr[0];

        for (int i = 1; i < n; i++) {
            prefix[i] = prefix[i - 1] + arr[i];
        }

        System.out.println(Arrays.toString(prefix));
    }
}
```

Output:

```
[2, 6, 12, 20, 30]
```

The key formula is:

\\[ prefix[i]=prefix[i-1]+arr[i] \\]

## 4. Calculate a range sum using Prefix Sum

Now let's calculate the sum from index `1` to index `3`.

```
import java.util.*;

public class Main {
    public static void main(String[] args) {
        int[] arr = {2, 4, 6, 8, 10};
        int n = arr.length;

        int[] prefix = new int[n];
        prefix[0] = arr[0];

        for (int i = 1; i < n; i++) {
            prefix[i] = prefix[i - 1] + arr[i];
        }

        int left = 1;
        int right = 3;

        int sum;

        if (left == 0) {
            sum = prefix[right];
        } else {
            sum = prefix[right] - prefix[left - 1];
        }

        System.out.println(sum);
    }
}
```

Output:

```
18
```

Notice the special case: when `left == 0`, there is no preceding prefix to subtract.

## 5. Prefix Sum time complexity

| Operation                  | Without Prefix Sum         | With Prefix Sum |
| -------------------------- | -------------------------- | --------------- |
| Build cumulative sums      | —                          | O(n)            |
| One range-sum query        | O(n)                       | O(1)            |
| Multiple range-sum queries | O(q × n) in the worst case | O(n + q)        |

Here, `n` is the array length and `q` is the number of queries. Prefix sums are especially useful when the array stays unchanged while many range-sum queries are processed.

## 6. Types and categories of Prefix Sum problems

For your DSA notes, organize Prefix Sum into these categories:

1. Basic Prefix Sum — cumulative sums and range-sum queries.
2. Prefix Sum + HashMap — count subarrays with a target sum, find zero-sum subarrays, and find the longest subarray with a target sum.
3. Prefix Sum + HashSet — track previously seen prefix values to detect certain repeated sums.
4. Prefix Sum on Binary Arrays — equal numbers of zeros and ones, and subarrays with a given binary sum.
5. Prefix Sum + Modulo — count subarrays whose sum is divisible by `k`.
6. 2D Prefix Sum — calculate the sum of rectangular regions in a matrix.
7. Prefix Sum + Difference Array — efficiently apply multiple range updates.
8. Prefix Sum + Other Patterns — combine prefix sums with sliding windows, sorting, or binary search where appropriate.

### Important distinction

Prefix Sum and Sliding Window solve some similar problems, but they work differently.

- Prefix Sum: stores cumulative information so range sums can be calculated quickly.
- Sliding Window: maintains a moving contiguous range, updating its state as the boundaries move.
- Prefix Sum + HashMap: often solves subarray problems involving negative numbers or counting all ranges with a particular sum, where the usual sum-based sliding-window approach may fail.