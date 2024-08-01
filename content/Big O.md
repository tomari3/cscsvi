# 1	what is it
- notation for decribing the upper bound of an algorithm's time or space
- grows in relation to input size
- helps compate efficiency
# 2	types
- from best to last

| #   | Big O      | in words          |
| --- | ---------- | ----------------- |
| 1   | O(1)       | Constant time     |
| 2   | O(log n)   | Logarithemic time |
| 3   | O(n)       | Linear time       |
| 4   | O(n log n) | Linearithmic time |
| 5   | O($n^2$)   | Quadratic time    |
| 6   | O($2^n$)   | Exponential time                  |

# 3	testwise

## 3.1	time complexity
- count the number of operations in relation to input size
- look for nested loop (usually quadratic time)
- look for divide and conquer (usually logarithmic time)

## 3.2	space complexity
- look for creation of new data structures
- consider extra space used by algorithm

## 3.3	improve efficiency
- look for redundancy of calculations or loops
- consider efficiency of data structures (eg. HashSet for O(1))

# 4	example

```java
public static boolean what (int[]a, int num) {
	for (int i = 0; i < a.length; i++) {
		for (int j = i; j < a.length; j++) {
			if (f(a, i, j) == num)
				return true;
		}
	}
	return true;
}
```

## 4.1	time comlexity analysis

- there are two loops
- outer loop runs n times → O(n)
- inner loops runs from u to n → O(n)
- f is just a sum function from i to j → O(n)
- comlexity → O($n^3$)

## 4.2	improvements
- sliding window
- cumulative sum approach

## 4.3	fomart answer
1. state original time and space complexity
2. explain reasoning
3. propose improvement
4. analyse improvement
5. explain improvement