# 1	fundamentals
## 1.1	definition
- a method that calls itself to solve a smaller instance of the same problem
## 1.2	key components
- base case: the simpelest scenario where the problem can be solved without further recutison
- recursive case: where the methods calls itself with a simpler or smaller input
## 1.3	how
- problem is broken into subproblems
- subproblems are solved recursively
- solutions are combined to solve the original problem
## 1.4	advantages
- cleaner, intuitive code
- suited for trees, fractals, etc...
## 1.5	disadvantages
- less efficient due to function call overhead
- risk of stack overfow
# 2	example
- write a recursive method `calc` that finds the number of arithmetic expressions that can be formed using a given number `num` to reach a targer `result`, using at most `maxOp` operations
1. base cases
	- `if maxOp = 0 && num = result, return 1` valid expression
	- `if maxOp = 0 && num != result, return 0` invalid expression
2. recursive case
	- try each operation with the current num
	- call calc recursively with the result of each opertaion, decreasing `maxOp` by 1
	- sum the results
```java
public static int calc(int num, int result, int maxOp) {
	// Base cases
	if (maxOp == 0) {
		return (num == result) ? 1 : 0;
	}

	// Recursive cases
	int count = 0;
	count += calc(num + num, result, maxOp-1)
	count += calc(num - num, result, maxOp-1)
	count += calc(num * num, result, maxOp-1)
	if (num != 0) {
		count += calc(num / num, result, maxOp-1
	}
}
```
