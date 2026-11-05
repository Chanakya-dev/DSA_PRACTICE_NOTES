# 1. Understanding recursion

Recursion is a programming technique in which a method calls itself until a specific condition is satisfied.

Every recursive method generally has two parts:

1. Base Case: Defines when recursion must stop.
2. Recursive Case: Defines how the problem is reduced into a smaller problem.

Consider:

```
public static int factorial(int num) {

    if (num == 1) {
        return 1;
    }

    return num * factorial(num - 1);
}
```

Let's understand each part.

### Base case

```
if (num == 1) {
    return 1;
}
```

Why do we need this?

Imagine that we don't have this condition.

```
return num * factorial(num - 1);
```

Then Java will keep calling:

```
factorial(5)
factorial(4)
factorial(3)
factorial(2)
factorial(1)
factorial(0)
factorial(-1)
factorial(-2)
...
```

It will never stop.

Eventually, Java will throw a `StackOverflowError` because the call stack has exceeded its capacity.

Therefore, the base case is essential.

### Recursive case

```
return num * factorial(num - 1);
```

This is where we break a bigger problem into a smaller problem.

Mathematically:

\\[ 5! = 5 \times 4! \\]

\\[ 4! = 4 \times 3! \\]

\\[ 3! = 3 \times 2! \\]

\\[ 2! = 2 \times 1! \\]

We are not calculating the entire factorial in one execution.

Instead, we are asking the same method to calculate a smaller factorial.

# 2. Understanding the call stack

This is probably the most important concept to understand before moving into backtracking.

Let's assume we execute:

```
public static void main(String[] args) {
    int result = factorial(5);
    System.out.println(result);
}
```

When Java executes `factorial(5)`, it creates a stack frame for that method call.

Each stack frame maintains its own local variables and execution state.

For example:

- `factorial(5)` has its own `num = 5`.
- `factorial(4)` has its own `num = 4`.
- `factorial(3)` has its own `num = 3`.

These are separate method executions.

## Phase 1: Stack building (recursive calls)

Let's execute the code step by step.

Step 1: factorial(5)

```
return 5 * factorial(4);
```

Java cannot calculate the final result yet.

Why?

Because it needs the return value of `factorial(4)`.

So it pauses this execution and moves into `factorial(4)`.

Step 2: factorial(4)

```
return 4 * factorial(3);
```

Again, Java needs the result of `factorial(3)`.

So it pauses this execution.

Step 3: factorial(3)

```
return 3 * factorial(2);
```

Again, Java needs the result of `factorial(2)`.

Step 4: factorial(2)

```
return 2 * factorial(1);
```

Now Java needs `factorial(1)`.

Step 5: factorial(1)

```
if (num == 1) {
    return 1;
}
```

Base case reached

Finally, the method returns `1`.

Let's visualize the stack.

Call stack — before reaching the base case

factorial(1)

Base case: return 1

factorial(2)

Waiting for factorial(1)

factorial(3)

Waiting for factorial(2)

factorial(4)

Waiting for factorial(3)

factorial(5)

Waiting for factorial(4)

Each method call is waiting for the next method to return.

Notice something important:

`factorial(5)` has not completed yet.

It is still waiting for the result of `factorial(4)`.

This is exactly what you described as the call stack.

# 3. Phase 2: Stack unwinding (returning from recursive calls)

Now comes the interesting part.

We have reached:

```
factorial(1) = 1;
```

Java starts returning to the previous method call.

Remember, Java follows the LIFO principle:

Last In, First Out.

The last method called is the first method to finish.

Let's see how the pending calculations get completed.

## Stack unwinding

1. factorial(1)

   Base case returns `1`.
   # 1
2. factorial(2)

   Previously waiting at:

   `return 2 * factorial(1);`

   Now:

   `2 * 1 = 2`
   # 2
3. factorial(3)

   Previously waiting at:

   `return 3 * factorial(2);`

   Now:

   `3 * 2 = 6`
   # 6
4. factorial(4)

   Previously waiting at:

   `return 4 * factorial(3);`

   Now:

   `4 * 6 = 24`
   # 24
5. factorial(5)

   Previously waiting at:

   `return 5 * factorial(4);`

   Now:

   `5 * 24 = 120`
   # 120

Finally:

```
System.out.println(result);
```

Output:

```
120
```

This is called stack unwinding.

# 4. Understand what happens to the execution pointer

There is another important concept.

Look at this statement:

```
return num * factorial(num - 1);
```

Suppose we execute:

```
factorial(3);
```

Java encounters the following:

```
return 3 * factorial(2);
```

At this point, Java remembers:

- Current value of `num` is 3.
- It needs to multiply 3 by the result of `factorial(2)`.
- The multiplication cannot finish until `factorial(2)` returns.

After `factorial(2)` returns 2, Java resumes the pending operation:

```
return 3 * 2;
```

It returns 6.

Important: Java does not restart the method from the beginning when a recursive call returns. It resumes the suspended method execution at the pending operation.

This is why understanding stack frames is so important.

# 5. Recursion has two directions

Remember this distinction throughout your DSA preparation.

Going down

Recursive calls are created.

5 → 4 → 3 → 2 → 1

Coming back up

Pending calculations complete.

1 → 2 → 6 → 24 → 120

This concept will become extremely important when we study:

- Subsets
- Permutations
- Combination Sum
- N-Queens

Because in backtracking, we will use recursion to explore possibilities and then undo our choices when returning.

# 6. Let's understand recursion using another example

Now let's take a slightly different problem.

Find the sum of numbers from 1 to N.

Mathematically:

\\[ Sum(5) = 5+4+3+2+1 = 15 \\]

Java implementation:

```
public class Main {

    public static int sum(int n) {

        if (n == 0) {
            return 0;
        }

        return n + sum(n - 1);
    }

    public static void main(String[] args) {

        System.out.println(sum(5));
    }
}
```

Here:

```
return n + sum(n - 1);
```

Notice the difference from factorial:

- Factorial uses multiplication.
- Sum uses addition.

But the recursion mechanism is exactly the same.

| Call   | Pending operation |
| ------ | ----------------- |
| sum(5) | 5 + ?             |
| sum(4) | 4 + ?             |
| sum(3) | 3 + ?             |
| sum(2) | 2 + ?             |
| sum(1) | 1 + ?             |
| sum(0) | Return 0          |

Unwinding:

```
sum(0) = 0
sum(1) = 1 + 0 = 1
sum(2) = 2 + 1 = 3
sum(3) = 3 + 3 = 6
sum(4) = 4 + 6 = 10
sum(5) = 5 + 10 = 15
```

Output: `15`

# 7. Important recursion concepts you must understand

Before moving into backtracking, let's establish these concepts.

| Concept                  | What you should understand                      |
| ------------------------ | ----------------------------------------------- |
| Base case                | When recursion stops                            |
| Recursive case           | How the problem becomes smaller                 |
| Call stack               | How method calls are maintained                 |
| Stack frame              | Each call's local variables and execution state |
| Stack unwinding          | How pending calls return                        |
| Recursion tree           | Visual representation of recursive calls        |
| Multiple recursive calls | A method calling itself more than once          |
| Return vs void           | Returning results versus performing actions     |

One more distinction: Recursion does not always mean that we return a calculated value. Some recursive methods use `void` and simply perform operations.
