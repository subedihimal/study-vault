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
It is not dependent on the input so O(1)

3.
```java
for(int i=1; i<n; i++){
	for(int j=1; j<n: j++){
		System.out.println("Hello");
	}
}
```

![[img1.jpeg]]

Answer: O(n^2)
If two loop and inside loop doesn't depend on outer loop then shortcut the answer is O(n^2)

3.
```java
for(int i=1;i<n; i++){
	for(j=1;j<i^2; j++){
		System.out.println("Hello");
	}
}
```

![[img2.jpeg]]

Answer: O(n^2)
4.
```java
for(int i=1; i<n; i++){
	for(j=1; j<i^2; j++){
		System.out.println("Hello");s
	}
}
```
![[img3.jpeg]]
Answer: O(n^3)

5.
```java
for(int i=1; i<n; i++){
	for(int j =1; j<m; j++){
		System.out.println("Hello");
	}
}
```
Answer: O(nm)


6.
```java
for(int i =1; i<=n; i*2){
	System.out.println("Hello");
}
```

Answer: O(log2n)

7.
```java
for(int i=n/2; i<=n; i++){
	for(j=1;j<=n/2; j++){
		for(k=1;k<=n; k++){
			System.out.println("Hello");
		}
	}
}
```
Answer O(n^3)