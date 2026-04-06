```js
//find if an array is array
const arr = [1,2];
console.log(Array.isArray(arr));  // true



const emptyarr = [];
console.log(emptyarr); //Output: []

let arr = Array(3);
console.log(arr);                 // [ <3 empty items> ]
console.log(arr.length);          // 3

arr[0] = 1;
// arr[1]=4;                      //Didnt input arr[1]
arr[2]=5
arr[3]=4
console.log(arr)                //Output: [ 1, <1 empty item>, 5, 4 ]


//Array.of method

let arrNew = Array.of(3);    //Same as arrNew = [3]


//Array from method
let arr = Array.from("DUST");   // arr = [ 'D', 'U', 'S', 'T' ]


//Truncet Array
let arr = [a,b,c,d,e];
arr.length = 3;             // arr = [a,b,c]
arr.length = 5;              // arr = [a,b,c, <2 empty items>]
```

---
### Methods that mutate and don't mutate an array

**Mutate**
push, pop, shift, unshift, splice

**Doesn't mutate** (We Prefer This in React and redux)
concat, slice, flat, flatmap

**For Searching**
indexOf, includes, find, findIndex

```js
//To copy array
const trainCopy = wholeTrain.slice();

const notFlat = [1, 2, 3, [5, 6]];  
const flat = notFlat.flat();   //flat = [1,2,3,5,6]
```
