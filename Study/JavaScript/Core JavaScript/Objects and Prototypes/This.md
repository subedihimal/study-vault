This represents the current Execution Context. 

### In Node JS when not using Strict Mode
![[41.png|697]]


---
### In Strict Mode
`this` Doesn't give access to the global object so this inside a `function` gives **undefined**.


---
### In Browser

![[Images/40.png]]

---

### Arrow Function and `this`

Arrow function doesn't have definition of `this` so it inherits whatever definition the parent has.
```js
let test = {
    car: "tata",
    speed: function(){
        nested = ()=>{
            console.log(this.car);   //Output is tata
        }
        nested();
    }   
}
test.speed();
```

**WhereAs if use normal function**
**Here `this` of the nested function represents the global execution context**
```js
let test = {
    car: "tata",
    speed: function(){
        function nested(){
            console.log(this.car);  //Output: undefined
        }
        nested();
    }   
}
test.speed();
```

---
### Using this inside a Object  method

If this is used inside a method which is inside an object. It refers to the object.
Example
```js
let test = {
    car: "tata",
    speed: function(){
        console.log(this)
    }   
}
test.speed(); { car: 'tata', speed: [Function: speed] }
```

****

Complex 
```js
let test = {
    car: "tata",
    speed: function(){
        let ram = {
            name : "Himal",
            nest: ()=>{
                console.log(this);  //Output: { car: 'tata', speed: [Function:                                                   **speed**] }
            }
        }
        ram.nest();
    }   
}
test.speed();

```


---
**Interaction with ForEach**
```js
const obj = {
  name: "Tesla",
  cars: ["Model S", "Model 3"],
  showCars: function() {
    this.cars.forEach(function car() {
      console.log(this.name + ": " + car);
    });
  }
};

obj.showCars();

/* Output
undefined: function car() {
      console.log(this.name + ": " + car);
    }
undefined: function car() {
      console.log(this.name + ": " + car);
    }
himal@FakeBook practice % 

*/
```

**When using arrow**
```js
const obj = {
  name: "Tesla",
  cars: ["Model S", "Model 3"],
  showCars: function() {
    this.cars.forEach(car => {
      console.log(this.name + ": " + car);
    });
  }
};

obj.showCars();

//Output: 
//Tesla: Model S
//Tesla: Model 3
```


- `car => console.log(this.name)` is an **arrow function**
- **Arrow functions don’t have their own `this`** → they **inherit from the enclosing scope**
- Enclosing scope = `showCars` function → `this = obj`
- ✅ Output: `"Tesla"`

 Notice: **it does NOT inherit from `forEach`** because `forEach` itself does **not create a`this` for the callback** — the callback is just called normally by the engine.

---
```js
const actor = {
    name: "Himal",
    bow(){
        console.log(this.name);
    }
}
const detachedBow = actor.bow;

console.log(detachedBow());
```

---
![[42.png]]
Output: Himal Takes a bow

![[43.jpeg]]
Undefined Takes a bow