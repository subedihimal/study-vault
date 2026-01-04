---
tags:
  - DSA
---

### Time Complexity
Time complexity refers to how the runtime of an algorithm changes **(number of operation)** as the input size changes.

Time Complexity **!=**  time taken for execution

**Big(O): O(n) = Worst Time Complexity (Big 0)**     ---> MOST IMPORTANT
θ     : θ(n)   = Average Case (theta)
Ω : Ω(n) = Best Case (Omega)

Whats the Time complexity of this?
1.
 ```java
 
 for(int i=1; 1<=n; i++){
	System.out.println("hello");
 }
 ```
Answer: (n)

2.
```java
for(int i =1; i<10; i++){
	System.out.println("hello");
}
```
Answer: O(10) witch is ultimately ---> O(1)
It is not dependent on the input