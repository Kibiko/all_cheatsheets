# FrontEnd Cheatsheet

# Table of Contents

- [FrontEnd Coding -](#)
    * Week 8 -
        * <details><summary><a href="#introduction">Introduction</a></summary>
            - <a href="#javascript-vs-java">JavaScript vs Java</a></details>
        * [Node.js](#nodejs)
        * [JavaScript Shortcuts](#javascript-shortcuts)
        * <details><summary><a href="#javascript-basics">Basics</a></summary>
            - <a href="#formatting">Formatting</a><br>
            - <a href="#conditionals">Conditionals</a><br>
            - <a href="#arrays">Arrays</a><br>
            - <a href="#objects">Objects</a><br>
            - <a href="#loops">Loops</a></details>
        * [Scope](#scope)
        * [Functions](#functions)
        * [Package Management Tool](#package-management-tool)
        * <details><summary><a href="#testing">Testing</a></summary>
            - <a href="#importing-and-exporting-functions">Importing and Exporting</a><br>
            - <a href="#test-coverage">Test Coverage</a></details>
        *  <details><summary><a href="#constructors--prototypes">Constructors & Prototypes</a></summary>
            - <a href="#modules">Modules</a><br>
            - <a href="#inheritance">Inheritance</a><br>
            - <a href="#higher-order-functions">Higher Order Functions</a></details>
        * <details><summary><a href="#enumeration">Enumeration</a></summary>
            - <a href="#mapping">Mapping</a><br>
            - <a href="#filtering">Filtering</a><br>
            - <a href="#reducing">Reducing</a></details>
        * <details><summary><a href="#html-css-javascript">HMTL-CSS-JavaScript</a></summary>
            - <a href="#ux-user-experience">UX - User Experience</a><br>
            - <a href="#wireframe">Wireframes</a><br>
            - <a href="#semantic-html">Semantic HTML</a></details>
        * <details><summary><a href="#duck-appreciation-example">Duck Example</a></summary>
            - <a href="#useful-links">Useful Links</a></details>
        * <details><summary><a href="#art-website-example">Art Website Example</a></summary>
            - <a href="#useful-css">Useful CSS</a></details>
        * [Web Content Accessibility Guidelines](#web-content-accessibility-guidelines)
    * Week 9 - 
        * [DOM - Document Object Model](#dom---document-object-model)
        * <details><summary><a href="#functionality-events">Functionality (Events)</a></summary>
            - <a href="#favicon">Favicon</a><br>
            - <a href="#buttons">Buttons</a></details>
        * [ToDo List](#to-do-list)
        * <details><summary><a href="#synchronicity">Synchronicity</a></summary>
            - <a href="#promise">Promise</a><br>
            - <a href="#response">Response</a><br>
            - <a href="#db-serialisation">DB Serialisation</a><br>
            - <a href="#asyncwait">Async/Await</a></details>
        * [Handling Objects in JSON](#handling-objects-in-json-data)
        * <details><summary><a href="#react">REACT</a></summary>
            - <a href="#destructuring">Destructuring</a><br>
            - <a href="#intro">Intro</a><br>
            - <a href="#getting-started">Getting Started</a><br>
            - <a href="#components">Components</a></details>
        * [Bakery - Cake Example](#bakery---cake-example)
        * [CI & CD](#cicd)
        * [Errors and Exceptions](#errors-and-exception)
    * Week 10 -
        * [Bakery - Extended Example](#bakery---extended-example)
        * <details><summary><a href="#useeffect---colour-picker">UseEffect - Colour Picker</a></summary>
            - <a href="#sliders">Sliders</a><br>
            - <a href="#implementing-useeffect">Implementing UseEffect</a></details>
        * [Data Loading and UseEffect](#data-loading-and-useeffect)
        * <details><summary><a href="#linking-front-end-to-back-end">Linking Front End to Back End</a></summary>
            - <a href="#issues">Issues</a></details>
        * <details><summary><a href="#react---final-tips">React - Final Tips</a></summary>
            - <a href="#front-end-project">Front End Project</a></details>
        * [Retrospective](#retrospective)

## Introduction

`Highlight` + `[cmd + D]` (as many times as possible) + edit

`[cmd + ctrl + space]` emoji entering

![intro](/images/javascript_intro.png)

### JavaScript vs Java

**Java -**
- statically typed and compiled
- more robust since things can not be reassigned a different datatype

**Javascript -** 
- dynamically typed interpreted language
- useful for flexible in front end

e.g. 

***Java***

```java
Bear bear = new Bear("Baloo");
bear = new Cat() does not work
```

***JavaScript***

```js
bear = new Bear()
bear = "lol"
```

**Java and JavaScript has nothing to do with each other!! It used to be called LifeScript but was renamed just because Java was the most important back end language at the time.**

Official name of JavaScript is ECMAScript.

**Node.js** is javascript but for backend!

## Node.js

|No.	|Javascript	|NodeJS|
|------------|----------------|---------------|
|1.	|Javascript is a programming language that is used for writing scripts on the website.	|NodeJS is a Javascript runtime environment.|
|2.|	Javascript can only be run in the browsers.	|We can run Javascript outside the browser with the help of NodeJS.
|3.|	It is basically used on the client-side.	|It is mostly used on the server-side.
|4.|	Javascript is capable enough to add HTML and play with the DOM.	|Nodejs does not have capability to add HTML tags.
|5.|	Javascript can run in any browser engine as like JS core in safari and Spidermonkey in Firefox.	|V8 is the Javascript engine inside of node.js that parses and runs Javascript. 
|6.|	Javascript is used in frontend development.	|Nodejs is used in server-side development.
|7.|	Some of the javascript frameworks are RamdaJS, TypedJS, etc. |Some of the Nodejs modules are Lodash, express etc. These modules are to be imported from npm. 
|8.|	It is the upgraded version of ECMA script that uses Chrome’s V8 engine written in C++.|Nodejs is written in C, C++ and Javascript.

In terminal we can use `node` to enter the REPL and code `js` in the terminal environment. `CTRL` + `D` to exit the environment. Instead we will be writing scripts in Visual Studo Code.

## JavaScript Shortcuts

|Syntax|Description|
|------|------|
|log + `TAB`|autocompletes `console.log()`|
|`node [js file]`| runs file in terminal |
|`node --print-bytecode [file]`|shows what it takes to compile and run the code|

## JavaScript Basics

### Formatting

We can format a String through `${}`. Inside the curly braces we can put any kind of operation and it will execute it. e.g. `2 + 2` , `temperature * 2` , `personName + [other String]`

```js
personName = "Ed";
temperature = 36;

console.log(`Hello ${personName}`);
console.log(`The temperature is ${temperature} degrees today`); //much simpler than python format!
```

### Conditionals

`1 == "1"` - returns true as JavaScript asks, "Can we make it work?"

`1 === "1"` - checks the data type as well, therefore this is much more reliable in the beginning as we are used to statically typed languages

`!==` - three symbols is always going to be data type check compared to `!=`

`"a" < "b"` - can be used for alphabetic checks

e.g.

```js
if(userGuess === secretNumber){
    console.log(`Congrats, good guess, the secret number was ${secretNumber}`);
} else if (userGuess > secretNumber){
    console.log("Guessed too High");
} else {
    console.log(`Guessed too Low, guess again`);
}
```

Everything has a **TRUTHY** or **FALSY** value. Therefore just the number `15` counts as a true boolean for conditionals. This is the same for Strings. Both are inherently **TRUTHY**.

```js
loggedInUser = null;
loggedInUser = "Zsolt" //if this line is commented out, then falsy

if(loggedInUser){
    //execute code
}
```

### ***Falsy values:***

- `0`
- `null`
- `""`
- `NaN`
- `undefined` (when forgotten to initialise with a value)

### Type Coercion

This is JavaScript trying to make things work, providing flexibility so that it does not break down.

e.g.

`55 + "hello"` - makes entire of it a String

`[ ] + " "` - allowed

`5 + [ ]` - also fine

`[ ] + { }` - array + object gives `[object Object]`

### Arrays

We can define an empty array through `longArray = Array(16)` with a certain size or through setting values,

```js
emptyArray = [];
numbers = [1, 2, 3, 4 ,5];
letters = ['a', 'b', 'c', 'd'];
badIdea = [0, "a", true, numbers];
```

|Methods|Syntax|Description|Returns|
|----|----|----|----|
|add| `myArray.unshift([value])`|adds an element to the front of the array|array length|
|add|`myArray.push([value])`|adds an element to the array at the end|array length|
|add| `myArray.splice(index, 0, value)`| adds the element into the array at index|
|access| `myArray[index]`|accesses the element at index|<-|
|size|`myArray.length`|the length of the array|<-|
|remove| `myArray.shift()`| removes the ***first*** element| element removed|
|remove| `myArray.pop()`| removes the ***last*** element of the array| element removed|
|remove| `myArray.splice(index, amount)`| removes a certain amount of elements at index and after|
|contains|`myArray.includes(value)`|returns true if array contains value| true or false|
|index| `myArray.indexOf(value)`| returns (first?) index of the value in the array|
|sort| `myArray.sort()`| sorts the array by numerical or alphabetical order|


### Objects

We can define an object just as we expected from a JSON body.

```js
alice = {
    name : 'Alice',
    age : 21,
    favColour : 'blue',
    pets: ['bobby','callum']
};

bob = {
    age: 28,
    name: 'Bob',
    favColour: 'blue'
};
```

Keys **can not** start with a number, have to be unique and naming is important! 

We can access an objects properties through `alice.pets` or `alice["pets"]`. If the key has a weird name (e.g. has a hyphen), the latter is needed to access it.

Sometimes we want to grab the key and access it rather than modifying it directly through the above.

```js
cat = {
    name: 'Cuddles',
    age: 15
}

key = 'name';
cat[key] = 'Fluffy';
cat.breed = 'calico';
```

|Methods|Syntax|Description|
|----|----|----|
|add|`myObject.[new key name] = [value]`|we can add a property just by calling it in .js|
|remove| `delete myObject.[key]`|removes the key from the object|
|keys| `Object.keys([object name])`| returns all the keys of the object as an array|
|values| `Object.values([object name])`| returns all the values of the object as an array|

### Loops

Similar to other codes,


***For***
```js
shoppingList = ['milk', 'eggs', 'bread', 'apples', 'kimchi', 'tea'];

for (item of shoppingList){
    console.log(item.toUpperCase()); //same method for Strings
}

for (index = 0; index < shoppingList.length; index++) {
    console.log(shoppingList[index]);
}

for (index = shoppingList.length-1; index > -1 ; index--) { //reverse order
    console.log(shoppingList[index].toUpperCase());
}

//looping through objects

for (key in alice){ //simple
    value = alice[key];
    console.log(`The ${key} is ${value}`);
}

for (key in alice) { //default
    if (Object.hasOwnProperty.call(alice, key)) {
        element = alice[key];
        console.log(element);
    }
}
```

***While***
```js
counter = 0;

while (counter<10){
    console.log(counter);
    counter++;
}

while(true){
    rand = Math.random(); //random number between 0,1
    console.log(rand);
    if(rand>0.9){
        break;
    }
}
```

## Scope

By default all variables are available on a global scope. To counter this, we can manage the scope through,

### Block scoped - `const` and `let`

This only allows the block `({ })` to access this.

```js
let age = 25; //allows reassigning
const name = "Yuko"; //should not be changed and prevents it
```

### Lexical Scope

Defining outside of the block will allow it to be accessed. This is similar to the parent, child relationship we have in Java. e.g,

```js
let numberToPrint = 0;

for(let number of numbers){
    numberToPrint = number; // can access variable outside the block
    console.log(`Value of number inside loop: ${numberToPrint}`);
}
```

### Examples

```js
numbers = [1, 2, 3, 4, 5];

for(number of numbers){
    console.log(`Value of number inside loop: ${number}`);
}

console.log(number)
```

The above code, the `number` in the for loop is globally available, making it possible to print out another `5` at the end. Instead, we can add the type `let`,

```js
for(let number of numbers){
    //code
}
```

which makes it unavailable outside the loop. This brings up an error when we try to print out `number` outside the block.

When dealing with Arrays, you can add and remove from the array even though it's a `const myArray;`. You can even change the values of the elements. However you can not assign it to be a different array. e.g. `myArray = diffArray;`

This is the same with objects.

## Functions

Order of named functions does not matter as JavaScript hoists functions to the top. This is due to the interpreter. Below we have examples of named functions,

```js
// named functions
function greet(timeOfDay, name){
    console.log(`Good ${checkTime(timeOfDay)}, ${name}`);
}

function checkTime(number){
    if(number< 12){
        return "morning";
    } else if(number>=12 && number <18){
        return "afternoon";
    } else{
        return "evening";
    }
}

greet(19,`Kevin`);
```

Anonymous functions do not have a name and can be assigned to a variable,

```js
//anonymous functions
const sum = function(number1, number2){
    return number1+number2;
}

console.log(sum(1,2));
```

Named functions are not as common, instead usually it's a safe bet to have anonymous functions which can be set to a variable and passed around the code. **Anonymous functions** order does matter!! This is not hoisted by the interpreter. Should default to anonymous functions.

**Arrow functions** came in at ES6, 

```js
//arrow functions
const multiply = (number1, number2) => { //longer implementation
    return number1 + number2;
}

OR

const multiply = (number1, number2) => number1 + number2; //simpler with implicit return

console.log(multiply(2,5));
```

This is much simpler out of the three and since it has come in recently, not as much use as anonymous functions but should be a nice default as well for future.

## Package Management Tool

Packages are code that other people have written which can be used. These are essentially libraries in Python.

Maven is a PMT that we are used to. Gradle is also another. Both can do similar things but not everything that each can do.

In JavaScript, we have NPM and yarn. 

NPM is Node Package Manager. Essentially how it works is that if a package relies on another one and that relies on another etc, this helps make sure you have the dependencies needed. 

### Setup

(Npm should come with node)

`npm init` in the terminal at the root folder *(like git)* 

Hit `enter` and can add description, entry point, test command, git repository and keywords. The flag `-y` after `npm init` skips through all.

This creates a `package.json` file.

`npm install [package name]` or `npm i [package name]` installs a package

```js
//package.json
{
  "name": "npm_intro",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "author": "Kibiko",
  "license": "ISC",
  "dependencies": {
    "five": "^0.8.0" //dependency added, the ^ means it takes most updates or 0.8.0
  }
}
```

A new file called `package-lock.json` is created along with a `node_modules` folder. The `package-lock.json` file should not be changed as it keeps the specific version of the dependency. The `node_modules` folder is one thing to be very familiar with.

This folder contains the code where the dependency is. This contains the source code, ignores, readmes etc. This gives you everything to inspect and change however you want.

If the `node_modules` folder is nuked, you can use `npm install` to get the package back. This way, you do not have to send over the entire node_modules folders but just the `package.json` since it has the dependencies needed. This also helps with storage, you can always remove the node modules when the project is not in use and install it when needed.

NOTE: Always create a `.gitignore` file that ignores `node_modules`.

*.gitignore*
```
node_modules
```

### Using Packages

We can import the package into a file through,

```js
const five = require("five");

console.log(five.japanese());
```

Now we can call the methods of the package which we assigned `five` to be.

## Testing

Most popular packages are chai, mocha and jest. Jest by far is the most downloaded testing package with regular support.

`npm install -D jest` - the extra flag makes devDependencies rather than dependencies in the `package.json` file. The testing package is only useful for the developers and not the end user. This is why we need the tag for Jest. If we publish the code, Jest will not be a part of it.

### Importing and Exporting Functions

To import functions, we have to make sure to export them first from the file.

```js
//calculator.js
const sum = (number1, number2) => {
    return number1 + number2;
}

module.exports = {sum} //needed to make function avaiable globally
```

A test file should always have the naming convention `[name].test.js`,

```js
//calculator.test.js
const {sum} = require('./calculator'); //imports sum function from calculator.js 
                                       //through file path ./calculator
```

To use the Jest testing framework, we call the `test()` method with arguments,

```js
test("can add two small positive numbers", () => {
    //Arrange
    const expected = 5;
    //Act
    const actual = sum(2,3);
    //Assert
    expect(actual).toBe(expected);
})
```

To run our package of test and calculator, we modify the scripts in `package.json`,

```js
"scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  }

===========>

"scripts": {
    "test": "jest"
  },
```

When we run `npm test`, it runs the tests for us and spits out the results of the tests. In reality we need more than just one test for a function. A good way to distinguish between blocks of tests is by adding a `describe()`,

```js
//calculator.test.js
const {sum} = require('./calculator');

describe('addition functionality', () => {

test("can add two small positive numbers", () => {
    //Arrange
    const expected = 5;
    //Act
    const actual = sum(2,3);
    //Assert
    expect(actual).toBe(expected);
});

test("can add two small negative numbers", () => {
    //Arrange
    const expected = -12;
    //Act
    const actual = sum(-7,-5);
    //Assert
    expect(actual).toBe(expected);
});

});
```

### Test Coverage

To add test coverage in JavaScript, we add a new script in the `package.json`,

```json
"scripts": {
    "test": "jest",
    "test:coverage": "jest --coverage"
  },
```

We then call it through `npm run test:coverage` since this script is a custom one that we have made to test the coverage of our code. This creates a `coverage` folder which shows the reports in the `lcov-report`. Handily, we have the `index.html` file which can be opened in browser to show the coverage in a nice way.

## Constructors & Prototypes

### Constructors

In JavaScript, we can use a function like a class and constructor without needing to define the properties of the class beforehand. Constructors by default is capitalised and at the same time, methods can be included in the function,

```js
const User = function(name, age, email){
    this.name = name;
    this.age = age;
    this.email = email

    this.setName = (newName) => { //inefficient
        this.name = newName;
    }
}

const user = new User("Kevin", 30, "kevinjunchan@gmail.com")
user.setName("Bob");
```

However we end up with a redundancy where the method is included in every object that we have created. Therefore it is not useful to put the method with the constructor. Instead we put it in as a prototype.

### Prototypes

This allows us to define methods outside of the constructor. NOTE: lambdas (=>) do not work as a method definer in a prototype. We have to use an anonymous function instead,

```js
User.prototype.setName = function(newName) {
    this.name = newName;
}

const kevin = new User("Kevin", 30, "kevinjunchan@gmail.com");

kevin.setName("Bob");
```

### Modules

We can export the constructor and methods to be available to other files (modules), similar to when we exported the function for testing where we used `module.exports = {sum}`. In our case, we export from the constructor,

```js
//User.js

//constructor, getters and setters, methods

module.exports = User;
```

and in the modules that we use the class,

```js
//index.js

const User = require("./User");

//use methods and create objects
```

### Inheritance

### Employee Module

In order to implement inheritance in JavaScript, we can import the `User` class into another class. In our example we create an `Employee` class.

```js
const User = require("./User");

const Employee = function(name, age, email, role){
    User.call(this, name, age, email);
    this.role = role;
}

Object.setPrototypeOf(Employee.prototype, User.prototype);

const jack = new Employee("Jack", 21, "jack@gmail.com", "Software Engineer");
jack.setName("Jimbo");
```

In the `Employee` constructor, similar to super in Java, we call the properties from the `User` class through `User.call(this, [properties])`. In order to inherit the methods as well, we include the `Object.setPrototypeOf()` method to make Employee prototypes from User prototypes.

We can also check if the Employee is a child of the User module through,

`console.log(jack instanceof User);`

### Customer Module

We also create a `Customer` module which extends the `User` module and inherits the methods while having a new property and methods related to `billingAddress`.

```js
const User = require("./User");

const Customer = function(name, email, billingAddress) {
    User.call(this, name, email);
    this.billingAddress = billingAddress;
}

Customer.prototype.getBillingAddress = function() { return this.billingAddress; }
Customer.prototype.setBillingAddress = function(billingAddress){
    this.billingAddress = billingAddress;
}

Object.setPrototypeOf(Customer.prototype, User.prototype);

module.exports = Customer;
```

### Higher Order Functions

We can have higher order functions, meaning functions nested inside another function. We can take in a function as an argument to be used. e.g. calculator,

```js
const sum = (number1, number2) => {
    console.log(number1 + number2);
};

const subtract = (number1, number2) => {
    console.log(number1 - number2);
};

const multiply = (number1, number2) => {
    console.log(number1 * number2);
}


const doCalculation = (number1, number2, callback) => {
    callback(number1, number2);
};

doCalculation(4,5,multiply);
doCalculation(4,5,sum);
doCalculation(4,5,subtract);
```

Whenever we pass in a function into a different one, we need to name it `callback` for convention. Another way to define a callback is through putting the method into the argument itself,

```js
doCalculation(2,3, (number1, number2) => {
    console.log(number1 / number2);
});
```

This is mostly used for situational problems where the function does not need to be called over and over.

## Enumeration

Instead of for loops to print out elements in an array, we can use higher order functions,

```js
const numbers = [1, 2, 3, 4, 5];
const letters = [`a`, `b`, `c`, `d`, `e`];

const printElement = (arrayElement) => {
    console.log(arrayElement);
};

numbers.forEach(printElement);
letters.forEach(printElement);
```

This way, we can make it much simpler to alter and change if needed. The `forEach()` method for Arrays takes in a function that will apply it to every element in the array. More methods are included in [Arrays Prototypes](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array).

### Mapping

`Array.prototype.map()` takes in a function, `f(x)` and applies to to every element in the array and creates a new array with the function applied, `[f(x_1), f(x_2), f(x_3) etc...]`

e.g.

```js
const numbers = [1, 2, 3, 4, 5];

const doubledNumbers = numbers.map((number) => {
    return number * 2;
});

console.log(doubledNumbers);
```

This is essentially the same as `forEach()` but a new array is returned. This is useful for an Array of objects to get values. e.g. people array with person objects with a name property.

### Filtering

`Array.prototype.filter()` creates a new array that only includes the elements that pass the test implemented in the function. This function **has to** return a boolean.

```js
const lowerThanFour = numbers.filter(number => {
    return number < 4;
});

console.log(lowerThanFour);
```

Useful later down the line when there are multiple objects and you need to filter them when collected in an Array of objects.

### Reducing

`Array.prototype.reduce()` executes a "reducer" callback function on each element of the array, in order, passing in the previous return value from the calculation onto the next element. The final result of running the reducer across all elements of the array is a single value.

```js
const total = numbers.reduce((reducer, number) => {
    return reducer + number;
}, 0);

console.log(total);
```

The first time that the callback is run there is no "return value of the previous calculation". Therefore we needed to define the reducer to an initial value of 0 as part of the arguments for the `.reduce()` method. If this is not initialised, the reducer will take the first value in the array, no matter what data type it is (including objects), therefore it is important to include it.

### Example with Array of Objects

```js
const colin = {
    name: "Colin",
    age: 27
}
const kevin = {
    name: "Kevin",
    age: 30
}
const zsolt = {
    name: "Zsolt",
    age: 28
}

trainers = [colin, kevin, zsolt];

initialValue = 0;

const totalAge = trainers.reduce((reducer, trainer) => {
    return reducer + trainer.age;
}, 0);

console.log(totalAge);
```

## HTML-CSS-JavaScript

**HTML is the frame and content of a house**. So things like chairs, tables, doors, stairs, the bare essentials of what constitutes a house, nothing more.

**CSS is the paint and the rounded edges** of a house that makes visually appealing and comfortable to live in. Technically, the definition of a chair is something that you sit on, but things like shape, size, and padding (design) is what makes chairs comfortable (or uncomfortable) to sit on.

**JavaScript is the electricity and water supply** that makes a modern home a modern home, and makes taking baths, cooking food, and not freezing to death during the winter possible. A JavaScript developer make sure that light switches on when you flip the switch, and hot/cold water comes out when you turn the water tap.

### UX (User Experience)

The overall experience of a person using a product such as a website or computer application. How easy or pleasing it is to use.

Important to consider all the stages,

e.g. Buying a book

- Where to buy it
- How to find it
- Comparison on prices
- How many steps to purchase
- Payment (one click buy)
- Shippings, lead times
- Delivery
- Feedback

### UX Design Cycle

- Strategy
- Discovery
- Analysis
- Design
- Product

(cycle through)

### Personas

- Similar to a profile, a character sketch
- Ideally created after research
- Gather information about your users and transforming into a set of fact-based profiles
- Able to demonstrate real needs and goals of your users
- Watch out for stereotypes - no Karens, no Chads
- Persona spectrum - design for inclusion
- This is used to extrapolate user needs

***Proto-persona***

- BIO
- DEMOGRAPHICS
- NEEDS & GOALS
- BEHAVIOURS

![persona](/images/persona.png)

### Wireframe

- A wireframe is the outline of a web page or app
- Wireframes provide an overview of layout, structure, user flow and functionality
- Can come in different fidelities (rough sketch, mid, full on detail)

### Considerations

- Consider that the app may be spread across multiple devices
- May wish to consider mobile first as it has the most limitations
- Accessibility is one other to consider (UK: understanding accessbility requirements for the public sector)
- Web Content Accessibility Guidelines (WCAG)

### Possible Workflow

- Start with list
- Pen and paper
- Digital wireframe - Figma, Sketch, Invision, Excalidraw

### Task

Task: have a go at Crazy Fours/Eights: fold a piece of paper into 4 or 8 and sketch out some possible homepage layouts for a mobile app

**Requirements**

- Logo
- Newsletter sign up
- Link to main menu
- Link to shopping cart
- Link to collections (suggestions: Kids, Women, Men, Home)

![wireframes](/images/wireframes.png)

### Semantic HTML

Hypertext Markup Language

Semantic HTML means uses that word with its proper meaning in its proper context, therefore writing HTML5 as it was mean to be.

Currently HTML5 is the used version of HTML.

**HTML Elements**

- `<ol>` - ordered list
- `<ul>` - unordered list
- `<li>` - list item inside ol or ul
- `<h1> to <h6>` - headers
- `<p>` - paragraph
- `<div>` - section (vague)
- `<img>` - image

**Why use semantic HTML?**

- HTML can take complex structure with many elements
- Especially a problem with the rise of frameworks, code can be hard to read
- Semantic HTML improves readability, therefore easier to maintain
- Also easier for screen readers to understand
- Promotoes 'clean' code

![breaking down](/images/breaking_wireframes.png)

## Duck Appreciation Example

### Useful Links

https://fonts.google.com/ - fonts to include

https://coolors.co/ - generates colors

### CSS

Referring to class, element and id

```css
/* styles.css */

.duck{ /* class */
    border-radius: 100%;
    border: 5px outset brown;
    width:100%; 
    height:90%; 
    object-fit: cover;
}

h1{ /* element */
    text-align: center;
    font-size: 50px;
    color: #F6C28B;
    background-color: #5296A5;
}

#main-nav a{ /* id with a tag */
    text-decoration: none;
}

#main-nav a:hover{ 
    color:purple;
}
```

### Aligning Items

***Flexbox***

https://flexboxfroggy.com/ - practice css

```css
.dog{
    display: flex;
    justify-content: center; /* x */
    align-items : center;  /* y */
}
```

***Grid***

https://css-tricks.com/

https://cssgridgarden.com/ - practice

```css
.products__container{
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
}
```

## Art Website Example

https://github.com/sandramtzd/artuk_website

### Useful CSS

***Setting background image***

```css
header{
    background-image: url("./assets/banner.jpg");
    background-size: cover;
    background-position-y: -500px;
    width: 100%;
    height: 400px;
}
```

***Header opacity and spacing***
```css
.header-top{
    font-family: 'Montserrat', sans-serif;
    display: flex;
    justify-content: space-between;
    align-items: center;
    background-color: #393D3F;
    opacity: 0.7;
    height: 100px;
}
```

***Scaling font size***
```css
#main-nav a{
    color: white;
    text-align: right;
    text-decoration: none;
    padding: 1em 1em;
    font-size: 1.6vw;
}
```

***Hover***
```css
#main-nav a:hover{
    background-color: #0F1108;
    text-decoration: none;
}

```

***Functions***
```html
<!-- index.html -->
 <script>
        function myFunction() {
            var element = document.body;
            element.classList.toggle("dark-mode");
        }
</script>

<li><button onclick="myFunction()">Dark Mode</button></li>
```

```css
/* styles.css */
.dark-mode {
    background-color: black;
    color: white;
}
```

## Web Content Accessibility Guidelines

https://www.gov.uk/service-manual/helping-people-to-use-your-service/understanding-wcag

## DOM - Document Object Model

***What is the DOM?***

- something created by browser when HTML document loads inside it
- aim is to interact with the HTML doc from our JavaScript code so that we can change, add or remove content

The DOM consists of -

- A node tree: a representation of all the elements that make up the current page

![node-tree](/images/node_tree.png)

- Provides up with Methods and Properties that allow us to manipulate the node-tree using JavaScript

**Window and Document**

- The `window` represents and open window in a browser
- Known as the browser's global object
- We can access the DOM via the window : `window:document`
- We have already done this through `window.console.log`

### Example

We create two files, `index.html` and `index.js`

We can start with `html:5` to insert the boilerplate code in VS.

Make sure to include `<script src="index.js" type="text/javascript" defer></script>`

*index.html*
```html
<body>

    <h1 id="main-heading">Heading</h1>
    <p class="paragraph">Lorem ipsum dolor sit amet consectetur, adipisicing elit. Laborum deserunt sint impedit hic id excepturi debitis eum alias illum qui iste veniam, iure nesciunt voluptas quo amet harum? Dolor, voluptatem?</p>
    <p class="paragraph">Lorem ipsum, dolor sit amet consectetur adipisicing elit. Quasi quaerat earum optio aperiam esse dolorum illo, repellendus sint a maiores tempora dolores id. Porro numquam cum atque velit quos ipsam.</p>
    <h2>Sub heading</h2>
    <ul class="list"></ul>

</body>
```

*index.js*
```js
const paragraph = document.querySelector(".paragraph");
console.log(paragraph);
```

We can use JavaScript to call the `query` of the DOM provided. In our case, it is the paragraph class and we call it out into the console. When inspecting the webpage through chrome, we can see the **FIRST** instance of paragraph and it prints it out to the console.

You can interact with the DOM inside the console.

![interact](/images/interact_dom.png)

### Methods on the DOM API

![dom methods](/images/dom_methods.png)

NOTE: The most popular methods are the last two.

### Altering Text

With the header, we can edit it through the innerText property of the heading. It is unwise to hard code all changes in HTML, therefore it's nice to edit it through the DOM via JavaScript.

```js
const heading = document.querySelector("#main-heading")
console.log(heading);
heading.innerText = "Cool stuff I've learned about the DOM";
```

When querying more than one section via `querySelectAll`, you have to access the return list via indexing as usual,

```js
const paragraphs = document.querySelectorAll(".paragraph");
paragraphs[0].innerText = "Lorem can go away"
paragraphs[1].innerText ... etc
```

We can chain the methods like in Java and JS,

```js
document.querySelector("h2").innerText = "Sub sub sub heading";
```

### Creating Elements

We can create an element by calling the `createElement` method and passing in the tag you want to create,

```js
const listItem1 = document.createElement("li");
listItem1.innerText = "About us";

const listItem2 = document.createElement("li");
listItem2.innerText = "Contact";

const list = document.querySelector(".list");
list.appendChild(listItem1);
list.appendChild(listItem2);

list.removeChild(list.lastChild) //removes last element of list
```

## Functionality (Events)

We have covered the different methods of altering text, changing elements, but how do we make this functionality available to people using the webpage? This could be via, scroll, mouse click, buttons, dropdown etc...

### Favicon

```html
 <link rel="icon" type="image/x-icon" href="./favicon.png">
```

### Buttons

*index.html*
```html
<button id="btn">CLICK ME</button>
```

*index.js*
```js
const button = document.querySelector("#btn");

const printButtonConfirmation = () => {
    console.log("Button Clicked");
}

button.addEventListener("click", printButtonConfirmation);
```

### Inputs

We can deal with inputs through,

*index.html*
```html
    <div id="box">
        <h2 class="caption">Hello World!</h2>
    </div>
    <input type="text" id="text-input" placeholder="Enter a message...">
```

*index.js*
```js
const box = document.querySelector("#box");
const caption = document.querySelector(".caption");
const input = document.querySelector("#text-input");

input.addEventListener("input", (event) => {
    console.log(event.target.value);
    caption.innerText = event.target.value;
});
```

The `event.data` returns the value of the single keystroke, but the `target.value` takes in the whole string of the event.

### Options

`select>option*5 + TAB`

This shortcut gives us 5 options that can be chosen.

*index.html*
```html
    <select name="color-picker" id="color-picker">
        <option value="red">Red</option>
        <option value="blue">Blue</option>
        <option value="green">Green</option>
        <option value="yellow">Yellow</option>
        <option value="hot-pink">Hot Pink</option>
    </select>
```

*index.js*
```js
const dropdown = document.querySelector("#color-picker");


dropdown.addEventListener("change", (event) =>{
    const newColor = event.target.value;
    box.setAttribute("style", `background-color: ${newColor}`);
});
```

This is more of a sledgehammer way, where the `element.style` overrides the css code when it is changed to a different background color.

### Color (to be tested)

`<input type="color">`

### History

We can store the history of the choices through,

```js
const history = document.querySelector("#history");

const createAndAppendListItem = (content) =>{
    const newListItem = document.createElement("li");
    newListItem.innerText = content;
    history.appendChild(newListItem);
}

dropdown.addEventListener("change", (event) =>{
    const newColor = event.target.value;
    box.setAttribute("style", `background-color: ${newColor}`);
    createAndAppendListItem(newColor);
});
```

## To Do List

https://github.com/Kibiko/js_events

This front end code is a to do list which incorporates the following functionality

- adding a task to the todo list
- adding a functional delete button to the task
- adding a functional checkbox to the task
- grey and crossing out a completed task
- moving a completed task to the completed list
- adding a functional delete button to the completed task

### script.js

```js
const input = document.querySelector("#new-todo");
const button = document.querySelector("#enter");
const list = document.querySelector("#list");
const dateButton = document.querySelector("#date");
const date = document.querySelector("#show-date");
const completedList = document.querySelector("#completed-list");

//shows date
const showDate = () => {
    console.log(Date());
    dateButton.innerText = Date();
}

dateButton.addEventListener("click", showDate)

//create and append list with task, delete button and checkbox
const createAndAppendListItem = () => {
    const newListItem = document.createElement("li");
    newListItem.innerText = input.value;
    const newCompletedItem = document.createElement("li");
    newCompletedItem.innerText = newListItem.innerText;

    //delete button
    const deleteButton = document.createElement("button");
    deleteButton.innerText = "Delete";
    deleteButton.addEventListener("click",() => {
        list.removeChild(newListItem);
    });
    deleteButton.className = "delete";
    newListItem.appendChild(deleteButton);

    //complete checkbox
    const completeButton = document.createElement("input");
    completeButton.type = "checkbox";
    const deleteComplete = document.createElement("button");
    completeButton.onclick = () => {
        if(completeButton.checked == true){ //moving task to completed list
            newListItem.classList.add("completedTask");
            completedList.appendChild(newCompletedItem);
            deleteComplete.addEventListener("click", () => {
                completedList.removeChild(newCompletedItem);
            })
            deleteComplete.innerText = "Delete";
            deleteComplete.className = "delete";
            newCompletedItem.appendChild(deleteComplete);
        } else {
            newListItem.classList.remove("completedTask");
            completedList.removeChild(newCompletedItem);
        }
    }
    newListItem.appendChild(completeButton);
    list.appendChild(newListItem);
}

//button click
button.addEventListener("click", createAndAppendListItem);
```

## Synchronicity

JavaScript executes code in a single thread, which means it executes one statement at a time. As expected, it executes code in order and must finish executing a piece of code before moving onto the next.

Asynchronous programming is a technique that enables your program to start a potentially long-running task and still be able to be responsive to other events while that task runs, rather than having to wait until that task has finished. Once that task has finished, your program is presented with the result.

A good example is generating prime numbers and then displaying it.

This is the basic problem with long-running synchronous functions. What we need is a way for our program to:

- Start a long-running operation by calling a function.
- Have that function start the operation and return immediately, so that our program can still be responsive to other events.
- Notify us with the result of the operation when it eventually completes.

That's precisely what asynchronous functions can do. The rest of this module explains how they are implemented in JavaScript.

### Promise

A fetch request is an asynchronous event.

*app.js*
```js
const fetchDogImage = () => {
    const request = fetch("https://dog.ceo/api/breeds/image/random");
    console.log(request);
}

fetchDogImage();
```

This event comes back as a promise. This `Promise` object is telling us that they are starting it but it might not come back. It is the eventual completion (or failure) of an asynchronous operation and its resulting value. This comes as `fufilled` or `rejected`.

![](/images/promise.png)

At the time the promise is logged out, it is still pending. But when we open up the tab it is re-evaluated and the state is fufilled by the time.

### Response

```js
const fetchDogImage = () => {
    const request = fetch("https://dog.ceo/api/breeds/image/random")
        .then(response => console.log(response)) //wait for this process to finish, then do what you need to do
    console.log("This is the last line");
}

fetchDogImage();
```

![](/images/response.png)

This instead, returns a `Response` object. Now we can see that as the request is being executed, the code moves onto the next line and returns `"This is the last line"` before the response comes back. Here we can see a good example of asynchronous coding.

### DB Serialisation

How do we convert this data to something useful?

```js
const fetchDogImage = () => {
    const request = fetch("https://dog.ceo/api/breeds/image/random")
        .then(response => response.json())
        .then(data => console.log(data))
}
```

We can convert the response to a json object and then we can see how the data is represented by logging it out. The data comes out in JSON format.

In order to use the data back into the code, we can change the `console.log(data)`, to a `querySelector`,

```js
const fetchDogImage = () => {
    const request = fetch("https://dog.ceo/api/breeds/image/random")
        .then(response => response.json())
        .then(data => document.querySelector("#dog-image").src = data.message);
};

fetchDogImage();

const randomDogButton = document.querySelector("#dog-button");

randomDogButton.addEventListener("click", fetchDogImage);
```

Now we can add functionality to the button as well to call the method.

### Async/Wait

To keep this code up to date and current trend, we need to modify the function to include the tags of `async` and `await`. This gives it a cleaner look and easier to understand and read,

```js
const fetchDogImage = async () => {
    const response = await fetch("https://dog.ceo/api/breeds/image/random");
    const jsonData = await response.json();
    document.querySelector("#dog-image").src = jsonData.message;
};
```

The `await` keyword can only be used inside an `async` function.

The `await` keyword makes the function pause the execution and wait for a resolved promise before it continues.

When dealing with multiple `messages` which contain the url of multiple images, we will have to loop through the jsonData by using the `forEach()` mapping method,

```js
const fetchDogImage = async () => {
    const response = await fetch("https://dog.ceo/api/breed/germanshepherd/images");
    const jsonData = await response.json();
   
    const imageContainer = document.createElement("div");
    
    jsonData.message.forEach(url => {
        const dogImage = document.createElement("img");
        dogImage.src = url;
        imageContainer.appendChild(dogImage);
    });

    document.querySelector("body").appendChild(imageContainer);
};
```

## Handling Objects in JSON Data

Pagination is creating extra keys in the json object to present small bits of the large data to the front end. This can include a link to previous page and next page. In the below, they show only 50 characters on a page and then provide links to the next pages with the next 50.

![](/images/pagination.png)

A useful method for all this is `Promise.all()`. We are able to create multiple fetch requests in this method and wait for all of these methods to resolve before we `callback` to do things with the data.

Steps:

- Generate a for loop that creates different fetch requests
- Collect them into an array
- Promise all of the requests in the array
- Then callback and do something

```js
// Create multiple fetch requests with similar URLs
// only difference between urls is a page number
// use promise.all magic

const allPromises = [];

for(let i = 1; i < 26; i++){
    allPromises.push(
        fetch(`https://api.disneyapi.dev/character?page=${i}&pageSize=300`)
        .then((response) => response.json())
    )
}

Promise.all(allPromises) //wait til all promises are fulfilled and all the data comes back 
.then((allResults) =>{
    console.log(allResults);
})
```

The full functionality of the `promise.all()` is below where we append it to a list on our html,

```js
Promise.all(allPromises) //wait til all promises are fulfilled and all the data comes back 
.then((allResults) =>{
    // console.log(allResults);
    //allResults = [{[]}, {[]}] is an array of objects of arrays
    const allCharacters = allResults.map((result) => result.data).flat() //map through objects and only give back the data key
    // if arrays have arrays in them, it will unpack the arrays inside
    console.log(allCharacters);

    const characterList = document.querySelector("ul");

    allCharacters.forEach((character) =>{
        const characterLi = document.createElement("li");

        const characterAnchor = document.createElement("a");  //anchors for links
        characterAnchor.textContent = character.name;
        characterAnchor.href = character.sourceUrl;

        characterLi.appendChild(characterAnchor);

        characterList.appendChild(characterLi);
    })
});
```

## REACT

### Destructuring

We can destructure code by assigning variables through a different syntax. This is useful because we can pick multiple things out easily from arrays or objects,

```js
const numbers = [10, 20, 30, 40];

// WITHOUT destructuring

const ten = numbers[0];
const twenty = numbers[1];

console.log(ten);
console.log(twenty);

// WITH destructuring

const [ten, twenty, ...rest] = numbers;

console.log(ten); //10
console.log(twenty); //20
console.log(rest); //[30, 40]
```

In terms of objects,

```js
//example 2

const person = {
    name: "Sally",
    age: 25
}

// WITHOUT destructuring

const name = person.name;
const age = person.age;

// WITH destructuring

const { name, age } = person;

console.log(name); //"Sally"
console.log(age); //25
```

***This is very common in REACT!***

### Intro 

Vanilla JS can get really messy therefore we have frameworks to help make it cleaner, easier to read, maintain and solve for bugs.

Frameworks streamline the process of building a web app and often integrate HTML and JS code closer than would be possible otherwise.

**What is REACT?**

- Library written in JavaScript but acts like a framework
- Makes it easy to develop user interfaces
- Think of it as the 'view layer' in our application
- Open source!

**Why REACT?**

- https://stateofjs.com/en-US (ranking all the frameworks)
- Loads of frameworks to choose from: Vue, Angular...
- React is a very strong contender since 2013 release and backed by Meta

**Benefits**

- Component based UI - breaking down our UI into smaller parts called components
    - Each part is looking after one thing
    - JSX syntax
    - Looks more like HTML

```js
import logo from './logo.svg';
import './App.css';

function App() {
  return (
    <div className="App">
      <header className="App-header">
        <img src={logo} className="App-logo" alt="logo" />
        <p>
          Edit <code>src/App.js</code> and save to reload.
        </p>
        <a
          className="App-link"
          href="https://reactjs.org"
          target="_blank"
          rel="noopener noreferrer"
        >
          Learn React
        </a>
      </header>
    </div>
  );
}

export default App;
```

Above we see it's a JavaScript file however it contains HTML looking code. What REACT allows us to do is mix the two and type in JSXML. Under the hood, every tag we add essentially is a `createElement()` method.

* One way data flow
    * Set up is hierarchical
    * Parent component is responsible for tracking all the application's data
    * This is known as **state**
    * Responsible for sending data to 'children' components
    * Data sits 'high' in a REACT Application

![state](/images/state.png)

- Virtual DOM
    - Updating the browser using JS is expensive
    - Keeps a virtual version of the DOM in memory and only updates the real DOM where necessary
    - When we make a change it updates the virtual DOM and compares it to the real DOM
    - Doesn't have to burn the DOM and make a new one

![virtual dom](/images/virtual_dom.png)

* Single Page Applications (SPAs)
    * SPA is when server only sends one HTML page...
    * 

### Getting Started

- `npm install react` to install the library
- `npx create-react-app my-app-name` to create the app and gives us boilerplate code

### Starting the app

- `npm start`

Now we can type in JS and HTML into the same file!

```js
import './App.css';

function App() {
  //java script goes here

  return ( //html goes in here
    <div className='blue'>
      <h1>Hello World!</h1> 
        <p>Welcome to this amazing React app where you can write JSXML!</p>
    </div>
    );
}

export default App;
```

the `return` can only be one `parent`. Therefore, we have to enclose everything into one `<div>` or `fragment` tag. If there are further divisions in the HTML part, `fragments` should be added which are essentially empty tags, `<> , </>`.

One thing to note is that to define a class, we need `className` since JS has class inherently.

### Mixing Both Sections

As both HTML and JS sections are separated, we are actually able to code JS into the HTML section. This is through the `{ }` braces in the HTML side and ...

```js
import './App.css';

function App() {
  //java script goes here

  let counter = 0;

  const incrementCounter = () => {
    counter++;
  }

  return ( //html goes in here
    <div className='blue'>
      <h1>Hello World!</h1> 
      <hr></hr>
      <p>The current value of the counter is {counter}</p> {/* The curly braces makes it able to access the JS part*/}
      <button onClick={incrementCounter}>Increment Counter</button>
    </div>
    );
}

export default App;
```

### State Saving

https://www.freecodecamp.org/news/usestate-hook-3-different-examples/

When adding a button into the code, we see that the state does not get updated when the button is clicked. In order to tell REACT to watch this state and update it whenever we click the increment button,

```js
import { userState } from `react`; //hook
//other imports

function App() {
  //java script goes here

    let [counter, setCounter] = useState(0); //updated to denote this variable as a state
    //rest of JS part

    const incrementCounter = () => {
    setCounter(counter+=1); //this has to be modified as well, we have to use the method set

    return ( 
        // html code
    )
}
```

Note that the second part of the variable 'array' is almost always `set{firstPart}`. This lets us set the hook name to which we can update the counter with whatever new variable or method we wish to use.

A `hook` allows us to “hook into” React state and lifecycle features from function components.

### Components

These are essentially reusable methods and functions that we can use in the REACT code. Whenever we need to repeat functionality in the code we can create a component and call it in the REACT code.

![](/images/wireframe_react.png)

In the above wireframe we see repeating buttons and layout. We need to draw a `component diagram` to figure out how to the data flows. Since REACT will only allow data to flow from parent to child, **never** child to parent or child to child, planning is essential.

Number of components do not matter in a diagram, it indicates the flow of data. `Containers` should be the place where the state is kept and where the heavy lifting should be. `Components` should not be doing anything complex and should only function to do simple things.

![](/images/components_diagram.png)

In terms of code, 

### Inspecting Componenets

![](/images/components_direction.png)

![](/images/components_list.png)

## Bakery - Cake Example

https://github.com/Kibiko/react_bakery

### Useful Parts

*CakeDisplay.js*
```js
const CakeDisplay = ({cake}) => {

    const displayIngredients = cake.ingredients.map((ingredient) =>{  //maps through and returns list items in an array
        return <li>{ingredient}</li>
    });

    return(
        <>
            <h2>{cake.cakeName}</h2>
            <h3>Ingredients:</h3>
                <ul>{displayIngredients}</ul> {/* fills the ul with array of li */}
            <p><b>Price:</b> £{cake.price}</p>
            <p><b>Rating:</b> {cake.rating}/5</p>
        </>
    )

}

export default CakeDisplay;
```

## CI/CD

### Continuous Integration

- CI runs a **script** builds our app and runs the **entire test suite**
- This means that if you are only working on the front end, you want to make sure that it does not break the back end
- This also gives insight into if the backend code breaks your front end when merging
- **CI pipelines** can catch bugs early and promotes gradual increments
- It can guarantee that once code is pushed to production, it will not break other parts
- **Cons:** requires additional resources (inhouse or outhouse), team testing culture must be solid and robust
- **Tools:** Jenkins, CircleCI, CodeShip, GitHub Actions

### Continuous Deployment

- CD is the **automation of both delivery and integration**
- Enables teams to **continuously deliver features** rather than wait for release cycles
- **Relies** on existing CI pipeline
- Once running it speeds up delivery of features considerably
- If it's robust, it is much safer and can release new features seamlessly
- It relies on the CI pipeline to catch errors - any shortcomings could cause app breaking bugs to slip through
- **High initial cost**
- Tools are similar to CI 
- Way it works is that new deployment would take on the new traffic whereas old deployment would handle the existing traffic it had

## Errors and Exception

`try` is saying test this block of code. We can throw a custom error in the block which essentially just creates it.

`catch` is saying if the try block fails, what we should do next.

```js
const fetchCountryList = async () =>{
    try{
        const response = await fetch("https://restcountries.com/v3.1/all");
        if(!response.ok){
            throw new Error(`Fetch request failed with status code: ${response.status}`)
        }
        const jsonData = await response.json();
        return jsonData;
    } catch (error){
        body.textContent = 'Error! ' + error.message;
        console.log(error); //logs the error
        alert(error); //creates a popup error
    }
}
```

## Bakery - Extended Example

Here we make the cake list more dynamic and the ability to add cakes to the existing array of cakes.

https://github.com/Kibiko/react_bakery_dynamic

![](/images/bakery_component_diagram_extended.png)

## UseEffect - Colour Picker

![](/images/colour_diagram.png)

![](/images/colour_component_diagram.png)

### Sliders

*ColourPickerContainer.js*
```js
import { useState } from "react";
import Slider from "../components/Slider";

const ColourPickerContainer = () => { 

    const [red, setRed] = useState(parseInt(50));
    const [green, setGreen] = useState(parseInt(50));
    const [blue, setBlue] = useState(parseInt(50));
    const [rgbValue, setRgbValue] = useState("");

    return(
        <>
            <Slider colour="Red" value={red} onValueChange={setRed}/>
            <Slider colour="Green" value={green} onValueChange={setGreen}/>
            <Slider colour="Blue" value={blue} onValueChange={setBlue}/>
        </>
    )

}

export default ColourPickerContainer;
```

*Slider.js*
```js
const Slider = ({colour, value, onValueChange}) => {

    const handleValueChange = (e) => {
        onValueChange(parseInt(e.target.value));
    }

    return(
        <>
            <label htmlFor={colour}>{colour}</label>
            <input
                type="range"
                id={colour}
                value={value}
                onChange={handleValueChange}
            />
            <p>{colour}: {value}</p>
        </>
    )
}

export default Slider;
```

### Implementing UseEffect

In the colour picker example,

*ColourPickerContainer.js*
```js
// rest of code

    useEffect(() => {
        const red255 = Math.ceil(red*2.55);
        const green255 = Math.ceil(green*2.55);
        const blue255 = Math.ceil(blue*2.55);
        setRgbValue(`rgb(${red255}, ${green255}, ${blue255})`)
    }, [red, green, blue]) //only things in array will trigger useEffect function when it changes. THIS IS IMPORTANT

// rest of code
```

## Data Loading and UseEffect

In this example, we load data from a film API of Aardman animations.

`FilmContainer.js` -> `FilmList.js` -> `Film.js`

`1. calls FilmList` -> `2. maps through films and returns film li items` -> `3. how to display film`

When using the useEffect, the dependency array is very important because we want to mount the component but not fire a fetch every time that our data is loading in.

*FilmContainer.js*
```js
import { useState, useEffect } from "react";
import FilmList from "../components/FilmList";

const FilmContainer = () => {

    const [films, setFilms] = useState(null);

    const loadData = async () => {
        const response = await fetch("https://raw.githubusercontent.com/annahndr/annahndr.github.io/master/aardman_data/aardman.json");
        const jsonData = await response.json();
        setFilms(jsonData);
    }

    useEffect(() => {
        loadData();
    },[]); // <------- empty dependency array

    return(
        <>
            <h1>Aardman Animations</h1>
            { films ? <FilmList films={films}/> : <p>loading...</p> }
        
        </>
    )
};

export default FilmContainer;
```

The empty dependency array makes sure that no other change will trigger it apart from the first `loadData()` method in the `useEffect` function.

An issue with this is that the data is mapped before we do the API call after mounting the UseEffect. This comes in the form of a `mapping` error. In order to fix this, we can call a rendering at a certain point. We add the ternary operator to make sure it is not rendered until the `films` is not null.

Another way around this would be to set the `useState` of the `films` to be an empty array so that there is something to `map` over even before the data is loaded into the films.

We can filter the data as well for `truthy` values via,

*Film.js*
```js
const Film = ({film}) => {

    const castMembers = film.roles.filter((roles) => roles.voice) //filters the truthy roles.voice
    .map((role) => { //then maps
        return <li key={role.id}>{role.voice}</li>
    });

    return(
        <>
            <h2>{film.title}</h2>
            <p>Released: {film.released}</p>
            <p>About: {film.about}</p>
            <ul>{castMembers}</ul>
        </>
    )

};

export default Film;
```

where not all the voices have a String, therefore we only take parts that have been filled out with a String (truthy).

Below is the code for the intermediary `FilmList.js`,

```js
import Film from "./Film";

const FilmList = ({films}) => {

    const mappedFilms = films.map( (film) => {
        return <Film film={film} key={film.id}/>
    })

    return(
        <>
            {mappedFilms}
        </>
    )

};

export default FilmList; 
```

## Linking Front End to Back End

### Issues

(BackEnd)

CORS - Cross Origin Resource Sharing

- we need to add a CORS configuration to allow a fetch to your localhost database
- this occurs when one of the port domains running is trying to send requests to another port on your machine
- this is implemented as a security since hackers would be able to send scripts from one port to another

***Solution:***

- Create a new configurations package at the same level as others
- Create a file SpringGlobalConfig.java
- 

```java
package com.bnta.chocolate.configurations;

import org.springframework.context.annotation.Configuration;
import org.springframework.web.servlet.config.annotation.CorsRegistry;
import org.springframework.web.servlet.config.annotation.WebMvcConfigurer;

@Configuration
public class SpringGlobalConfig implements WebMvcConfigurer {

    public void addCorsMappings(CorsRegistry registry){
        registry.addMapping("/**") //any path pattern
                .allowedOrigins("*") //allow everything - this could be set up to only allow certain IP addresses
                .allowedHeaders("*") //headers would be things like application json headers, token authentication headers etc...
                .allowedMethods("*"); //what kind of requests are allowed - GET, PUT, PATCH
    }
}
```

## React - Final Tips

### Front End Project

https://github.com/darkpoetOX/Restaurant_frontend

## Retrospective

These are used to reflect on the past project or sprint. Agile methodology has a planning, stand up everyday, execution of plan and retrospective. This is used not for singleing out people or venting but instead should be used to clearly go through the points that the team experienced and improvements for next project/sprint.

*Useful website:* https://metroretro.io/

- Good

- Bad

- Start

- Stop

- Actions - assign someone to do something

![](/images/retrospective.png)

<hr>

[Back to Top](#frontend-cheatsheet)
