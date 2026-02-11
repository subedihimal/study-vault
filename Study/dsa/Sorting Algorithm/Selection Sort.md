![[29.png]]

Find the smallest Number (index 0 - 5) swap it with the index 0
Find the smallest Number (index 1 - 5) swap with index 1 
Find the smallest Number (index 2 - 5) swap with index 2
Find the smallest Number (index 3 - 5) swap with index 3 
and so on...


```java
public static void main(String[] args) {
        int[] arr = { 10, 8, 2, 3, 1, 4 };
        int smallest = 0;

        // Finding Smallest
        for (int i = 0; i <= arr.length - 2; i++) {
            smallest = i;
            for (int j = i+1; j <= arr.length - 1; j++) {
                if (arr[smallest] > arr[j]) {
                    smallest = j;
                }
            }
            // Swapping
            int temp = arr[i];
            arr[i] = arr[smallest];
            arr[smallest] = temp;

        }
        System.out.println("swapping end");

        for (int n : arr) {
            System.out.println(n);

        }

 }
```