---
layout: post
title:  Javascript Thinkful prep course note
date:   2019-01-19 16:40
categories: Thinkful
tags: javascript
---
* content
{: toc}


## Facts

[CanIUse](https://caniuse.com/#home)
can help you understand which browsers support the feature.


To get JavaScript into a web page, there are two main options.

let and var declare a variable; const declares a constant. A constant cannot be reassigned to a new value.





```html
<!DOCTYPE html>
<html lang="en">
    <body>
        <script>src = "app.js"</script>
    </body>
</html>
```


*With jquery*

```javascript
<script src="https://www.somewhere-on-the-internet.com/coolLibrary.js"></script>
```




*Transpiling* is when you use a program to rewrite ES6 code as ES5 so it can run in all browsers.

But unless you have a specific reason not to use `const` or `let`, you should abandon `var` entirely.

`const` is used to define constant values, which is another way of saying variables whose value cannot be reassigned.

`let` and `var` differ in terms of their scope.



```
'use strict';

foo = 'bar'; // => Raises reference error
```

### coercion
variables are converted from one type to another in JavaScript

`typeof` check datatype

`null` is distinct datatype, but if use `typeof null` it returns "object"

`undefined`, do not use it as value to a variable. use  `null` instead.

"objects" is considered as complex data type

```
const person = {
  name: 'Jane Doe',
  greet: function() {
    console.log('Hello world');
  }
};

console.log(person.name); // => Jane Doe
person.greet(); // => Hello world
```

The example above demonstrates that if you combine a number with a string using the + operator, the resulting value will be a string.


```
<script src="https://code.jquery.com/jquery-3.1.0.js"></script>
 <script src="index.js"></script>
```

## Function
`alert`

an argument is a value that gets passed to the function when it's called. A parameter is the variable that holds the place of an argument when the function is defined.

 call signature ()

Note that functions that do not set an explicit return value via return still return something, namely, undefined

hoisting

Default function parameters

ES6 has default parameters

```
function Myfunction(para){
    //something
}

const Myfunction = function(para)
{
    //something
}

const Myfunction = (para) => //something

```
When defining an arrow function that takes a single parameter, the parentheses are optional:


### Immediately invoking a function expression-IIFE

Notice the `()`, without it, the IIFE will throw an error.

```
(function () { return 'abc' }())
'abc'
```

### Closure 

to reference a specific instance of a local binding in an enclosing scope—is called closure.

```javascript
//A function is defined, it creates a local binding, and //return a function that accesses and returns the local // binding. 
function wrapValue(n){
  let local = n;
  return ()=> local;
}
let wrap1 = wrapValue(1);
let wrap2 = wrapValue(2);
console.log(wrap1());
console.log(wrap2());

```
more creative example

```javascript
function multiplier(factor){
  return number => number*factor;
}
console.log(multiplier(5));

```

### recursion 

e.g factorial function 
```javascript
function factorial(n){
  if(n===1){
    return 1;
  } else{
    return n*factorial(n-1);
  }
}

console.log(factorial(4));
```
decide if a number is even or not. 

```javascript
function isEven(n) {
  if (n == 0) return true;
  else if (n == 1) return false;
  else if (n < 0) return isEven(-n);
  else return isEven(n - 2);
}
```



## template strings



```
const foo = "foo";
function sayHello(){
    return 'hello ';
}

const myString = `foo is set to ${foo}. Let's say hello:${sayHello}`

```



## string method
```
const fooBar = 'foo bar foo bar';
fooBar.length; // => 15
fooBar.charAt(0); // => "f"
fooBar.slice(4); // => "bar foo bar"
fooBar.slice(4, 7); // => "bar"
fooBar.split(" "); // => ["foo", "bar", "foo", "bar"]
fooBar.toUpperCase(); // => "FOO BAR FOO BAR"
fooBar.replace('foo', 'bar'); // => 'bar bar foo bar'
```
Inside a template string, you can refer to variables or execute code by using ${}

counter ++

```
let i = 0;
let j = 0;

// postfix operator
let x = i++;

// prefix operator
let y = ++j;

console.log(x); // 0
console.log(i); // 1

console.log(y); // 1
console.log(j); // 1
```
n the case of the prefix operator, it increments before it returns the value.
In the case of the postfix operator, it increments after it returns the value.






## Making logical assertions

False
```
console.log(Boolean(false));
console.log(Boolean(""));
console.log(Boolean(0));
console.log(Boolean(null));
console.log(Boolean(undefined));
console.log(Boolean(NaN));
```
True
```
console.log(Boolean({}));
console.log(Boolean([]));
console.log(Boolean(-1));
```

## Control flow and conditionals
```
function analyzeNumber(num) {
  if (typeof num !== 'number') {
    console.log('not a number');
  }
  else if (num % 2 === 0) {
    console.log('even number');
  }
  else {
    console.log('odd number');
  }
}
```
### Ternary operator
```
function getFee(isMember) {
  return (isMember ? "$2.00" : "$10.00");
}

console.log(getFee(true));
// expected output: "$2.00"
```
### Error handling

`try`, `catch`, `finally`

```
try{
nonExistenceVar +='foo';

}

catch (e){
    console.log("something went wrong");
    console.dir(e);
}

finally {
    console.log('This happens in both success and failure case!')
}

```

The browser will run the catch block and then continue running the next line of code. This is in contrast to an uncaught error, which bubbles up and stops code execution.

`throw`
intentionally throw an error.




```
try {
  throw 'myException';
}
catch (e) {
  // do something
}

```

### Switch
`switch`

```
var fruittype = "Oranges";

switch (fruittype) {
  case 'Oranges':
    console.log('Oranges are $0.59 a pound.');
    break;
  case 'Apples':
    console.log('Apples are $0.32 a pound.');
    break;
  case 'Bananas':
    console.log('Bananas are $0.48 a pound.');
    break;
  case 'Cherries':
    console.log('Cherries are $3.00 a pound.');
    break;
  case 'Mangoes':
    console.log('Mangoes are $0.56 a pound.');
    break;
  case 'Papayas':
    console.log('Mangoes and papayas are $2.79 a pound.');
    break;
  default:
   console.log('Sorry, we are out of ' + fruittype + '.');
}

```

`prompt("Enter passcode");`

`Number.isNaN`

## Loops

```
let yourName;
do {
  yourName = prompt("Who are you?");
} while (!yourName);
console.log(yourName);
```

## Array

const allTheThings = ['cats', 'dogs', 42, ['foo', 'bar'], true, function() { console.log('hello')}];
console.log(`The first thing is ${allTheThings[0]}`);

To add an item to the end of an array, use the built-in `.push` method:

```
const myArray = [1,2,3];
myArray.push(4);
console.log(myArray);

```

### Array methods

[list of array methods](https://repl.it/@JizongL/RuralMatureFilesize) repl exercise.

```
.pop()
.shift()
.find()
.reduce()
.filter()
.map()
.sort()
.indexOf()
.lastIndexOf()
.concat()
```


Use `.slice()` to remove an item from array

```javascript
function remove(array,index){
  return array.slice(0,index).concat(index+1)
}
console.log(remove(["a", "b", "c", "d", "e"], 2));
// → ["a", "b", "d", "e"]
```

## Rest Parameters
Notice that the parameter of the funciton is not an array, but just numbers. 
```javascript
function max(...numbers) {
  let result = -Infinity;
  for (let number of numbers) {
    if (number > result) result = number;
  }
  return result;
}
console.log(max(4, 1, 9, -2));
// → 9
```

spread an array into another array 

```javascript
arrayOne = [2,3];
arrayTwo = [1,...arrayOne,4,5]

console.log(arrayTwo)
```

### Math object

`.Math.abs()`
`.Math.ceil()`
`.Math.floor()`
`.Math.round()`



#### work with comparing function

```
const myArray = [200, 20, 2, 100, 1, 10];

console.log(myArray); // => [200, 20, 2, 100, 1, 10]

function sortNumbers(a, b) {
  return a - b;
}

myArray.sort(sortNumbers);
console.log(myArray)
```

#### work with Anonymous function
```
const myArray=[200,20,2,100,1,10];
myArray.sort(function(a,b){
    return a-b
    })
console.log(myArray)
```

#### use arrow function with sort()

```
myArray.sort((a,b) => a -b);
console.log(myArray)

```


## Loops

```
for (i=1;i<=countTo;i++){
    console.log(i)
}

```
### For Loop

*note*:you can decrement (i--) or increment by, say, 2 (i+=2).

### While loop

```
let counter = 1;
const countTo = 10;
while (counter <= countTo){
    console.log(counter);
    counter++;
}

```

```
while(true){
    if (someCondition){
        break;
    }
}
```

## Scope

Global VS Block

scope chain



check out [Scope Write up Challenge](https://github.com/JizongL/Thinkful2019BootCamp/blob/master/CSS_Precourse_2019/javascript_jquery/scope/challenge.md)


* scope chain

* determinate and indeterminate functions

* global scope should be avoided.

* pure function => determinate and no side effect.

### Use let, const, and strict mode
always use let or const inside local block to define variable.

'use strict', it will throw an error when `let` or `const` is not used.

it's best practice to default to putting 'use strict'; at the top of all your JavaScript files.


## Object

 object literal.

Key does not use quotation mark.
```
const ledZeppelin = {
  singer: 'Robert Plant',
  guitar: 'Jimmy Page',
  bass: 'John Paul Jones',
  drums: 'John Bonham'
}

```

Key uses quotation marks, to include a space in between.
```
const ledZeppelin2 = {
  'lead singer': 'Robert Plant',
  'lead guitar': 'Jimmy Page',
}
```

When an object has a value that is a function, it is called [method](https://repl.it/@JizongL/Object-basics-example)

### add, delete and update values.

```
const foo = {
    bar: 'bizz';
}

//add
foo.mar = 'dizz';

//update
foo.bar = 'cizz';

delete foo.bar;


```

### Self-reference and `this`

```javascript
const myFamily = {
    lastName:"John";
    sayHi:function(){
        console.log(`Hello from the ${this.lastName}s`);
        // console.log(`Hello from the ${myFamily.lastName}s`);
    }
}

myFamily.sayHi();

```

`Object.assign`
`Object.keys`

```javascript
let journal = [];

function addEntry(events, squirrel) {
  journal.push({events, squirrel});
}

addEntry(["work", "touched tree", "pizza", "running",
          "television"], false);
addEntry(["work", "ice cream", "cauliflower", "lasagna",
          "touched tree", "brushed teeth"], false);



console.log(Object.keys(journal))
// return [0,1] 
```

## Factory functions
In this example, mammal is a factory function. The job of a factory function is to create an individual instance of some model.

```javascript
function mammal(name,numEyes){
    return {
        name:name;
        isWarmblooded:true;
        numEyes:numEyes;
        evolve:function(){
            console.log("I'm not mutating, I'm evolving");
            this.numEyes++;
        }
    explainYourSelf:function({
        console.log(
            `I'm just a ${this.name} with ${this.numEyes} eye(s). Nothing to see here`
        );
    }),    
};
}

const tiger = mammal('tiger',2);
tiger.explainYourSelf();
tiger.evolve();
tiger.explainYourSelf();

const oneEyedBadger = mammal('badger',1);
oneEyedBadger.explainYourSelf();
```



In this challenge, you'll practice [grokking](https://en.wikipedia.org/wiki/Grok) (that is, understanding) code written by someone other than yourself.




## Question to ask


* Ask how the mechanism of the .sort() and function.

```

myArray.sort((a,b)=> a-b);


function greatestToLeast(array) {
  // your code goes here
  return array.sort((a,b)=>b-a);
}
```
for the drilling, I was able to figure out if I change it from `a-b` to `b-a`, then it becomes from greatest to least.


* discuss array methods with mentor.


* If you use myVar = <...>, there will be no side effects; if you use myVar.someAttribute = <...>, there will be side effects. from Object lesson 3.




## seminar

object
```
let pet_info = {
  "name":"Addie",
  "weight": 6,
  "happiness": 0,
}

console.log(pet_info['name'])
```
change value
```
pet_info['name']="David"
```

...
&hellip;



## download and links

[mozilla javascript docs](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures)
[loop and iteration](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Loops_and_iteration)
[How to read other People's code](https://designbygravity.wordpress.com/2009/10/23/how-to-read-other-peoples-code-and-why/)






<link src="mailto:rsmith@thinkful.com">



## quiz

* Working with objects

* Using factory functions to create instances of a model object

* Explaining the difference between an object method and object property

* Explaining why you need to be careful when passing objects as an argument to a function

* Using the this keyword in object literals to achieve self-referentiality in your code
