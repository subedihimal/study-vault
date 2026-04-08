Two ways to access an object
. and []

**[] useful when there is space in the key**
```js
const hero = {
    name: "Himal",
    "class Name": "Bachlor",
    health: 45
}
console.log(hero.class Name); //Error
console.log(hero["class Name"]); //works
```

**[] is also useful with dynamic key**

```js
const hero = {
    name: "Himal",
    "class": "Bachlor",
    health: 45
}

const key = "class";

hero.key;             //Doesnt Work
hero[key]             //Does Work
```


**delete and in method**
```js

const ranger = {
	name: "Himal",
	ability : 80,
	stealth: undefined
}

console.log("name" in ranger); // true
console.log("stealth" in ranger) // true

delete ranger.ability; //Deletes the entry of ability in obj

```

### Problem with in method
```js
const ranger = {
	name: "Himal",
	ability : 80,
	stealth: undefined
}

console.log("toString" in ranger); //true BECAUSE IT INHERIT DIFFERENET                                                PROPERTIES FROM PROTOTYPE

//To aviod this use
console.log(ranger.hasOwnProperty("toString")); //false


const keys = Object.keys(ranger);      //[ 'name', 'ability', 'stealth' ]
const values = Object.values(ranger);   //[ 'Himal', 80, undefined ]
const entries = Object.entries(ranger) 
// [ [ 'name', 'Himal' ], [ 'ability', 80 ], [ 'stealth', undefined ] ]
```


### Converting Objects into arrays and vice versa

```js
const ranger = {
	name: "Himal",
	ability: 80,
	stealth: undefined
};

const entries = Object.entries(ranger); // Ouput: [ [ 'name', 'Himal' ], [ 'ability', 80 ], [ 'stealth', undefined ] ]

const againObj = {}; // ✅ initialize as object

for (const [key, value] of entries) {
    againObj[key] = value;
}

console.log(againObj);


// ==========================  
// ⭐ BEST METHOD (BUILT-IN)  
// ==========================  
  
// Directly convert entries → object  
//Object.entries() converts object → array of `[key, value]` pairs  
//Object.fromEntries(). converts *array of `[key, value]` pairs → object

 const best = Object.fromEntries(Object.entries(ranger));  
  
console.log(best);  
// { name: "Himal", ability: 80, stealth: undefined }
```


----
**Freeze and seal Methods**

```js
const arr = {
    artifact: "Obsidian",
    location: "Hall A, Case 3",
    locked: true
}

Object.freeze(arr)

delete arr.artifact; // Wont Work as object is Freeze
arr.location = "Jawlakhel" // Wont work
```

```js
//Seal add edit but no delete and add
const arr = {
    artifact: "Obsidian",
    location: "Hall A, Case 3",
    locked: true
}

Object.seal(arr)
arr.location = "Jawlakhel" // Allows editing existing data


delete arr.artifact; // Wont Work as object is Freeze

```

---
## Define property and Define Properties

defineProperty gives you access to various other properties of the object like writable, enumerable and configurable
```js
const secureArtifacts = { name : "Ruby Pendant"}

Object.defineProperty(secureArtifacts, "catelogId" , {
	value: "Sec-999",
	writable: false,
	enumerable: true,
	configurable: false
});

console.log(secureArtifacts) 
//Output: { name: 'Ruby Pendant', catelogId: 'Sec-999' }


secureArtifacts.catelogId = "test";     // As writable is false wont change


for(const[key, value] of Object.entries(secureArtifacts)){
	console.log(`${key}: ${value}`);  // If enurable is false it wont show catelogId Currently it is true so it shows categoryId details
}


//To check this properties
console.log(Object.getOwnPropertyDescriptor(secureArtifacts, "catelogId"));
```

**Object.defineProperties**
```js
const obj = {};  
  
Object.defineProperties(obj, {  
name: {  
value: "Himal",  
writable: false  
},  
age: {  
value: 22,  
writable: true  
}  
});  
  
console.log(obj);
```