
**VAR has global scope where as  LET and CONST are blocked scope**


**Primitive DataTypes (Stored Directly in Stack so fast access) :** simple, immutable values stored directly (Number, String, Boolean, Undefined, Null, Symbol, BigInt).

 **Non-Primitive Data types (Reference stored in stack, actual data in heap):** complex values stored by reference, like Objects, Arrays, and Functions

---
**Const and Objects**
```js
const tresureChest = {
	"gold" : 30,
	"rubies“ : 50,
	"maps" : 10
}

tresureChest.gold = 30 //  Allowed to manupulate Content
treasureChest["silver"] = 20; // Allowed to add

tresureChest = { 
	"gold": 100
}                     // Creates New refrence - NOT ALLOWED WHEN Object is const 
```

**Const and arrays**
```js
const crew = [ "Ram", "Shyam" ];
crew.push("Himal"); // Allowed
crew[0]= "Ramesh"; // Allowed

crew = ["Hari"];  // Not allowed
```

**Const and Array of Objects**

```js
const crew = [  
{ name: "Ram", role: "dev", exp: 2 },  
{ name: "Shyam", role: "tester", exp: 1 }  
];  
  
// ✅ Allowed (push new object)  
crew.push({ name: "Himal", role: "manager", exp: 5 });  
  
// ✅ Allowed (modify object inside array)  
crew[0].name = "Ramesh";  
crew[1].exp = 3;  
  
// ❌ Not allowed (reassign whole array)  
crew = [  
{ name: "Hari", role: "dev", exp: 4 }  
];
```

---
Type of null is an Object it was a bug and they kept it that way so old code doesn't break
```js
let fruits = null;
console.log(typeof fruits).  //Output: object
```

---
### Symbol (Datatype is Symbol only)
Symbol guarantees the uniqueness of datatypes and Immutability.
```js
const id1 = Symbol("id");  
const id2 = Symbol("id");  // Although label is same they are unique
  
console.log(id1 === id2); // false ❌ (always unique)

//Printing may work properly in vs-code but lot of time breaks in prod, So when printing Symbol convert to string
const test = Symbol("test_symbol");

console.log(test.toString()); //Best Practice
```

---

**Function Datatype when check typeof show function but it is also object in js**

```js
function spell(){ return "fireball"; }
console.log(typeof spell);   //Output function but is also and object internally
```

---

## Various type of with their output

```js
console.log(typeof 42); // "number"  
console.log(typeof 42n); // "bigint"  
console.log(typeof "ram"); // "string"  
console.log(typeof null); // "object" (historical JS bug)  
console.log(typeof undefined); // "undefined"  
console.log(typeof true); // "boolean"  
console.log(typeof Symbol()); // "symbol"  
console.log(typeof function(){});// "function"  
console.log(typeof {}); // "object"  
console.log(typeof []); // "object" (arrays are objects)
```

---
