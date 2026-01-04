Finds the element by checking each item one by one form the start until the target is found or the list ends.

Time Complexity: O(n)

![[linearsearch.png]]

Code example of linear search 
```java
int search = 3;
int[] arr = {1,2,3,4,5};

for(int i=0; i<arr.length; i++){
	if(arr[i] == search){
		System.out.println("Found at index :" + i );
		break;	
	}
}
```