Symbol is used to create unique datatypes even if their value is same.
```js
const id1 = Symbol("test");  
const id2 = Symbol("test");  

console.log(id1 === id2); // false

console.log(typeof id1); //symbol
console.log(id1.toString()); // Symbol(test)
console.log(id1.description); //test


const fakeId = Symbol();
console.log(fakeId.description) //undefined
```

---

**More DeepDive into symbol**

```js
const biometricHash = Symbol("biomertricHash");
const bloodGroup = Symbol("bloodGroup")
const citizenRecords = {
	name: "Himal",
	age: 21,
	[biometricHash]: "a7yb90",
	[bloodGroup]: "O+"
}

console.log()
```