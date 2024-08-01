# 1	in general
- array is a fixed size, oedered collection of elements of the same data type
- elements are accessed using an index, starting at 0
- arrays provide constant time access to any element given its index
- in Java, arrays are objects, created using 'new'

```java
dataType[] arrayName = new dataType[size];
```

# 2	in memory
- arrays are stored in contiguous memory locations
- each element occupies the same amount of memory (according to the data type)
- the memory adress of any element can be calculated using its index and the size of the data type
- this contiguous storage allows for efficient access but makes resizing difficult

# 3	looping
- arrays are often used with loops for iteration and manipulation

```java
for (int i = 0; i < array.length; i++) {} // iteration through all element
while (i < array.length && array[i] != target) {i++;} // search for an element
for (int i = 0; i < array.length; i++) {array[i] = someValue} // altering data
```

# 4	array of objects
- stores refrences to objects of a specific class or subclass
```java
ClassName[] arrayName = new ClassName[size];
```
- each element is initially null and must be instantiated separately
```java
Person[] people = new Person[5];
people[0] = new Person("Tom")
```

# 5	2D
- arrays where each element is in itself and array. creating a matrix
- visulaised as rows and coloumns
```java
int[][] matrix = new int[rows][columns] // int
matrix[row][column] // access
for (int i = 0; i < matrix.length; i++) {
	for (int j = 0; j < matrix[i].length; j++) {} // nested loops for traversal
}
```

# 6	testwise
- arrays start at 0 and end at length-1
- arrays have a fixed size and to resize, you create a new array with new size and copy the elements
- potential for ArrayIndexOutOfBoundsExecption when accesing elements
- in object arrays, each object needs to be instantiated
- 2d arrays can be traversed row-by-row or column-by-column. points out what you use. 