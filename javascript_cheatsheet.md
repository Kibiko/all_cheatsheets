# JavaScript Cheatsheet

# Table of Contents

- [FrontEnd Coding -](#)
    * Week 7 -
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