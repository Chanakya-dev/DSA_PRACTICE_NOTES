# Two Pointer Technique — Complete Notes

## 1. Introduction

The Two Pointer Technique is an algorithmic technique in which two variables, called pointers, are used to track positions in a data structure, usually an array, string, or linked list.

In Java, these pointers are generally integer indices that identify the positions of elements.

The main purpose of this technique is to solve problems efficiently by moving two pointers according to specific conditions, often reducing the time complexity compared with a brute-force approach.

For example:

```
int[] arr = {1, 2, 3, 4, 5};

int left = 0;
int right = arr.length - 1;
```

Here, `left` points to the first element, while `right` points to the last element.

The pointers can move toward each other, in the same direction, or independently through different data structures, depending on the problem.

### Main categories

1. Two Pointers in Opposite Direction
2. Two Pointers in Same Direction
3. Two Pointers Each Pointing to a Different Data Structure

### Advantages

- Can reduce time complexity from \\(O(n^2)\\) to \\(O(n)\\) for suitable problems.
- Often requires \\(O(1)\\) extra space.
- Avoids unnecessary comparisons.
- Is widely used in array, string, and linked-list interview problems.

## 2. Two Pointers in Opposite Direction

### Definition

In this approach, one pointer starts at the beginning of an array or string, and the other starts at the end. Both pointers move toward each other according to the problem's conditions.

### Initialization

```
int left = 0;
int right = arr.length - 1;
```

Typical loop condition:

```
while (left < right) {
    // Process elements
}
```

### Example 1: Reverse an array

Input:

```
int[] arr = {10, 20, 30, 40, 50};
```

Code:

```
import java.util.Arrays;

public class Main {
    public static void main(String[] args) {
        int[] arr = {10, 20, 30, 40, 50};

        int left = 0;
        int right = arr.length - 1;

        while (left < right) {
            int temp = arr[left];
            arr[left] = arr[right];
            arr[right] = temp;

            left++;
            right--;
        }

        System.out.println(Arrays.toString(arr));
    }
}
```

Output:

```
[50, 40, 30, 20, 10]
```

Explanation:

1. Swap the first and last elements.
2. Move both pointers inward.
3. Continue until the pointers meet.

Time complexity: \\(O(n)\\)

Space complexity: \\(O(1)\\)

### Example 2: Check whether a string is a palindrome

A palindrome reads the same forward and backward.

```
public class Main {
    public static void main(String[] args) {
        String str = "madam";

        int left = 0;
        int right = str.length() - 1;

        boolean isPalindrome = true;

        while (left < right) {
            if (str.charAt(left) != str.charAt(right)) {
                isPalindrome = false;
                break;
            }

            left++;
            right--;
        }

        System.out.println(isPalindrome);
    }
}
```

Output:

```
true
```

Explanation:

- Compare the characters at both ends.
- If they differ, the string is not a palindrome.
- Otherwise, move both pointers inward.

Time complexity: \\(O(n)\\)

Extra space: \\(O(1)\\)

### Example 3: Find a pair with a target sum

Given a sorted array, find two elements whose sum equals the target.

```
int[] arr = {1, 2, 4, 6, 8, 9};
int target = 10;

int left = 0;
int right = arr.length - 1;

while (left < right) {
    int sum = arr[left] + arr[right];

    if (sum == target) {
        System.out.println(arr[left] + ", " + arr[right]);
        break;
    } else if (sum < target) {
        left++;
    } else {
        right--;
    }
}
```

Output:

```
2, 8
```

Explanation:

- If the sum is smaller than the target, move `left` forward.
- If the sum is larger than the target, move `right` backward.
- If the sum matches the target, the pair is found.

Important: This approach relies on the array being sorted. It does not generally work on an unsorted array without additional processing.

### When to use this category

- Reverse an array or string.
- Check palindromes.
- Find pairs with a target sum in sorted arrays.
- Find pairs with a target difference.
- Container With Most Water.
- Trapping Rain Water.

## 3. Two Pointers in Same Direction

### Definition

In this approach, both pointers move in the same direction, usually from left to right.

They often perform different responsibilities. One pointer scans the data, while the other tracks the position where a valid element should be processed or placed.

Common names are `slow` and `fast`.

### Initialization

```
int slow = 0;
int fast = 0;
```

The exact starting positions depend on the problem. For example, `fast` may start at index `1` if the first element is already considered valid.

### Example 1: Remove duplicates from a sorted array

Input:

```
int[] arr = {1, 1, 2, 2, 3, 4, 4};
```

Expected unique elements:

```
[1, 2, 3, 4]
```

Code:

```
import java.util.Arrays;

public class Main {
    public static void main(String[] args) {
        int[] arr = {1, 1, 2, 2, 3, 4, 4};

        if (arr.length == 0) {
            return;
        }

        int slow = 0;

        for (int fast = 1; fast < arr.length; fast++) {
            if (arr[fast] != arr[slow]) {
                slow++;
                arr[slow] = arr[fast];
            }
        }

        int count = slow + 1;

        System.out.println(Arrays.toString(
            Arrays.copyOf(arr, count)
        ));
    }
}
```

Output:

```
[1, 2, 3, 4]
```

Explanation:

- `fast` scans every element.
- `slow` identifies the position of the last unique element.
- When `fast` finds a new value, `slow` moves forward and the new value is copied into that position.
- The first `slow + 1` positions contain the unique elements.

Time complexity: \\(O(n)\\)

Extra space: \\(O(1)\\) for the in-place algorithm, excluding the array copy used to print the result.

### Example 2: Move zeroes to the end

Input:

```
int[] arr = {0, 1, 0, 3, 12};
```

Expected output:

```
[1, 3, 12, 0, 0]
```

Code:

```
import java.util.Arrays;

public class Main {
    public static void main(String[] args) {
        int[] arr = {0, 1, 0, 3, 12};

        int slow = 0;

        for (int fast = 0; fast < arr.length; fast++) {
            if (arr[fast] != 0) {
                int temp = arr[slow];
                arr[slow] = arr[fast];
                arr[fast] = temp;

                slow++;
            }
        }

        System.out.println(Arrays.toString(arr));
    }
}
```

Output:

```
[1, 3, 12, 0, 0]
```

Explanation:

- `fast` searches for nonzero elements.
- `slow` tracks the next position for a nonzero element.
- When a nonzero value is found, it is moved to the `slow` position.
- The relative order of the nonzero elements is preserved.

Time complexity: \\(O(n)\\)

Space complexity: \\(O(1)\\)

### Example 3: Find the middle of a linked list

This variation uses two pointers moving in the same direction at different speeds.

- `slow` moves one node at a time.
- `fast` moves two nodes at a time.

When `fast` reaches the end, `slow` is at the middle.

```
class ListNode {
    int val;
    ListNode next;

    ListNode(int val) {
        this.val = val;
    }
}

public class Main {
    public static ListNode middleNode(ListNode head) {
        ListNode slow = head;
        ListNode fast = head;

        while (fast != null && fast.next != null) {
            slow = slow.next;
            fast = fast.next.next;
        }

        return slow;
    }
}
```

For a list with an even number of nodes, this implementation returns the second middle node.

Time complexity: \\(O(n)\\)

Space complexity: \\(O(1)\\)

### When to use this category

- Remove duplicates from sorted arrays.
- Move zeroes.
- Remove a specific element in place.
- Partition arrays.
- Find the middle of a linked list.
- Detect cycles in a linked list.

## 4. Two Pointers Each Pointing to a Different Data Structure

### Definition

In this approach, each pointer tracks a position in a different data structure, such as two arrays, two strings, or two linked lists.

The pointers move independently according to the relationship between the current elements.

### Initialization

```
int i = 0;
int j = 0;
```

Here, `i` tracks the first data structure, while `j` tracks the second.

### Example 1: Merge two sorted arrays

Input:

```
int[] a = {1, 3, 5};
int[] b = {2, 4, 6};
```

Expected output:

```
[1, 2, 3, 4, 5, 6]
```

Code:

```
import java.util.Arrays;

public class Main {
    public static void main(String[] args) {
        int[] a = {1, 3, 5};
        int[] b = {2, 4, 6};

        int[] result = new int[a.length + b.length];

        int i = 0;
        int j = 0;
        int k = 0;

        while (i < a.length && j < b.length) {
            if (a[i] <= b[j]) {
                result[k++] = a[i++];
            } else {
                result[k++] = b[j++];
            }
        }

        while (i < a.length) {
            result[k++] = a[i++];
        }

        while (j < b.length) {
            result[k++] = b[j++];
        }

        System.out.println(Arrays.toString(result));
    }
}
```

Explanation:

- `i` points to the current element of array `a`.
- `j` points to the current element of array `b`.
- Compare the two elements and copy the smaller one into `result`.
- Advance the pointer belonging to the array from which the element was copied.
- Once one array is exhausted, append the remaining elements of the other array.

Time complexity: \\(O(n+m)\\)

Extra space: \\(O(n+m)\\) for the result array.

### Example 2: Check whether one string is a subsequence of another

A subsequence preserves the order of characters but does not require them to be contiguous.

Input:

```
String s = "abc";
String t = "ahbgdc";
```

Expected output:

```
true
```

Code:

```
public class Main {
    public static void main(String[] args) {
        String s = "abc";
        String t = "ahbgdc";

        int i = 0;
        int j = 0;

        while (i < s.length() && j < t.length()) {
            if (s.charAt(i) == t.charAt(j)) {
                i++;
            }

            j++;
        }

        System.out.println(i == s.length());
    }
}
```

Explanation:

- `i` tracks the characters of the target subsequence.
- `j` scans the larger string.
- When the characters match, advance both pointers.
- Otherwise, advance only `j`.
- If `i` reaches the end of `s`, every required character has been found in order.

Time complexity: \\(O(n+m)\\), where `n` and `m` are the lengths of the two strings.

Extra space: \\(O(1)\\).

### When to use this category

- Merge two sorted arrays.
- Find common elements in sorted arrays.
- Compare two strings.
- Check whether a string is a subsequence of another.
- Compare two linked lists.
- Merge sorted linked lists.

## 5. Comparison of the Three Categories

| Feature                 | Opposite direction               | Same direction                 | Different data structures              |
| ----------------------- | -------------------------------- | ------------------------------ | -------------------------------------- |
| Pointer initialization  | Beginning and end                | Usually both at beginning      | One at the beginning of each structure |
| Pointer movement        | Toward each other                | Usually forward                | Independent movement                   |
| Main purpose            | Compare or process opposite ends | Scan, filter, or modify        | Compare or combine structures          |
| Typical examples        | Palindrome, sorted Two Sum       | Remove duplicates, move zeroes | Merge arrays, subsequence              |
| Typical time complexity | \\(O(n)\\)                       | \\(O(n)\\)                     | \\(O(n+m)\\)                           |

These are common patterns, not rigid rules. A problem's exact requirements determine how pointers are initialized and moved.

## 6. How to Identify a Two Pointer Problem

When you read a DSA problem, ask yourself:

1. Can I solve it by tracking two positions instead of examining every pair?
2. Is the array sorted, or does it have some other useful structure?
3. Do the pointers need to move toward each other?
4. Do they need to scan in the same direction?
5. Am I comparing two different arrays, strings, or lists?
6. What condition determines which pointer moves?
7. What is the termination condition?

If you can define these rules clearly, you are much closer to building the correct solution.

## 7. Common Mistakes

- Using opposite-direction pointer logic on an unsorted array when the algorithm depends on sorted order.
- Moving both pointers when only one should move.
- Using the wrong loop condition and skipping valid elements.
- Forgetting empty arrays or single-element arrays.
- Confusing a contiguous subarray with a subsequence.
- Ignoring duplicates when the problem requires unique pairs.
- Failing to analyze the total pointer movements when calculating complexity.

## 8. Recommended Problem Order

Practice the problems in this order:

Opposite direction

1. Reverse an array.
2. Valid Palindrome.
3. Two Sum II — Input Array Is Sorted.
4. Container With Most Water.
5. 3Sum.

Same direction

1. Remove Duplicates from Sorted Array.
2. Move Zeroes.
3. Remove Element.
4. Middle of the Linked List.
5. Linked List Cycle.

Different data structures

1. Merge Sorted Array.
2. Is Subsequence.
3. Intersection of Two Sorted Arrays.
4. Merge Two Sorted Lists.
5. Compare Version Numbers.

## Final takeaway

The Two Pointer Technique is a family of approaches, not a single algorithm. Its effectiveness comes from defining what each pointer represents and establishing a correct rule for moving it.

For every problem, document the pointer initialization, movement conditions, termination condition, dry run, and time and space complexity. This will help you build a structured DSA notebook and recognize the appropriate pattern during interviews.