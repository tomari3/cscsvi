# 1	structure
- composed of nodes
- each node has 
	- Data (value)
	- reference (link) to next node
# 2	types
1. singly linked list: each node points to the next
2. doubly linked list: each node points to the next and previous
3. circular linked list: last node points to the first
# 3	operations
- insertion: O(1) at start, O(n) elsewhere
- deletion: O(1) at start, O(n) elsewhere
- traversal: O(n)
- search: O(n)
# 4	implementation
```java
public class Node {
	private int data;
	private Node next;

	public Node(int data) {
		this.data = data;
		this.next = null;
	}
}
```
# 5	testwise
- operations in tests: traverse, insert/delete, reverse, find middle, detect cycle. marge two sorted lists

## 5.1	remove duplicates

```public void removeDuplicates() {
	if (head == null || head.next == null) return;
	Node current = head;
	while (current != null && current.next != null) {
		if (current.data == current.next.data) {
			current.next = current.next.next;
		} else {
			current = current.next;
		}
	}
}
```

## 5.2	tips 
- draw linked list for visualization
- consider edge cases: empty, single. all dups
- careful with null pointer exceptions
- consider multiple pointers if needed (fast & slow)