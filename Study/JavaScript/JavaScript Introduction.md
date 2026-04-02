
Working Architecture of JavaScript Compared to a Wood Factory
![[34.png]]
![[33.png|697]]

**NodeJS is just a runtime environment. Not a framework or library, the actual translation is handled by V8 engine not Node.**


*Memory and Execution phase in js*

![[35.png]]

1. Memory phase runs and loads the variable age as assigns undefined *(Incase of Let/Const - `age` is created BUT NOT initialized )*
2. In the Code phase (Execution Phase) the code runs and  when it reaches the **var age** line assigns 32 as the value of age and when it reaches the console.log line it looks up value of age and prints out 32
```js
console.log(age); // ❌ ReferenceError  
let age = 32;

console.log(age); // ✅ undefined  
var age = 32;
```

---
### Hoisting
Hosting is a mechanism in JavaScript where function, class and variable declearation are moved to the top of their respective scope during memory creation phase.

**Declarations are hoisted initialization aren't hoisted**

```js
sayHi(); // Works  
function sayHi() {  
  console.log("Hi");  
}  
```
*Here unlike a variable which assigns the value to the variable when the execution reaches that line in the execution phase. **Body of functions are assigned to the function name in the memory phase only***

