# 1	definition
- dynamic data structures that can grow or shrink in size
- part of the Java Collections Framwork
# 2	main interfaces
- list
- ArrayList, LinkedList
# 3	ArrayList
- backed by and array that grows dynamically
- fast random access O(1)
- slower insertion/deletions O(n) (worst case)
- good for frequent access and infrequent mods
# 4	LinkedList
- doubly-linked list
- fast intersion and deletion O(1)
- slower random access O(n)
- good for frequent mods
# 5	operations
```java
add(E element) // appends element to end
add(int index, E element) // inserts element a to specific index
get(int index) // retrives element at index
remove(int index) // remove element at index
size() // return number of elements
isEmpty() // checks if list is empty
```
# 6	iteration
## 6.1	for each
```java
for (ElementType element : list) {
	//
}
```
## 6.2	iterator
```java
Iterator<ElementType> it = list.iterator();
while (it.hasNext()) {
	ElementType element = it.next()
}
```
# 7	list vs array

|                  | lists   | array      |
| ---------------- | ------- | ---------- |
| size             | dynamic | fixed      |
| stores           | objects | primitives |
| built in methods | V       | X           |

# 8	testwise
```java
public static List<int[]> findPairs(List<Integer> numbers, int target) {
List<int[]> result = new ArrayList<>();
Set<Integer> seen = new HashSet<>();

	for (int num : numbers) {
		int complement = target - num;
		if (seen.contains(complement)) {
			result.add(new int[]{num, complement})
		}
		seen.add(num)
	}
	return result;
}
```
1. ArrayLists store result pairs
2. iteration through input once
3. HashSet for efficient lookup of complements
4. lists used with other data structures
- choose appropriate list implementation based on use case (access vs mods)
- notice complexity of opertaions
