An array in Java is a data structure that stores multiple values of the same data type in a single variable. Arrays have a fixed size, and elements are stored in contiguous memory locations.  
Each element is accessed using an index, starting from `0`.

**Taking Input in Java**
Scanner scanner= new Scanner(System.in);
System.out.println("Enter a Number:");
int a = scanner.nextInt();
scanner.close();

**Declaring Array in java**

With value initialized:
int[] arr = {1, 2, 3, 4, 5};

Without value initialized:
int[] arr = new int[5];

**Printing all the elements in an array**
for (int n : arr) { System.out.println(n); }


