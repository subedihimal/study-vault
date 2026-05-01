A class is a **blueprint for creating objects** with properties and methods.

**Constructor**
 A constructor is a **special method in a class used to initialize object properties when an object is created**.

*Although this can be easily achieved by function we use class to make it more safe as well as structured*
👉 **In JavaScript, a class is syntactic sugar over functions and prototypes. So basically internally it is a function**


```js
class Cricketer{
	constructor(name, role){
		this.name = name
		this.role = role
		this.matchesPlayed = 0
		this.stamina = 100
	}
	
	introduce(){
		return `${this.name} the ${this.role} | MatchesPlayed ${this.matchesPlayed}`
	}
}


const player1 = new Cricketer("Himal", "BatsMan");
const player2 = new Cricketer("Ram", "FootBall");

console.log(player1);
console.log(player2);

console.log(typeof Cricketer); //Function
console.log(player1.hasOwnProperty("name")); //true


/* Output
ricketer {
  name: 'Himal',
  role: 'BatsMan',
  matchesPlayed: 0,
  stamina: 100
}
Cricketer {
  name: 'Ram',
  role: 'FootBall',
  matchesPlayed: 0,
  stamina: 100
}
*/
```


---
```js
class Speaker{
    constructor(name){
        this.name = name
        this.walkOut = function() { return`${this.name} walks out to bat for the first time`}
    }
}
const first = new Speaker("Himal");
const second = new Speaker("Ram")

console.log(first.walkOut === second.walkOut). // False

/* Here
first.walkOut → new function  
second.walkOut → new function
*/
// This is more safe Private cant be accessed


//---------------------------------------------------------------

class Speaker {
	 constructor(name) { 
		 this.name = name; 
	} 

	walkOut() { 
		return `${this.name} walks out to bat for the first time`; 
	} 
} 
const first = new Speaker("Himal");
const second = new Speaker("Ram"); 
console.log(first.walkOut === second.walkOut); // True

/* Here 
first.walkOut → new function  
second.walkOut → new function

This is less safe but memory Efficient
*/
```
Here