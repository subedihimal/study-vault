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

Question Solution
![[39.png]]


**Brute Force**
```java
//Find the missed Numbers Kth missing number
public void missing(){
	int[] arr = { 2, 3, 4, 7, 11, 12};
	int k = 3; 
	int searchNumber = 1;
	
	while (k>1){
	   int start = 0, end = arr.length-1;
	   boolean found = false;
		while(start<=end){
			int mid = (start + (end-start)/2);

			if(arr[mid]> searchNumber){
				end = mid-1;
			}else if(arr[mid]<searchNumber){
				start = mid + 1;
			}else{
				found = true;
			  break;
			}
		}
		if(!found){
			--k;
		} 
		++searchNumber;
	}
	System.out.println(searchNumber);
	
}
```

**Actual Solution**

```js
//ACTUAL SOLUTION 
    public void missingAct(){
        //Example
        //             2 3 4 5 11 12
        //Index:       0 1 2 3 4 5
        //Compare with:1 2 3 4 5 6
        //No of missing:1 1 1 1 6 6
        //Here 6<5 so 11 +5 = 10 ; 10 is the 5th missing number
        int[] arr = {2, 3, 4, 7, 11, 12};
        int start = 0, end = arr.length-1;
        int k = 5;

        int ans = -1;
        while(start<=end){
            int mid = start+ (end-start)/2;
            if((arr[mid] - (1 + mid)) < k){
                start = mid+1;
            }else if((arr[mid] - (1 + mid))>k){
                end = mid-1;
                ans = mid;
            }else{
                end = mid-1;
                ans = mid;
            }
        }
        int answer = (arr[ans] - arr[ans-1])+k;
        System.out.println(answer);
        

    }
```

**More Optimized**

```js
public void missingg(){
       int[] arr = {2, 3, 4, 7, 11, 12};
        int start = 0, end = arr.length-1;
        int k = 5;

        int ans = -1;
        while(start<=end){
            int mid = start+ (end-start)/2;
            if((arr[mid] - (1 + mid))>=k){
                end = mid-1;
                ans = mid;
            }else{
                start = mid+1;
            }
        }
        int answer = ans+k;
        System.out.println(answer); 
    }
```