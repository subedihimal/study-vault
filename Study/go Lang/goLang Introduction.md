---
tags:
  - study
---

**Example Go Code**

```go
package main
import "fmt"
func main() {
    fmt.Println("Hello")
}
```

**Compile and Run**

- Run: `go run filename.go`
- Compile only: `go build filename.go`

**Variables and Constants**

Declare variables with `var` or shorthand `:=` Declare constants with `const`

```go
const name = "test"
var age int = 22
rollNo := 18  // Same as var rollNo int = 18
```

**Range**

Similar to for loop but with extra features

```go
for i := range 3 {
    fmt.Println("loop iteration", i)  // Output: 0, 1, 2
}

for i := range "Himal" {
    fmt.Println(i)  // Output: 0, 1, 2, 3, 4
}

for i, char := range "Sanket" {
    fmt.Println(i, char)  // Output: 0 83, 1 97, 2 110, 3 107, 4 101, 5 116
}
```

**While Loop**

Go doesn't have `while` keyword, use `for` instead

```go
j := 10
for j > 0 {
    fmt.Println("Running while loop")
    j--
}
```

**Arrays**

Fixed length arrays

```go
var arr [5]int
arr[0] = 1  // Adding value to array

var arr2 = [5]int{1, 2, 3, 4, 5}

arr3 := [5]int{1, 2, 3, 4, 5}
```

**Slices**

Arrays with no fixed length

```go
var arr1 []int  // Declared empty slice

// Adding elements to slice
arr1 = append(arr1, 1, 2, 3, 4, 5)  // Only works with slices

arr2 := []int{1, 2, 3}  // Slice with initial values
```

Maps
like Hashmap in  java or object in javascript
```go
var test map[string]int{ // OR test := map[string]int { VALUES }
	"iphone 15": 10000,
	"iphone 11": 5000
}
for key, value := range emptyMap{
	fmt.Println("Key:", key, "Value:" , value)
}
```

**Pointer**
Stores the address of a varaible
```go
i := 20,
var address *int = &i //Stores the adress of i
//OR SHORT FORM

add2 := &i

fmt.Println("address:", add2, "value in address:", *add2)
//
```

---
### Go Module
To have a multi file setup you need to create go module
Sytax:
`go mod init <moduleName>`
now you can easily import other files by

`import test <modulename>/<appname>`

**Important for cross package**
The function name has to have capital starting letter to make it public and be able to  be accessed throughout the module

**if multiple file in the main module you will need to run**
**`go run *.go`
or else it wont compile all the files and you will get error while running

You can use build system like  bazzle to avoid this 

