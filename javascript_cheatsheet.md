# JavaScript Cheatsheet

# Table of Contents

- [FrontEnd Coding -](#)
    * Week 8 -
        * [Introduction](#introduction)
            - [JavaScript vs Java](#javascript-vs-java)
        * [Node.js](#nodejs)
        * [JavaScript Shortcuts](#javascript-shortcuts)
        * [Basics](#javascript-basics)
            - [Formatting](#formatting)
            - [Conditionals](#conditionals)
                * [Type Coercion](#type-coercion)
            - [Arrays](#arrays)
            - [Objects](#objects)
            - [Loops](#loops)
        * [Scope](#scope)
        * [Functions](#functions)
        * [Package Management Tool](#package-management-tool)
        * [Testing](#testing)
            - [Importing and Exporting](#importing-and-exporting-functions)
            - [Test Coverage](#test-coverage)
        

## Introduction

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


