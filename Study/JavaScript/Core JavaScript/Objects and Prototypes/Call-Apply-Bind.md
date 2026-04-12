
## Call and Apply
Call and apply allows you to manually set the value of `this` in a function and also run it immediately like a normal function call.

### Call (Can Pass datatype after modifying `this`)

- Calls the function **immediately**
- Sets `this` to the object you pass
- Then you can pass normal Arguments after it
Syntax
`fn.call(thisArgument, arg1, arg2, arg3, ...)`

```js
function greet() {  
  console.log(this.name);  
}  
  
const user = { name: "Himal" };  
  
greet.call(user); // Himal
```

If you want to pass other normal parameters into the function you can also do so after **comma**.
```js
function greet(age){
	console.log(this,name, age);
}
const user = {name: "Himal"};

greet.call(user, 32)
```

---

### **Apply** (Can Pass Array after modifying `this`)

- Calls the function **immediately**
- Sets `this` to the object you pass
- Then you can pass array Arguments after it

Same as call but to pass an array.
Syntax
`functionName.apply(thisArgument, [arg1, arg2, arg3]);`

```js
function greet(age, city) {  
console.log(this.name, age, city);  
}  
  
const user = { name: "Himal" };  
  
greet.apply(user, [21, "Kathmandu"]);
```

---

*Apply can Also Can be used with Math.max()*
```js
let a =[1,2,3,4];
let b = Math.max(...a);               //Same 
let c = Math.max.apply(null, a);       // Same

console.log(b) //Output: 4
console.log(c) //Output: 4
```

---
### Bind
**Major Difference is It returns a new function**
```js
function reportDelivery(location, status){
    return `${this.name} at ${location}: ${status}`
}
const deliveryBoy = {name: "Ranveer"};


const returnedFunction = reportDelivery.bind(deliveryBoy, "Nepal", "Delivered")

console.log(returnedFunction());


```
---

Implementing Call - Apply and Bind All - Together
```js
function reportDelivery(location, status){
    return `${this.name} at ${location}: ${status}`
}
const deliveryBoy = {name: "Ranveer"};

console.log(reportDelivery.call(deliveryBoy, "Nepal", "Delivered")); 
//Ranveer at Nepal: Delivered
console.log(reportDelivery.apply(deliveryBoy, ["Nepal", "Delivered"])); //Ranveer at Nepal: Delivered
console.log(reportDelivery.bind(deliveryBoy, "Nepal", "Delivered")) 
//❌ Function: bound reportDelivery


//Actual way to do it with bind
const returnedFunction = reportDelivery.bind(deliveryBoy, "Nepal", "Delivered") // Ranveer at Nepal: Delivered

console.log(returnedFunction());
```

---