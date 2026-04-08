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
concat, slice, flat, flatmap, reduce

**For Searching**
indexOf, includes, find, findIndex

```js
//To copy array
const trainCopy = wholeTrain.slice();

const notFlat = [1, 2, 3, [5, 6]];  
const flat = notFlat.flat();   //flat = [1,2,3,5,6]
```


---
Explore .filter

```js
const spiceyOrders = [
    {dish: "Inferno Wings", price: 11, spicey: true},
    {dish: "Momo", price: 33, spicey:false},
    {dish:"Chowmin", price:22, spicey: true}
]

const output = spiceyOrders.filter((o)=> o.spicey);
console.log(output)

/**Output: [
  { dish: 'Inferno Wings', price: 11, spicey: true },
  { dish: 'Chowmin', price: 22, spicey: true }
]**/

```

**With Filter we always try to get Negative Condition **

```js
const kitchenOrders = [
    { dish: "Inferno Wings", price: 11, spicey: true, quantity: 1 },
    { dish: "Momo", price: 33, spicey: false, quantity: 2 },
    { dish: "Chowmin", price: 22, spicey: true, quantity: 1 },
    {dish : "thakali", price: 300, spicey: false, quantity: 1}
];

const mildReport = kitchenOrders
    .filter(order => !order.spicey)
    .map(order => ({
        dish: order.dish,
        total: order.price * order.quantity
    }))
    .sort((a, b) => a.total - b.total);

console.log(mildReport); // Output:[ { dish: 'Momo', total: 66 }, { dish: 'thakali', total: 300 } ]

```



---

Implementing .reduce
```js
const spiceyOrders = [
    {dish: "Inferno Wings", price: 11, spicey: true, quantity: 1},
    {dish: "Momo", price: 33, spicey:false, quantity: 2},
    {dish:"Chowmin", price:22, spicey: true, quantity: 1}
]

const totalRevinue = spiceyOrders.reduce((sum , order)=> {            //Here sum = 20 as at last callback is 20 so it will do 20+11+33+22 
    return sum +(order.price * order.quantity);
},20)

console.log(totalRevinue)

//Output: 119
```


```js
/** const grouped = orders.reduce((acc, order)=>{
	//logice
}, acc) **/

const orders = [
    {dish: "Inferno Wings", price: 11, spicey: true, quantity: 1},
    {dish: "Momo", price: 33, spicey:false, quantity: 2},
    {dish:"Chowmin", price:22, spicey: true, quantity: 1}
]

const grouped = orders.reduce((acc, order)=>{
	const category = order.spicey ? "spicey": "mild";
	acc[category].push(order.dish);
	return acc;
	
}, {spicey:[], mild: []})

console.log(grouped)


// Output: { spicey: [ 'Inferno Wings', 'Chowmin' ], mild: [ 'Momo' ] }
```

**You can use reduceRight to access in decending order**

---
**.sort**
**Works out of the box with strings but if we need to sort numbers we pass parameters**
```js
const arr = [100, 25, 3, 42, 8, 90];

const asc = [...arr].sort((a, b)=> a-b ); // [3, 8, 25, 42, 90, 100]
const dsc = [...arr].sort((a,b)=> b-a);// [100, 90, 42, 25, 8, 3]

console.log(arr); // [100, 25, 3, 42, 8, 90] Not effected as spread operator is                        used
```

---
### Converting Anything to array we use form

```js
const convertedArray = Array.from(test);
```