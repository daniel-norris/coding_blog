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
And using the constructor to create a new object: 

```javascript 
function  Dog() {
	this.name = "Rupert";
	this.color = "brown";
	this.numLegs = 4;
}
let  hound = new  Dog();

console.log(hound);
// returns { name: 'Rupert', color: 'brown', numLegs: 4 }
```
Using constructor to create a new object and passing arguments as parameters: 

```javascript 
function  Dog(name, color) {
	this.name = name,
	this.color = color,
	this.numLegs = 4
}

let  terrier = new  Dog("Spot", "Brown");
console.log(terrier); // returns { name: 'Spot', color: 'Brown', numLegs: 4 }
console.log(terrier.name); // returns Spot
```
**Check objects constructor using `instanceof`**
You can check the parent constructor for  an instance using `instanceof`. Returns a bool value. 

```javascript 
function  House(numBedrooms) {
	this.numBedrooms = numBedrooms;
}

let  myHouse = new  House(3);
// console.log(myHouse);
myHouse  instanceof  House; // returns true
```
### Types of Properties

**Object own properties** 
In the example below, `name` and `numLegs` are own properties as they are defined directly on the instance object of `canary`. This pushes all the own properties to a new array called `ownProps`. 

```javascript 
function  Bird(name) {
	this.name = name;
	this.numLegs = 2;
}
let  canary = new  Bird("Tweety");
let  ownProps = [];

for (let  property  in  canary) {
	if (canary.hasOwnProperty(property)) {
		ownProps.push(property);
	}
}
console.log(ownProps); // returns ['name', 'numLegs']
```
**`prototype` properties to reduce code**
Might need to revisit this but the principle here is that using `prototype` reduces duplicate code in lieu of using the `this` keyword to assign common variables to new instances. In the example below, all new instances of the `Dog` constructor will have a `numLegs` property. 

```javascript 
function  Dog(name) {
	this.name = name,
	Dog.prototype.numLegs = 2
}
let  beagle = new  Dog("Snoopy");
console.log(beagle.numLegs); // returns 2
```
**Iterate over all properties** 
Own properties are defined on the instance itself and `prototype` properties are defined on the prototype. 

You can iterate over this using the `hasOwnProperty`method. 

```javascript 
function  Dog(name) {
	this.name = name;
}

Dog.prototype.numLegs = 4;
let  beagle = new  Dog("Snoopy");
let  ownProps = [];
let  prototypeProps = [];

for (let  property  in  beagle) {
	if (beagle.hasOwnProperty(property)) {
		ownProps.push(property);
	} else {
		prototypeProps.push(property);
	}
}
console.log(ownProps); // returns ['name']
console.log(prototypeProps); // returns ['numLegs']
```
**The `constructor` property** 
You can use the `constructor` property to check what constructor function created the instance. 

Since you can change or overwrite the constructor property its generally better to use `instanceOf` method to check the type of an object. 

```javascript
function  Dog(name) {
	this.name = name;
}

function  joinDogFraternity(candidate) {
	if (candidate.constructor === Dog) {
		return  true;
	} else {
		return  false;
	}
}

let  labrador = new  Dog();

console.log(joinDogFraternity(labrador)); // returns true

console.log(labrador.constructor === Dog); // returns true
```
### The prototype 
**Changing `prototype` to a new object** 
Instead of adding properties to the prototype individually, you can set them to a new object so they are all added at once. 

```javascript
function  Dog(name) {
	this.name = name;
}
Dog.prototype = {
	numLegs: 2,
	eat: function() {
		console.log("nom nom nom");
	},
	describe: function() {
		console.log("My name is " + this.name);
	}
};
```
**Set the `constructor` property when changing `prototype`**
If you manually set the prototype to a new object it deletes the constructor property. So you need to set it manually. 

```javascript 
function  Dog(name) {
	this.name = name;
}
Dog.prototype = {
	constructor: Dog,
	numLegs: 4,
	eat: function() {
		console.log("nom nom nom");
	},
	describe: function() {
		console.log("My name is " + this.name);
	}
};
```
**`isPrototypeOf` method**
Objects inherit prototype directly from the constructor function. You can use `isPrototypeOf` to check the prototype of an instance. 

```javascript 
function  Dog(name) {
	this.name = name;
}
let  beagle = new  Dog("Snoopy");

Dog.prototype.isPrototypeOf(beagle);
```
**The `prototype` chain**
(Almost) all objects in JavaScript can have a prototype. Prototypes can have their own prototypes which are also objects. The prototype of `Dog.prototype` is `Object.prototype`. `Dog` is the `supertype` for `beagle` and `beagle` is the `subtype`. `Object` is the `supertype` for both. 

```javascript 
function  Dog(name) {
	this.name = name;
}
let  beagle = new  Dog("Snoopy");

Dog.prototype.isPrototypeOf(beagle); // yields true

Object.prototype.isPrototypeOf(Dog.prototype);
```
