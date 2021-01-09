# Dynamic Programming
General Powerful algorithm design technique

Kind of exhaustive search Exponential search. DP gives polynomial time 

DP ~= Careful bruteforce

Why? Dynamic Programming => origin sounded cool :)

DP ~= Subproblems + reuse solution

## Example Fibonacci Numbers

Naive recursive algo

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


