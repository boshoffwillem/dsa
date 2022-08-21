# Types of Data Structure

Basically, data structures are divided into two categories:

- Linear data structure
- Non-linear data structure

## Linear data structures

1. Array Data Structure
2. Stack Data Structure
3. Stack Data Structure
4. Linked List Data Structure

## Non-linear data structures

1. Graph Data Structure
   - Spanning Tree and Minimum Spanning Tree
   - Strongly Connected Components
   - Adjacency Matrix
   - Adjacency List
2. Tree Data Structure
   - Binary Tree
   - Binary Search Tree
   - AVL Tree
   - B-Tree
   - B+ Tree
   - Red-Black Tree

## Asymptotic Analysis

The study of change in performance of the algorithm with the change in the
order of the input size is defined as asymptotic analysis.

### Asymptotic Notations

Asymptotic notations are the mathematical notations used to describe the
running time of an algorithm when the input tends towards
a particular value or a limiting value.

For example: In bubble sort, when the input array is already sorted,
the time taken by the algorithm is linear i.e. the best case.

But, when the input array is in reverse condition, the algorithm takes
the maximum time (quadratic) to sort the elements i.e. the worst case.

When the input array is neither sorted nor in reverse order,
then it takes average time. These durations are denoted using asymptotic notations.

There are mainly three asymptotic notations:

- Big-O notation
- Omega notation
- Theta notation

### Big-O Notation (O-notation)

Big-O notation represents the upper bound of the running time of an algorithm.
Thus, it gives the worst-case complexity of an algorithm.

### Omega Notation (Ω-notation)

Omega notation represents the lower bound of the running time of an algorithm.
Thus, it provides the best case complexity of an algorithm.

### Theta Notation (Θ-notation)

Theta notation encloses the function from above and below.
Since it represents the upper and the lower bound of the running time
of an algorithm, it is used for analyzing the average-case complexity
of an algorithm.

## Master Theorem

The master theorem is used in calculating the time complexity of
recurrence relations (divide and conquer algorithms)
in a simple and quick way.

## Divide and Conquer Algorithm

A divide and conquer algorithm is a strategy of solving a large problem by

1. breaking the problem into smaller sub-problems
2. solving the sub-problems, and
3. combining them to get the desired output.

To use the divide and conquer algorithm, recursion is used.

### How Divide and Conquer Algorithms Work?

Here are the steps involved:

1. **Divide**: Divide the given problem into sub-problems using recursion.
2. **Conquer**: Solve the smaller sub-problems recursively.
If the subproblem is small enough, then solve it directly.
3. **Combine**: Combine the solutions of the sub-problems that are part of
the recursive process to solve the actual problem.

The complexity of the divide and conquer algorithm
is calculated using the master theorem.

```text
T(n) = aT(n/b) + f(n),
where,
n = size of input
a = number of subproblems in the recursion
n/b = size of each subproblem. All subproblems are assumed to have the same size.
f(n) = cost of the work done outside the recursive call,
which includes the cost of dividing the problem and cost of merging the solutions
```

Let us take an example to find the time complexity of a recursive problem.
For a merge sort, the equation can be written as:

```text
T(n) = aT(n/b) + f(n)
     = 2T(n/2) + O(n)
Where,
a = 2 (each time, a problem is divided into 2 subproblems)
n/b = n/2 (size of each sub problem is half of the input)
f(n) = time taken to divide the problem and merging the subproblems
T(n/2) = O(n log n) (To understand this, please refer to the master theorem.)

Now, T(n) = 2T(n log n) + O(n)
          ≈ O(n log n)
```
