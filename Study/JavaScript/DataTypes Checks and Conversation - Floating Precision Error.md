
Some Pre-Defined functions to check various Datatypes details

```js
// === Numbers ===  
let num = 23;  
console.log(Number.isNaN(num)); // false, checks if NaN  
console.log(Number.isFinite(num)); // true, checks if finite  
console.log(Number.isInteger(num)); // true, checks if integer 
console.log(Number.MAX_SAFE_INTEGER); // gives the value of maximum number
console.log(Number.MIN_SAFE_INTEGER); //gives the value of negative max number
 
  
// === Arrays ===  
let arr = [1, 2, 3];  
console.log(Array.isArray(arr)); // true, checks if array  
console.log(arr.includes(2)); // true, checks if value exists  
  
// === Null & Undefined ===  
let a = null, b;  
console.log(a === null); // true  
console.log(b === undefined); // true  
  
// === General Type Checks ===  
let str = "Hello", bool = true, obj = {x:1};  
console.log(typeof str); // "string"  
console.log(typeof bool); // "boolean"  
console.log(typeof obj); // "object"  
console.log(obj instanceof Object); // true  
  
// === Functions ===  
function greet() { return "Hi"; }  
console.log(typeof greet); // "function"  
console.log(greet instanceof Function); // true
```

---

## Converting via Different DataTypes

```js
const fuelReading = "142.75 tons";
const sectorCode = "0xA3";
const countDown = "007";

console.log(parseInt(fuelReading)); //Output: 142
console.log(parseFloat(fuelReading)); //Output: 142.72
console.log(parseInt(sectorCode)); //As 0x in front it will undarstand it as                                          hexcode so it will convert into decimal                                          while parsing
console.log(parseInt(countDown)) // OUTPUT: 7   ->As no value of 0 in front

console.log(parseInt("111", "2")); //Output:  -> Understands 111 as base 2 so                                         converts to decimal

const value = 4.567;
console.log(Math.round(value)); //Output: 5
console.log(Math.floor(value)); // Output: 4
console.log(Math.ceil(value)); // Output: 5
console.log(Math.trunc(value)); // Output : 4


const temp = [ -120, 43, 56, -23];
console.log(Math.min(temp)); // Output: -120
console.log(Math.max(temp));// Output: 56

```


---
## FLOATING POINT PRECISION ERROR

Numbers in computers are stored in binary (base 2). Just like `1/3` can't be written exactly in decimal (`0.333...`), many fractions can't be stored exactly in binary — they get stored with a tiny rounding error, and that error can cause surprising bugs.

## Why Only Some Numbers Are Exact

A fraction is stored exactly **only if its denominator is a power of 2** — because binary can only represent sums of ½, ¼, ⅛, ¼...

| Exact ✅ | Approximate ❌ |
|---|---|
| `1/2 = 0.5` | `1/5 = 0.2` |
| `1/4 = 0.25` | `1/10 = 0.1` |
| `1/8 = 0.125` | `1/6 = 0.1666...` |
| `3/4 = 0.75` | `5/3 = 1.6666...` |

> `3.7` is **not** exact — it equals `37/10`, and 10 has a factor of 5, so it can't be represented cleanly in binary.

**The Bug** 

Neither `0.1` nor `0.2` can be stored exactly, so their rounding errors combine when added: 
```js 
console.log(0.1 + 0.2); // 0.30000000000000004 console.log(0.1 + 0.2 === 0.3); // false ❌ 
```

**What's actually stored**

| Value       | Actually stored as         |
| ----------- | -------------------------- |
| `0.1`       | `0.1000000000000000055...` |
| `0.2`       | `0.2000000000000000111...` |
| `0.1 + 0.2` | `0.3000000000000000444...` |
| `0.3`       | `0.2999999999999999888...` |

 **Solutions**

**1. Epsilon Comparison** — don't check equality, check if the difference is too small to matter. `Number.EPSILON` ≈ 2.2e-16, the smallest representable difference between two floats.
```js
Math.abs(0.1 + 0.2 - 0.3) < Number.EPSILON  // true ✅
```

**2. toFixed() Rounding** — round to a fixed number of decimal places. Returns a string, use `+` to convert back to a number.
```js
const result = 0.1 + 0.2
result.toFixed(2)   // "0.30" → string
+result.toFixed(2)  // 0.3   → number ✅
```

**3. Decimal Library** — for financial or high-precision math, use a library that stores numbers as exact decimals rather than binary floats.
```js
new Decimal(0.1).plus(0.2).toString()  // "0.3" ✅
```

**When to Use Which**

| Method             | Use when                                                 |
| ------------------ | -------------------------------------------------------- |
| Epsilon comparison | Comparing values where tiny rounding errors are expected |
| `toFixed()`        | Displaying numbers or doing simple arithmetic            |
| Decimal library    | Currency, invoices, tax, or any exact decimal arithmetic |

---