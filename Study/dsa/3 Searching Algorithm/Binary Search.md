![[38.png]]

```java
public void BinarySearch(){
	int[] arr = {2, 3, 6, 10, 11, 13};
	int key = 6, start = 0, end = arr.length-1;

	while(start<=end){
		int mid = (start+end)/2;
		if(arr[mid]<key){
			start = mid+1;
		}else if(arr[mid]>key){
			end = mid-1;
		}else{
			System.out.println("Key found at index = " + mid + " -----> " 
			+ key + " = " + arr[mid] );
			break;
		}
	}
		
}
```