A prototype is an object from which other objects **inherit properties and methods** in JavaScript.
There is a **top-level (global) prototype** in JavaScript called:
 -> `Object.prototype`

`prototype` is a hidden internal link, not a normal property, so we use 🟢`Object.getPrototypeOf()` to safely access it. you cant access it by just ❌`this.prototype`



```js
const prithviraj = {
    name: "Prithviraj",
    generation : "grandfather",
    cookTraditionalDish(){
        return `${this.name} cooks an ancient faimily recipe`;
    },
};

const raj = Object.create(prithviraj);   //Here we define that proithviraj is                                                 Prototype of raj
console.log(raj);         //Output: {}
console.log(raj.name);    //Output: Prithviraj


//If we manually change the raj name in raj obj
raj.name = "Himal";
console.log(raj.name);  //Output: Himal

delete raj.name;
console.log(raj.name); // Output: Prithviraj  `It fall back to prototype`
```

**Object.create() vs proto Methods**

| Feature | Object.create() | __proto__ |
|--------|----------------|-----------|
| Purpose | Create a new object with a given prototype | Get/set prototype of an existing object |
| When used | During object creation | After object is created |
| Syntax | Object.create(proto) | obj.__proto__ = proto |
| Recommended | Yes (modern, standard) | No (legacy) |
| Performance | Better | Slower |
| Clean code | Cleaner | Less clean |
| Use case | Proper inheritance | Debugging / quick testing |

----
### Prototype Chaning
![[Pasted image 20260419093931.png|289]]

```js
let person = {
    name: "Himal",
}

let student = Object.create(person);
student.studentName = "Ram";

console.log(Object.getPrototypeOf(person)); //Output:[Object: null prototype] {}
console.log(Object.getPrototypeOf(student)); //Output: { name: 'Himal' }
```

---
Making own prototype for Array
```js
Array.prototype.last = function(arr){
    return this[this.length-1]
}

let arr = [1, 2, 3, 8, 17];

console.log(arr.last());
```