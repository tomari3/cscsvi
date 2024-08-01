![undefined](https://upload.wikimedia.org/wikipedia/commons/c/c1/Binary-search-work.gif)
```java
public static int binarySearch(int [] arr, int target) {
	int l = 0;
	int r = arr.length-1;
	int m;
	while (l<=r) {
		m = (l+r)/2;
		if (arr[m]<target) l = m+1;
		else if (arr[m]<target) r = m-1;
		else return m;
	}
	return -1;
}
```

# 1	Problems!
## 1.1	almost sorted ascending array
```java
public static int findAlmostSorted(int [] arr, int target) {
	int l=0;
	int r=arr.length-1;
	while (l<=r) {
		int m = l + (r-l) / 2; // overflow prevention
		if (arr[m]==target) return m; // found target

		// prevent 
		if (m>0 && arr[m-1]==target) return m-1; 
		if (m<arr.length-1&&arr[m+1]==target) return m+1;
		
		if (target<arr[m]) {
			r = m - 2;
		} else {
			l = m + 2;
		}
	}
	return -1;
}
```