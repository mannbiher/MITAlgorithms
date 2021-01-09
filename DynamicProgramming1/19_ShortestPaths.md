# Shortest Paths

S(s,v) 

Use Guessing
Try all guesses (and take the best one)

DP ~= recursion + memoization + guessing

guessing == brute force

s -> O --> O --> O --> v

1. Guess last edges: One of incoming edges to V.
2. Recursively solve the shortest path from S to v
3. Min((s,u)) + w(u,v)

Exponential Algorithm. Memoize.
Is it a good algorithm.

Base case delta(s,s) = 0

```
  /<------- a --------> \
 s          ^            v
 \          |           /
  \-------> b <--------/

                                        |--- delta(s,s)
delta(s,v) => delta(s,a) ==> delta(s,b) |
                                        |--- delta(s,v)

```
Infinite time or graphs with cycle.

for DAGs O(V+E)

Time for subprob delta(s,v)
=> Total time = sum(in_degree(v)) = O(E)

Bellmen Ford?

Lessons Learned: Subproblem dependencies should be asyclic

Can we apply on cyclic graph? Make it asyclic.

1. Explode the graphs in layers
2. Each layer edges goes down

delta_k (s,v) => shortest weight of s to v path that uses <= k edges

Recurrence:
delta_k(s,v) = min(delta_k-1(s,u)+w(u,v))

Increased the subproblems V^2
Total Running Algorithm O(VE)
Bellman Ford Algorithm