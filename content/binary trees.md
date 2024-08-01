# 1	definition
- hierarchical data structure where each node has at most two children
- children are typically "left child" and "right child"
# 2	implementation
```java
public class Node {
	private int _number;
	private Node _leftSon, _rightSon;
	public Node(int number) {
		_number = number;
		_leftSon = null;
		_rightSon = null;
	}
}
```
# 3	operations
- insertion
- deletion
- traversal
- search
## 3.1	traversal methods (DFS)
![[Pasted image 20240712142919.png|Binary Tree Traversal]]
- in-order: left, root, right
- pre-order: root, left, right
- post-order: left, right, root
### 3.1.1	inorder
![[Pasted image 20240712143134.png|Inorder 4→2→5→1→3→6]]
- left → root → right
```java
public void inorderTraversal(TreeNode root) {
	if (root == null) return;
	
	inorderTraversal(root.left);
	System.out.print(root.val); // the action is IN recursion
	inorderTraversal(root.right);
}
```
### 3.1.2	preorder
![[Pasted image 20240712143307.png|Preorder 1→2→4→5→3→6]]
- root → left → right
```java
public void preorderTraversal(TreeNode root) {
if (root == null) return;

System.out.print(root.val); // action is PRE the recursion
preorderTraversal(root.left);
preorderTraversal(root.right);
}
```
### 3.1.3	postorder
![[Pasted image 20240712143703.png|Postorder 4→5→2→6→3→1]]
- left → right → root
```java
public void postorderTraversal(TreeNode root) {
	if (root == null) return;

	postorderTraversal(root.left);
	postorderTraversal(root.right);
	System.out.print(root.val); // actions is POST recursion
}
```
## 3.2	peoperties
- height: longest path from root to leaf
- deapth: length of path from root to specific node
- balanced vs unbalanced
# 4	recusion
- most binary trees opertaions are recursive
```java
public int someOperation(Node too) {
	if (root == null) {
		return someValue;
	}
	int leftResult = someOperation(root.getLeftSon())
	int rightResult = someOperation(root.getRightSon())
	return combineResults(leftResult, RightResult, root.getNumber)
}
```

# 5	binary search tree
- each node has at most two children, left and right. 
- all values in the right subtree are greater than the node's value
## 5.1	operations
- search: starting at the root, compare value of current node to the target, continue left if value is greater and right if value is lesser.
- insertion: traverse the tree to find the correct spot to insert while staying BST
- deletion: requires rearranging the tree

# 6	testwise
## 6.1	common questions
- implement travesal
- find height
- check balance
- count nodes with specific properties
## 6.2	what method (exam 3)
- minimum height of a tree
```java
public static int what(Node t) {
	if (t == null)
		return -1;
	if ((t.getLeftSon() == null) && (t.getRightSon() == null))
		return 0;
	int n1 = what(t.getLeftSon());
	int n2 = what(t.getRightSon());
	if (n1 == n2)
		return n1 + 1;
	if (n1 > n2)
		return n2 + 1;
	else
		return n1 + 1
}
```
## 6.3	tips
- consider best cases
- how to combine results
- think of special cases like skew or perfect
- understand traversal