
## Higher Order Function

A function that takes another function as a parameter. OR return them as result

```js
function test(AnyOtherFunction){
	return AnyOtherFunction() + 5;
}

function test1(){
	return 10;
}

var result = test(test1); // Output is 15
```


```js
function test(){
	return function ram(){
		return 33;
	}
}
```
---
## ForEach Function (Same as map but changes the same array and no return )

**Foreach expects a synchronous function - It doesn't wait for promises**  *No way to Break or Stop a ForEach loop other then throwing exception*


```js
let fruits = [ "apple", "mango", 32, true ];

function printKardo(element){
	console.log(element);
}

	fruits.forEach(printKardo); // This calls printKardo for each an every elements                                 of the array fruits
```

```js
//same Example with arrow function

let fruits = ["apple", "mango", 32, true];

fruits.forEach(anyInput => console.log(anyInput));
```

### Custom ForEach Implementation

```js
var fruits = ["apple", "mango"];

function customForEach (element, functionName){
    for (let i=0; i<element.length; i++){
        functionName(element[i]);
    }
}

function printer (elem){
    console.log(elem);
}
customForEach(fruits, printer)

```

**Same implementation but with Arrow Function**
```js
var fruits = ["apple", "mango"];

function customForEach (element, functionName){
    for (let i=0; i<element.length; i++){
        functionName(element[i]);
    }
}
var printer = element => console.log(element);

customForEach(fruits, printer)

```

---
### Map (Same as foreach but returns new array with modification)

Initializes new array and


```js
var nums = [1, 2, 3, 4, 5];

nums.map(3 => e*2) // Outpur : [1, 4, 6, 8, 10]
```

![[37.png]]

**Custom Map Implementation**
```js
let fruits = [ 1,2,3,4,5,6 ]

function map (element, func){
    let arr = [];

    for(let i =0; i<element.length; i++){
        arr[i] = func(element[i]);
    }
    return arr;
}

var result = map(fruits, elem => elem*2 );
console.log (result);
```