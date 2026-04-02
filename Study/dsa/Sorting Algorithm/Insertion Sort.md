![[32.jpeg]]

```java
public void InsertionSort(){
	int[] arr = {7, 4, 2, 3, 5};
	int index = 1;
	
	while(index <= arr.length-1){
		for(int i = index; i>0; i--){
			if(arr[i]<arr[i-1]){
				int temp = arr[i];
				arr[i] = arr[i-1];
				arr[i-1] = temp;
			}else{
				break;
			}
		}
		++index;
	}
}
```