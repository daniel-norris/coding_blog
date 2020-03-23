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

