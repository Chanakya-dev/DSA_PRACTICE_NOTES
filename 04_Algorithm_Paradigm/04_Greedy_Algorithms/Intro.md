# Introduction to Greedy Algorithms

## 1. What is a Greedy Algorithm?

A Greedy Algorithm is an algorithmic technique that solves a problem by making the best possible choice at each step, hoping that these locally optimal choices lead to the overall optimal solution.

In simple words, a greedy algorithm chooses what looks best at the current moment without reconsidering previous choices.

Once a choice is made, it is generally not changed.

## 2. How Does a Greedy Algorithm Work?

A greedy algorithm typically follows these steps:

1. Identify all available choices at the current step.
2. Select the choice that looks best according to the problem's criteria.
3. Check whether the choice is valid.
4. Add the choice to the solution.
5. Repeat until the solution is complete or no more valid choices exist.

## 3. Simple Example

Suppose you have coins of denominations ₹1, ₹2, ₹5, and ₹10, and you need to make ₹18 using the minimum number of coins.

A greedy approach always selects the largest coin that does not exceed the remaining amount.

| Step | Remaining amount | Coin selected              |
| ---- | ---------------- | -------------------------- |
| 1    | ₹18              | ₹10                        |
| 2    | ₹8               | ₹5                         |
| 3    | ₹3               | ₹2                         |
| 4    | ₹1               | ₹2 is too large, select ₹1 |
| 5    | ₹0               | Complete                   |

The selected coins are ₹10, ₹5, ₹2, and ₹1, giving a total of ₹18 using 4 coins.

Notice that the algorithm makes the best available choice at each step rather than exploring every possible combination.

## 4. Important Properties of Greedy Algorithms

1\. Greedy Choice Property

A globally optimal solution can be reached by making an appropriate locally optimal choice at each step.

2\. Optimal Substructure

An optimal solution to a problem can be constructed using optimal solutions to its smaller subproblems.

3\. Irrevocable Choices

In a typical greedy algorithm, once a choice is made, the algorithm does not go back and change it.

Important: Greedy algorithms do not always produce the optimal solution. Their correctness depends on the problem. For example, the coin-selection strategy above does not work for every possible coin denomination system.

## 5. Common Applications of Greedy Algorithms

- Activity Selection Problem
- Fractional Knapsack Problem
- Job Sequencing with Deadlines
- Minimum Spanning Tree — Kruskal's Algorithm
- Minimum Spanning Tree — Prim's Algorithm
- Dijkstra's Shortest Path Algorithm (with non-negative edge weights)
- Huffman Coding
- Interval Scheduling
- Meeting Rooms and Scheduling Problems
- Minimum Number of Platforms

## 6. Greedy vs. Other Algorithmic Techniques

| Technique           | Main approach                                            |
| ------------------- | -------------------------------------------------------- |
| Brute Force         | Explore possible solutions                               |
| Recursion           | Solve a problem through smaller instances of itself      |
| Divide and Conquer  | Divide into subproblems, solve them, and combine results |
| Greedy              | Make the best immediate choice                           |
| Dynamic Programming | Store and reuse solutions to overlapping subproblems     |
| Backtracking        | Explore choices and undo them when they fail             |

## 7. When Should You Use a Greedy Algorithm?

Consider a greedy approach when:

- The problem asks for a minimum or maximum result.
- You can identify a clear rule for choosing the next best option.
- Each choice can be made without needing to revise earlier choices.
- You can prove that these choices lead to an optimal solution.

The most important lesson: A choice that looks best right now is not necessarily the best choice for the entire problem. You must prove that the greedy strategy works before relying on it.