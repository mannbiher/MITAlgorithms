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


