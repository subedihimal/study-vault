Declaring Strings in js
```js
//Declaring Strings
const codeName = "Shadow Fox";
const backupName = String("Night Own");
const templateName = `Agent ${codeName}`;

const example = `
 ${check? "true" : "false"}
`

let intecepted = "HELLO";
intercepted[0] = "J"        // WONT CHANGE ANYTING WONT GIVE ERROR "SILENT FAIL"

```

Various available methods of strings

```js
const secretCode = "OMEGA-7";

console.log(secretCode.length);
console.log(secretCode.charAt(2));   // Can find where
console.log(secretCode.at(-1));   // Output = 7 , "-" means from oposite side

//What if you give index which is not defined

console.log(secretCode[10]);         //Undefined
console.log(secretCode.at(-10));      // Undefined
console.log(secretCode.charAt(15));   // Empty string output
```

More Methods
```js
const a = "HImAl"

console.log(a.toLowerCase());
console.log(a.toUpperCase());

//Searching
const message = "The drop point is at Drop 7. hello";

console.log(message.indexOf("Dock"));

// Split Method
const orders = "move-north|hold-position|extract"
let orderList = orders.split("|");        // Splits where there is |

console.log(OrderList); //Output: [ 'move-north', 'hold-position', 'extract' ]
console.log(Array.isArray(orderList));  // Output: yes

console.log ("SOS".split("")); //Output: [ 'S', 'O', 'S' ]
```

Trim
```js
const a = " Hima l       ";
console.log(a.trim(" "));     //Output : "Hima l"

const b = "Ram";
console.log(b.padStart(6, "0")); //Output: "000000Ram"
console.log(b.padEnd(6, "0")); //Output: "Ram000000"

```

**.replace is also there to replace a value in string**

---
To destroy variable after use
```js
let a = "Ram";

a = undefined;       //Also a way but not so prefered as it may be undefined as                         developer forgot to assign a value to the variable
a = null;           //NULL prefered as it means intentionally made null by                             developer
```