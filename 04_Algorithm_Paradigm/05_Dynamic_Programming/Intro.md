# Introduction to Dynamic Programming (DP)

## 1. What is Dynamic Programming?

Dynamic Programming (DP) is an algorithmic technique used to solve complex problems by breaking them into smaller subproblems, solving each subproblem once, and storing its result so that it can be reused whenever needed.

In simple words, Dynamic Programming avoids repeating the same calculations by remembering previously computed results.

It is especially useful for optimization problems involving finding the minimum, maximum, number of ways, or best possible solution.

## 2. Why Do We Need Dynamic Programming?

Consider the problem of finding the \\(n\\)-th Fibonacci number.

The Fibonacci sequence is:

`0, 1, 1, 2, 3, 5, 8, 13, 21, ...`

The formula is:

\\[ F(n)=F(n-1)+F(n-2) \\]

A simple recursive solution repeatedly calculates the same Fibonacci values.

For example, calculating `fib(5)` requires `fib(3)` through multiple recursive paths.

### Recursive approach without DP

fib(5)

fib(4)

fib(3) + fib(2)

fib(3)

fib(2) + fib(1)

Repeated subproblems are calculated multiple times.

Dynamic Programming solves each required Fibonacci subproblem once and stores the answer.

For example:

- `fib(2) = 1`
- `fib(3) = 2`
- `fib(4) = 3`
- `fib(5) = 5`

This avoids unnecessary repeated calculations.

## 3. The Two Main Properties of Dynamic Programming

### 1. Overlapping Subproblems

A problem has overlapping subproblems when the same smaller problems are solved repeatedly during the computation.

Example: In the Fibonacci problem, `fib(3)` and `fib(2)` are needed in multiple places.

DP stores their results and reuses them.

### 2. Optimal Substructure

A problem has optimal substructure when its overall optimal solution can be constructed from optimal solutions to its smaller subproblems.

Example: In the minimum-cost path problem, the minimum cost to reach a cell can be calculated using the minimum costs of its valid preceding cells.

Note: Many DP problems have both properties, but overlapping subproblems and optimal substructure are different concepts. Not every problem with optimal substructure requires DP.

## 4. Two Approaches to Dynamic Programming

[Programming Blog & Tutorials - Unwired Learning](https://images.openai.com/static-rsc-4/HQ0GVA5ZSOj47RX7UmbznxLt7iQVG5-XXxC69hxhmFkpyHXkl6eEW4C5QMA2eT-omgvacIziokLVENQhdzObirj4nDML1linC5a7oydc99ZBHymg5Pba19ns-l-H-fRh-xxC-4pIZa9_32ceG_q1Gqs902IM161IWNMWcC6tsKc?purpose=inline)

1\. Top-Down Approach (Memoization)

- Start with the original problem.
- Solve smaller subproblems recursively.
- Store each computed result.
- Reuse stored results when the same subproblem appears again.

[Dynamic Programming: A Handbook. Rethinking Recursion Through the Lens… | by Tomio Kobayashi | Dec, 2025 | Medium](https://images.openai.com/static-rsc-4/07xVz_74qXvzkYRHJM82aCDAi2kXS1XX7bxRVJ1g3sil9_t8K9N0q7Kq084bM9s3xSGGUo8GrbH1xzJR23XTwm5jnAvORlnDJtQEJZCTTLTXTr17f-HX1Mb9JiUXoecN_jJO1_FJeC-2B0ibE-qgQ1H-_Ia2sRTfegvRC_0zkWU?purpose=inline)

2\. Bottom-Up Approach (Tabulation)

- Start with the smallest subproblems.
- Store their answers in an array or table.
- Build larger answers using previously calculated results.
- Usually implemented using loops instead of recursion.

## 5. Example in Java

The following example calculates the Fibonacci number using bottom-up DP.

```
public class Main {
    public static void main(String[] args) {
        int n = 6;

        int[] dp = new int[n + 1];

        dp[0] = 0;
        dp[1] = 1;

        for (int i = 2; i <= n; i++) {
            dp[i] = dp[i - 1] + dp[i - 2];
        }

        System.out.println(dp[n]); // 8
    }
}
```

Here, `dp[i]` stores the Fibonacci number at position `i`.

- `dp[0]` and `dp[1]` are the base cases.
- Each subsequent value uses the two previously calculated values.
- Every Fibonacci value is calculated only once.

Time complexity: \\(O(n)\\)

Space complexity: \\(O(n)\\)

## 6. Dynamic Programming vs. Other Techniques

| Technique           | Main idea                                                      |
| ------------------- | -------------------------------------------------------------- |
| Brute Force         | Try possible solutions, often exhaustively                     |
| Recursion           | Solve a problem by calling the same function on smaller inputs |
| Divide and Conquer  | Divide into subproblems and combine their results              |
| Greedy              | Make the best immediate choice at each step                    |
| Dynamic Programming | Store and reuse results of overlapping subproblems             |
| Backtracking        | Explore choices and undo them when necessary                   |

Recursion and DP are not mutually exclusive. DP can use recursion with memoization or iteration with tabulation.

## 7. Common Applications of Dynamic Programming

- Fibonacci numbers
- Climbing Stairs
- 0/1 Knapsack
- Coin Change
- Longest Common Subsequence (LCS)
- Longest Increasing Subsequence (LIS)
- Edit Distance
- Subset Sum
- Rod Cutting
- Matrix Chain Multiplication
- Unique Paths
- House Robber
- Word Break
- Palindromic Substrings and subsequences
- DP on Trees
- DP on Graphs and bitmasks

## 8. How to Identify a DP Problem

Look for these clues:

1. The problem asks for a minimum, maximum, or number of possible ways.
2. The same subproblems appear repeatedly.
3. A larger problem can be expressed using smaller subproblems.
4. You can define a meaningful state, such as `dp[i]` or `dp[i][j]`.
5. You can establish base cases and a recurrence relation.

Not every minimum or maximum problem is a DP problem; greedy algorithms or other techniques may be more suitable.

## 9. Recommended Learning Order

For your DSA preparation, learn Dynamic Programming in this order:

1. Recursion fundamentals
2. Recursion tree and repeated subproblems
3. Memoization (top-down DP)
4. Tabulation (bottom-up DP)
5. Space optimization
6. One-dimensional DP
7. Two-dimensional DP
8. Knapsack patterns
9. Subsequences and string DP
10. Grid-based DP
11. Interval DP
12. DP on trees
13. Bitmask DP
14. Advanced DP and state optimization

Key takeaway: Dynamic Programming is not simply breaking a problem into smaller parts. Its central idea is to identify reusable subproblems, define their states, and store their results to avoid redundant work.