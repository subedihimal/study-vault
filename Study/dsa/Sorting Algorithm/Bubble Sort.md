![[30.png]]

In the first pass the largest value will go to the last
**UNLIKE THE FIGURE** IN the second pass the second largest value will go to the **second last**..

**You do it till array length  -1 passes or if u are counting from 0 then (arr.length-2)**

```java
public void bubbleSort() {

	int[] arr = { 7, 4, 8, 5, 3 };
	int end = arr.length - 2;

	while (end > 0) {
		for (int i = 0; i <= end; i++) {
			if (arr[i] > arr[i + 1]) {
				int temp = arr[i];
				arr[i] = arr[i + 1];
				arr[i + 1] = temp;
			}
		}
		--end;
	}
	for (int i : arr) {
		System.out.println(i);
	}
}
```