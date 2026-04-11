**Fun Fact: Spread Operator is Also used to shallow copy.**
View This notes for more context [[Parameters Passing - (Value vs Reference)]]

---
Spread operator is used to *expand* / *unpack* values. It works on:
Interaction with various data types
- Arrays ✔️ (iterable)
- Strings ✔️ (iterable)
- Objects can only be spread inside object literals `{}`
- Other iterables ✔️ (like Map, Set)

Also to *Shallow Copy* both Object or Array.
*Example OF unpack/ expand:*
```js
let a = [1 , 2, 3]; // Array
let b = {name: "Himal", age: 13, class: 11}; //Object

console.log(...a); //Output: 1 2 3

console.log(...b); //❌ Because Object is not iterable outside {}
```

---
As spread Operator can expand an array  you can decide what to do with the expanded value If you put wrap inside `[]` it becomes array if you wrap inside `{}` it becomes object

```js
let test = [1, 2, 3, 4]; // Array
let test2 = {name:"Himal", age: 32}//object

// Spreading array into object (indexes become keys)
let objTest = {...test}
console.log(objTest);   //Output: { '0': 1, '1': 2, '2': 3, '3': 4 }
 
//Converting Obj into arr
let arrayTest2 = [...test2]
console.log(arrayTest2);  //❌ Because Object is not Iterable outside {} (cannot                              be spread into arrays)

```

---

Interaction with Other Methods

Spread Operator can be used to implement other methods like
`Math.max`
```js
const bills = [100, 30, 25, 50];
let value = Math.max(...bills);

console.log(value); //Output: 100;
```

---
