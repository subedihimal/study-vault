The `new` keyword in JavaScript is used to create an object from a constructor function or class.

It does the following:
- Creates a new empty object
- Links the object to the constructor’s prototype
- Binds `this` to the new object
- Executes the constructor function
- Returns the object

Why use `new`:
- To create multiple objects from the same blueprint
- To use prototypes (shared methods)
- To structure code in a reusable way

Example:
```js
function Person(name, age) {  
this.name = name;  
this.age = age;  
}  
  
const p1 = new Person("Himal", 25);

console.log(p1); //Output: Person { name: 'Himal', age: 25 }
```

---

❌ Now You may think why not just make it simple no need `this` and `new`  

**This is called a constructor method**
```js
function TataCar(chasisNumber, modelName){
	this.chassisNumber = chasisNumber;
	this.modelNumber = modelNumber;
	this.fuelLevel = 100;
}
TataCar.prototype.status = function(){
	return `Tata Nexon #MH-101 | Fuel: 100 Tata Nexon #MH-101 | Fuel: 100Tata ${this.modelName} #${this.chassisNumber} | Fuel: ${this.fuelLevel}`
}

const car1  = new TataCar("MH-101", "Nexon");
const car2 = new TataCar("DL-202", "Harrier");

console.log(car1.modelName);  //Nexon
console.log(car2.modelName); //Harrier
console.log(car1.status()); // Tata Nexon #MH-101 | Fuel: 100
console.log(car2.status()); ////Tata Harrier #DL-202 | Fuel: 100
```


**This is called a Factory method** -- This is not the same as above
```js
function createAutoRickshaw(id, route){
	return{
		id,
		route,
		run(){
			return `Auto ${this.id} running on ${this.route}`;
		},
	};
}
const auto1 = createAutoRickshaw("UP-1", "Lucknow-kanpu");
const auto2 = createAutoRickshaw("UP-2", "Agra-Mathura");

console.log(auto1.run()); //Auto UP-1 running on Lucknow-kanpu
console.log(auto2.run()); //Auto UP-2 running on Agra-Mathura
```


| Instance           | Constructor                                                                            | Factory Function                                                               |
| ------------------ | -------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------ |
| Memory             | Methods live on `prototype` → shared once<br>**10,000 objects = 1 shared method copy** | Methods recreated per object.<br>**10,000 objects = 10,000 method copies**<br> |
| Private state      | No real privacy (everything on `this`)                                                 | Closures allow real private variables                                          |
| `instanceof`       | Works (`obj instanceof Constructor` → true)                                            | Always false (no prototype link)                                               |
| Forgetting `new`   | Can break or pollute global (`this` issue)                                             | No issue as no need of `new` (normal function call)                            |
| `this` behavior    | Can break in callbacks, needs `.bind()`/arrow                                          | No `this` usage required                                                       |
| Return flexibility | Always returns same constructed object                                                 | Can return different shapes conditionally                                      |
| Inheritance        | Works naturally with `prototype` / `class`                                             | Not compatible with `class` inheritance                                        |
