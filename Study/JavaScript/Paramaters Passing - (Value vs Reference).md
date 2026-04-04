
JS uses **PassByValue** for **Primitive-DataType** but uses **PassByReference** for **Non-Primitive DataTypes**

```js
//Primitive DataType
let a = 5;  
let b = a; // copy  
b = 10;  
console.log(a); // 5 (original unchanged)


//Non-Primitive DataType
let arr = [1,2,3];  
let b = arr; // reference  
b.push(4);  
console.log(arr); // [1,2,3,4] (original changed)

```

---
## How to Pass-By-Value in Objects then ?? (SHALLOW CLONE)

**Use "..."  (Spread Operator)**
```js
const original = { name: "Himal", age: 25 };  
  
// Copy only the value - PassByValue  
const copy = { ...original };
```
---
## **Still an issue** (DEEP CLONE)

**OBJECT inside an Object is still passed by reference** 

**structuredClone(ObjectName) : So even nested Object are passed by value**
```js
const test{
	"user": "normal",
	"name":{
		"first": "Himal",
		"second": "Subedi"
	},
	"age": 13
}

const testCopy = ...test;
testCopy.name.first = "Ram";   // WILL STILL CHANGE THE ORGINAL TEST OBJECT AS                                    YOU CHANGED AN OBJECT INSIDE AN OBJECT

testCopy = structuredClone(test); // Now even nested object are passedbyvalue

```