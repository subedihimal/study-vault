A **Promise** is an object that represents the **future result of an asynchronous operation**
Promises has 3 stages
- Pending
- Fulfilled
- Rejected
---

## Simple Promise Examples

```js
const promise = new Promise((res, rej) => {
   setTimeout(()=>{
      res("ChaiCode");
   }, 2000);
});

setTimeout(()=>{
   console.log(promise)       //Output: ChaiCode
}, 3000)
```


**Another Little  Complex Example**

```js
const promise = new Promise((res, rej) => {
   setTimeout(()=>{
      res("ChaiCode");
   }, 2000);
});

promise.then((value)=>{
   console.log(value);                //Output: ChaiCode
});


//promise.then(console.log)        //This also works Output = ChaiCode
```


**Here `.then` is responsible of passing value into given function so this also works **

```js
const promise = new Promise((res, rej) => {
   setTimeout(()=>{
      res("ChaiCode");
   }, 2000);
});

promise.then((value)=>{
   console.log(value);                //Output: ChaiCode
});
```

---
### Reject (Used to throw an error)
```js
const promise = new Promise((res, rej) => {
   setTimeout(()=>{
      rej(new Error("ChaiCode"));
   }, 1000);
});



promise.then((data)=>{
  console.log(data);  
},(error)=>{
   console.log(error);
});


//More SugarCoated Syntax

promise
.then((data)=>console.log(data))
.catch((error)=>console.log(error));


//Output
/*
Error: ChaiCode
    at Timeout._onTimeout (/Users/himal/Projects/practice/test.js:3:11)
    at listOnTimeout (node:internal/timers:605:17)
    at process.processTimers (node:internal/timers:541:7)
*/
```


**Manipulating the output from promise**

```js
const promise = new Promise((res, rej) => {
   setTimeout(()=>{
      res("chaicode")
   }, 1000);
});

promise
   .then(data => data.toUpperCase())
   .then(data => data + ".com")
   .then(console.log);

//Output : CHAICODE.com
```

---

## Theory Of Fetch (Promise)
![[Pasted image 20260701102807.png]]


### Fetch

Fetch is not inside JS it is an outside tool like timers, console or DOM that you can utilize to do various task.
Promise is most commonly used with `fetch` keyword which returns a promise.
Fetch basically gets a data if it finds it it will give resolved if not found it gives out error.
Syntax: 
`const data = fetch()`

Tasks of fetch
- Returns a reference (which is promise in the case of fetch)
- Fetch creates object that has (state = {pending, res, rej}, thenArray(fn, fn, fn ...) and catchArray(fn,fn,fn...))
- Talks with OS for network call
---
##  Some More Promise Example

**If you want immediately resolving promise**
```js
const turant = Promise.resolve("Turant Resolved");

console.log(turant); //Output: Promise { 'Turant Resolved' }
```
## Methods of Promises

1. **.all**
`.all` requires no error and all promise to be resolved
```js
const testPromise = Promise.all([
   Promise.resolve("Chai"),
   Promise.resolve("Code"),
   Promise.reject("Error"),
]);

testPromise.then(console.log); //Gives Error
```
2. **.allSettled**
`.allSettled` gives status of all promises

```js
const testPromise = Promise.any([
   Promise.resolve("Chai"),
   Promise.resolve("Code"),
   Promise.reject("Error"),
]);

testPromise.then(console.log); 

/*
[
  { status: 'fulfilled', value: 'Chai' },
  { status: 'fulfilled', value: 'Code' },
  { status: 'rejected', reason: 'Error' }
]
 */
```

3. **.any**
`.any` even if only one promise resolved it returns and finishes
```js
const testPromise = Promise.any([
   Promise.resolve("Chai"),
   Promise.resolve("Code"),
   Promise.reject("Error"),
]);

testPromise.then(console.log);

//output: Chai
```



---
### Very Complex Example of Promise

```js
function prepareOrder(dish) {
    return new Promise((resolve, reject) => {
        setTimeout(() => {
            if (!dish) {
                reject(new Error("No Dish is there"));
                return;
            }
            console.log(`${dish} is ready`);

            resolve({ dish, status: "prepared" });
        }, 100);
    });
}

function pickupOrder(order) {
    return new Promise((resolve) => {
        setTimeout(() => {
            console.log(`${order.dish} is picked up`);

            resolve({ ...order, status: "ready" });
        }, 100);
    });
}

function deliverOrder(order) {
    return new Promise((resolve) => {
        setTimeout(() => {
            console.log(`${order.dish} is delivered`);

            resolve({ ...order, status: "delivered" });
        }, 100);
    });
}

prepareOrder("Chai")
    .then(order => pickupOrder(order))
    .then(order => deliverOrder(order))
    .catch(err => console.error(err.message));

```


---


**Before Promises  - > (CalBack Hell)❌**
```js
function prepareOrderCB(dish, cb){
    setTimeout(() => cb(null, { dish, status: "prepared" }), 100);
}

function pickupOrderCB(order, cb){
    setTimeout(() => cb(null, { ...order, status: "picked-up" }), 100);
}

function deliverOrderCB(order, cb){
    setTimeout(() => cb(null, { ...order, status: "delivered" }), 100);
}

prepareOrderCB("Biryani", (err, order) => {
    if (err) return console.log(err);

    pickupOrderCB(order, (err, order) => {
        if (err) return console.log(err);

        deliverOrderCB(order, (err, order) => {
            if (err) return console.log(err);

            console.log(`${order.dish}: ${order.status}`);
        });
    });
});

//Output: Biryani: delivered

```
