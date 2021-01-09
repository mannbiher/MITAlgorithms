# Dynamic Programming
General Powerful algorithm design technique

Kind of exhaustive search Exponential search. DP gives polynomial time 

DP ~= Careful bruteforce

Why? Dynamic Programming => origin sounded cool :)

DP ~= Subproblems + reuse solution

## Example Fibonacci Numbers

### Naive recursive algorithm

```python
def fib(n):
	if n<=2: f=1
	else: f=fib(n-1)+fib(n-2)
	return f
```

Exponential Time Algorithm

T(n) = T(n-1)+T(n-2) + O(1)
     = Fn ~= Golden Ration ^ n

    >= 2T(n-2) = Theta(2^(n/2))

### Memoization DP
```python
memo = {}
def fib(n):
	if n in memo: return memo
	if n<=2:f=1
	else: f=fib(n-1)+fib(n-2)
	memo[n] =f
	return f
```

Recursion Tree:

                 |- f(n-2)
     |--f(n-1) --|- f(n-3)
fn---|
     |--f(n-2) --|- f(n-3)
	          |- f(n-4)

Complexity

fib(k) recurses only first time it is called.
1. memoized calls cost O(1)
2. Number of non-memoized calls is n

If you don't count recursion. running time is linear O(n)

DP

- memoize (remember) and reuse solutions to subproblems that solve the actual problem
- recursion ~= memoization
- Running time = number of subproblems * (amount of time for each subproblem)
- Don't count memoize recursion

## Bottom up DP Algorithm

```python
fib = {}
for k in range(1,n+1):
    if k<=2: f=1
    else: f=fib[k-1]+fib[k-2]
    fib[k] = f
return fib[n]
```

### General Case

- Exactly same computation
- Topologic sort of subproblem dependency DAG

 |-------->-------\ /------>-------\
Fn-4 --> Fn-3 --> Fn-2 --> Fn-1 --> Fn
          \--------->-------/

- Can often save space
E.g. can store only last two values