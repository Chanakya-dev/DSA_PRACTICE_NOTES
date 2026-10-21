# Introduction to Backtracking

## 1. What is Backtracking?

Backtracking is an algorithmic problem-solving technique that builds a solution step by step, explores possible choices, and reverses a choice when it cannot lead to a valid or desired solution.

It is commonly used when a problem requires exploring multiple possibilities to find one or more valid solutions.

Backtracking is often implemented using recursion.

## 2. Core Principles of Backtracking

1. Choose: Select one possible option.
2. Explore: Recursively continue building the solution.
3. Check: Determine whether the current solution is complete or invalid.
4. Undo: Reverse the previous choice and try another option.

The common pattern is:

`Choose → Explore → Undo`

## 3. How Backtracking Works

Example: Generate all binary strings of length 2.

The possible strings are `00`, `01`, `10`, and `11`.

Start

Empty string: ""

Choose 0

First position

`00` `01`

Choose 1

First position

`10` `11`

Each branch explores the next position, then returns to try another choice.

Once a string reaches length 2, it is complete. The algorithm returns and explores any remaining choices.

## 4. Java Example

```
public class Main {

    static void generate(String str, int n) {
        if (str.length() == n) {
            System.out.println(str);
            return;
        }

        // Choose 0
        generate(str + "0", n);

        // Choose 1
        generate(str + "1", n);
    }

    public static void main(String[] args) {
        generate("", 2);
    }
}
```

Output:

```
00
01
10
11
```

In this example, each recursive call explores a different choice. Since strings are immutable in Java, adding a character creates a new string rather than modifying and undoing the existing one. In other backtracking problems, such as subsets or permutations, you will often explicitly remove an element to undo a choice.

## 5. Important Components of Backtracking

- State: The current partial solution.
- Choices: The possible decisions available at each step.
- Constraints: Rules that determine whether a choice is allowed.
- Base case: The condition for completing or stopping a branch.
- Pruning: Skipping a branch that cannot produce a valid solution.
- Undo operation: Restoring the previous state before trying another choice.

## 6. Where Is Backtracking Used?

1. Generating subsets and subsequences.
2. Generating permutations and combinations.
3. Solving Sudoku.
4. Solving N-Queens.
5. Finding paths through mazes.
6. Word Search problems.
7. Graph coloring.
8. Finding combinations that satisfy a target sum.

## 7. Backtracking vs Recursion

| Recursion                          | Backtracking                                          |
| ---------------------------------- | ----------------------------------------------------- |
| A method calls itself.             | A problem-solving approach explores choices.          |
| May follow a single path of calls. | Typically explores alternative paths.                 |
| Does not require undoing choices.  | Usually undoes choices before exploring alternatives. |
| Example: factorial.                | Example: generating permutations.                     |

Remember: Backtracking commonly uses recursion, but recursion alone does not mean a program uses backtracking.

## 8. Recommended Learning Order

For your Java DSA preparation, learn backtracking in this order:

1. Understand the choose–explore–undo pattern.
2. Generate binary strings.
3. Generate subsets.
4. Generate subsequences.
5. Generate permutations.
6. Generate combinations.
7. Solve subset sum and Combination Sum.
8. Solve string partitioning problems.
9. Solve maze and grid problems.
10. Solve N-Queens and Sudoku.
11. Learn pruning and optimization techniques.

The most important skill is learning to identify what choice to make, when to stop, and how to restore the previous state before exploring the next possibility.