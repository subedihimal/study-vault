
**Arrow Functions have no own `this` and no `argument` objects** Example:

```js
//Normal Function have arguments

testFunc("Ram", 3);
function testFunc(){
	console.log("Type: ", typeof arguments); // Type: object
    console.log(Array.isArray(arguments)) // false
    console.log(arguments) // [Arguments] { '0': 'Ram', '1': 3 }
    
    
    //If you want to convert arguments to array we can
    const argsArray = Array.from(arguments);
    console.log(argsArray); // ["Ram", 3]
}
```

**Arrow function doesn't have arguments**

```js
const arrowBrew = () => {
	console.log(arguments);   // Gives out error and crashes code
}
arrowBrew();
```


---
**Impure and Pure Function**
Impure function changes variable outside it scope. Pure function doesn't change anything outside its scope.

`HERE FUNCTION IS IMPURE AND IT HAS A  SIDEEFFECT THAT IS globalCount (The function has a side Effect) `
```js
//Impure Function

let globalCount = 0;
function add(a, b){
	globalCount++;
	return a+b;
}
add(1,2);


```
---
## IIFE

syntax `()()`
```js
const example = (function(){
});

(function () {})()
```


----

**Here test is storing function definition**
```js
const test = (()=>{
    let inventory = 0;

    return { 
        func1(){
            return ++inventory;
        }, func2(){
            return inventory
        }
    }
})()
console.log(test)

//Output: { func1: [Function: func1], func2: [Function: func2] }

console.log(test.func1()); // 1 ✅ access via closure  
console.log(test.func2()); // 1 ✅ still remembers value  
  
console.log(test.inventory); // undefined ❌ not accessible
```

### Here in this case
Even though `makeFunc()` has finished executing,  
the inner function `displayName` **still has access to `name`**.

This happens because of a **closure**.
A **closure** is a function that **remembers and can access variables from its outer (lexical) scope even after that outer function has finished execution**.

```js
function makeFunc(){
    const name = "Mozilla";

    function displayName(){
        console.log(name);
    }
    return displayName;
}

const myFunc = makeFunc(); //Outpput : Mozilla
myFunc();
```