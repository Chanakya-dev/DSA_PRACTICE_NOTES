# Introduction to Recursion

## 1. What is Recursion?

Recursion is a programming technique in which a method calls itself to solve a problem by breaking it into smaller subproblems until it reaches a stopping condition.

In Java, a recursive method calls itself with a modified argument until a base condition is satisfied.

## 2. Key Components of Recursion

1. Base Case: The condition that stops recursive calls.
2. Recursive Case: The part where the method calls itself.
3. Progress Toward the Base Case: Each recursive call should move toward a condition that eventually stops recursion.

## 3. How Recursion Works

Example: Print numbers from 1 to 5.

```
public class Main {

    static void printNumbers(int n) {
        if (n == 6) {       // Base case
            return;
        }

        System.out.println(n);

        printNumbers(n + 1); // Recursive call
    }

    public static void main(String[] args) {
        printNumbers(1);
    }
}
```

Output:

```
1
2
3
4
5
```

Execution flow:

printNumbers(1)

printNumbers(2)

printNumbers(3)

printNumbers(4)

printNumbers(5)

printNumbers(6)

Base case reached → return

Each method call waits for the next call to finish. In this example, the base case stops further calls.

## 4. What Happens Internally?

Java uses a call stack to keep track of active method calls.

For example, with `printNumbers(1)`:

- `printNumbers(1)` calls `printNumbers(2)`.
- `printNumbers(2)` calls `printNumbers(3)`.
- This continues until `printNumbers(6)` returns.
- The previous calls then finish and return in reverse order.

If recursion continues without reaching a base case, the program may throw a `StackOverflowError`.

## 5. Types of Recursion

Learn these categories in order:

1. Direct Recursion — a method calls itself directly.
2. Indirect Recursion — one method calls another, which eventually calls the first.
3. Tail Recursion — the recursive call is the final operation in the method.
4. Non-Tail Recursion — some work remains after the recursive call returns.
5. Multiple Recursion — a method makes multiple recursive calls, such as Fibonacci.
6. Tree Recursion — recursive calls branch into a tree of calls.

These categories can overlap; for example, tree recursion is often a form of multiple recursion.

## 6. Where Is Recursion Used?

- Factorial and Fibonacci problems
- Reversing strings and processing arrays recursively
- Binary search
- Tree traversal
- Divide and conquer algorithms
- Backtracking problems, such as permutations and combinations
- Dynamic programming problems

## 7. Advantages and Disadvantages

| Advantages                                          | Disadvantages                     |
| --------------------------------------------------- | --------------------------------- |
| Can make complex logic easier to express            | Uses additional call-stack memory |
| Natural for tree-shaped problems                    | May cause `StackOverflowError`    |
| Helps implement backtracking and divide and conquer | Can repeat work unnecessarily     |
| Often produces concise code                         | Can be harder to debug initially  |

## 8. Recommended Learning Sequence for Recursion

For your Java DSA notes, study recursion in this order:

1. Recursion fundamentals and base cases
2. Understanding the call stack
3. Tracing recursive execution
4. Printing sequences using recursion
5. Sum of numbers and factorial
6. Problems involving digits of a number
7. Array and string recursion
8. Tail and non-tail recursion
9. Multiple and tree recursion
10. Recursion time and space complexity
11. Recursion versus iteration
12. Recursion problems that prepare you for backtracking

Important: Before starting backtracking, you should be comfortable tracing recursive calls on paper, identifying base cases, and understanding how method calls return. These skills will make backtracking much easier to learn.