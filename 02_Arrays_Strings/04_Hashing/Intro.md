# Hashing — Introduction

## 1. What is Hashing?

Hashing is a technique used to store, search, insert, and delete data efficiently using a key.

In Java, hashing is commonly used through `HashMap`, `HashSet`, and other hash-based collections.

For example, suppose you have an array:

```
int[] arr = {10, 20, 30, 40, 50};
```

You want to check whether the number `40` exists.

- Without hashing, you may need to check every element one by one.
- With a hash-based data structure, you can usually find the element in O(1) average time.

## 2. Why do we need Hashing?

Hashing is useful when a problem requires you to:

- Find how many times an element occurs.
- Check whether an element exists.
- Find duplicate elements.
- Find pairs that satisfy a target sum.
- Group elements based on a common property.
- Track character frequencies in a string.
- Find elements appearing only once.
- Store key-value pairs for fast lookup.

## 3. How does Hashing work?

Hashing uses a hash function to convert a key into a hash value, which helps determine where the data should be stored.

Input key

## 42

Hash function

Converts the key into a hash value

Hash table

Uses the hash value to determine the storage location

Conceptually, a simple hash function could be:

\\[ h(key)=key\ \\%\ 10 \\]

For example:

\\[ h(42)=42\ \\%\ 10=2 \\]

The key `42` maps to index `2` in this simplified example. Real Java hashing involves additional steps; `HashMap` does not simply use this formula.

## 4. Hashing example in Java

Let's count the frequency of each number in an array using `HashMap`.

```
import java.util.*;

public class Main {
    public static void main(String[] args) {
        int[] arr = {10, 20, 10, 30, 20, 10};

        Map<Integer, Integer> frequency = new HashMap<>();

        for (int num : arr) {
            frequency.put(
                num,
                frequency.getOrDefault(num, 0) + 1
            );
        }

        System.out.println(frequency);
    }
}
```

Possible output:

```
{20=2, 10=3, 30=1}
```

Explanation:

- `10` occurs three times.
- `20` occurs twice.
- `30` occurs once.
- The key represents the element, and the value represents its frequency.

The order of elements in a `HashMap` is not guaranteed.

## 5. Important Hashing concepts

These are the foundational concepts you should learn before solving hashing-based DSA problems.

| Concept            | Meaning                                                   |
| ------------------ | --------------------------------------------------------- |
| Hash function      | Converts a key into a hash value                          |
| Hash table         | Data structure used to store hashed entries               |
| Hash value         | Value calculated from a key                               |
| Bucket             | Storage location used by a hash table                     |
| Collision          | Two keys map to the same bucket                           |
| Collision handling | Method used to manage collisions                          |
| Load factor        | Measure used to determine when a hash table should resize |
| Rehashing/resizing | Redistributing entries when the table grows               |
| Key equality       | Determines whether two keys represent the same mapping    |
| Frequency counting | Counting occurrences using a map                          |

## 6. Hashing in Java Collections

`HashMap<K, V>`

Stores key-value pairs.

Example: `number → frequency`

Typical average lookup: O(1)

`HashSet<E>`

Stores unique elements.

Example: checking whether a duplicate exists.

Typical average search: O(1)

`LinkedHashMap<K, V>` and `LinkedHashSet<E>`

Hash-based collections that also maintain insertion order.

`TreeMap<K, V>` and `TreeSet<E>`

Maintain sorted keys or elements. These use tree-based ordering rather than hashing.

## 7. Time complexity of hashing

| Operation | Average case | Worst case |
| --------- | ------------ | ---------- |
| Insert    | O(1)         | O(n)       |
| Search    | O(1)         | O(n)       |
| Delete    | O(1)         | O(n)       |

These are general bounds for hash-based operations. Java's `HashMap` can use balanced trees for heavily collided buckets, improving some worst-case behavior.

## 8. Categories of Hashing problems for DSA

For your notes, organize hashing into these categories:

1. Frequency Counting — count occurrences of numbers or characters.
2. Duplicate Detection — find repeated or unique elements.
3. Lookup and Membership — quickly check whether an element exists.
4. Two Sum and Pair Problems — find pairs using a target or condition.
5. Subarray Sum with Prefix Sum + HashMap — count or find subarrays satisfying sum conditions.
6. String Hashing Patterns — anagrams, character frequencies, and matching.
7. Grouping Problems — group anagrams or elements with common properties.
8. Set-Based Problems — longest consecutive sequence and unique elements.
9. Advanced Map Problems — multiple frequency constraints and complex lookups.
10. Hashing Internals — `hashCode()`, `equals()`, collisions, buckets, resizing, and load factor.