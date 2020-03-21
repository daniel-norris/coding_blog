## Object Orientated Programming in JavaScript

###### [Daniel Norris](https://github.com/daniel-norris), 21 March 2020 
 
###### [Home](./) > Object Orientated Programming in JavaScript

<br> 

Revisiting objects again on JavaScript by taking a look at the challenges available on [freeCodeCamp.com](www.freecodecamp.com).  

- Objects are filled with unordered data and organised into key-value pairs. Keys can be of any data type. 
- If a key does not have special characters then you don't need to use quotation marks. 
- The values are also referred to as properties and functions are referred to as methods. 

A quick example of a basic object includes: 
```javascript 
let dog = {
	name: "Spot",
	numLegs: 4
};
```
**Accessing properties**  
There are two ways to access properties: **dot notation** and **bracket notation**. 

```javascript
let dog = {
	name: "Spot",
	numLegs: 4
};
```
e.g. **bracket notation**.
```javascript 
let dog = {
	name: "Spot", 
	numLegs: 4
}; 

console.log(dog["name"]); 
// returns "Spot" 
```

**Creating a method**  
Similar to creating a **declarative function** just assign it a key. 

```javascript 
let  dog = {
	name: "Spot",
	numLegs: 4,
	sayLegs: function () {
		return  "This dog has " + dog.numLegs + " legs.";
	}
};
dog.sayLegs();
// returns "This dog has 4 legs."
```
**Using the `this` keyword**  
`this` refers to the parent object and helps to make code more maintainable if the objects key changes. 
```javascript 
let  dog = {
	name: "Spot",
	numLegs: 4,
	sayLegs: function() {return  "This dog has " + this.numLegs + " legs.";}
};

dog.sayLegs();
```
**Creating a constructor function**  
Constructor has a capitalised name to distinguish between normal functions. Uses the `this` keyword to define properties and methods for the object it will create. 

```javascript 
function  Dog () {
	this.name = "Spot",
	this.color = "Brown",
	this.numLegs = 4
}
```


