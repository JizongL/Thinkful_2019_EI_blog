---
layout: post
title:  Free Code Camp Note
date:   2019-01-31 16:40
categories: FreeCodeCamp
tags: javascript
---

* content
{: toc}

# HTML5

`target="_blank"` linked docment opened in a new window tab.

`<hr>` horizontal line.

`line-height`

`z-index` move it higher in the stack than those with lower values.



# CSS

### Specify how font should degrade
set up two fonts, when the first one is not available, the second will replace it.

id has more importance compared to class.

*style tag on html*
The browser reads from top to bottom, so if the CSS is on the html page inside the `<style></style>`,
then the later one is used.
inline style overrides `<style>` tag.
`!important` overrides everything if added;

### color
`rgb(0, 0, 0)`

### Fallback value to a CSS Variable
`background: var(--pengiun-skin,black);`

[penguin css](https://learn.freecodecamp.org/responsive-web-design/basic-css/use-a-media-query-to-change-a-variable)


*Create nice shadow edge*

use `box-shadow`
The `box-shadow` property takes values for `offset-x` (how far to push the shadow horizontally from the element), `offset-y` (how far to push the shadow vertically from the element), `blur-radius`, `spread-radius` and a color value, in that order. The `blur-radius` and `spread-radius` values are optional.


```
#thumbnail{
  box-shadow: 0 10px 20px rgba(0,0,0,0.19), 0 6px 6px rgba(0,0,0,0.23);
}
```

# Javascript
`.hasOwnProperty()`


We have an array of objects representing different people in our contacts lists.

A lookUpProfile function that takes name and a property (prop) as arguments has been pre-written for you.

The function should check if name is an actual contact's firstName and the given property (prop) is a property of that contact.

If both are true, then return the "value" of that property.

If name does not correspond to any contacts then return "No such contact"

If prop does not correspond to any valid properties of a contact found to match name then return "No such property"

```
//Setup
var contacts = [
    {
        "firstName": "Akira",
        "lastName": "Laine",
        "number": "0543236543",
        "likes": ["Pizza", "Coding", "Brownie Points"]
    },
    {
        "firstName": "Harry",
        "lastName": "Potter",
        "number": "0994372684",
        "likes": ["Hogwarts", "Magic", "Hagrid"]
    },
    {
        "firstName": "Sherlock",
        "lastName": "Holmes",
        "number": "0487345643",
        "likes": ["Intriguing Cases", "Violin"]
    },
    {
        "firstName": "Kristian",
        "lastName": "Vos",
        "number": "unknown",
        "likes": ["JavaScript", "Gaming", "Foxes"]
    }
];


function lookUpProfile(name, prop){
// Only change code below this line
    for(var i=0;i<contacts.length;i++){
        if(contacts[i]["firstName"]===name){
            if(contacts[i][prop]){
                return contacts[i][prop];
            }else{
                return "No such property";
            }
        }
    }
// Only change code above this line
    return "No such contact";
}

// Change these values to test your function
lookUpProfile("Akira", "likes");

```


The following create random number between 0 and 9.
Math.floor() rounds number up.
Math.random() creates random float between 0 and 1.
so Math.random() would produce a range of [0,10),when multiplied by 10, it will generate
the digit between 0 to 10.
```
var randomNumberBetween0and19 = Math.floor(Math.random() * 20);

function randomWholeNum() {

  // Only change code below this line.

  return Math.floor(Math.random()*10);

}

```


## Range number within a range.

Create a random number within a range, inclusively.

```
function randomNumberInRange(max,min){
    return mathFloor(math.random()*(max-min))+min;
}
```

## Parse Integer

`parseInt(str, base)`


## Ternary operator

```
function checkSign(num) {
    return num === 0 ? "zero":(num>0)?"positive":"negative";
}

checkSign(10);
```

## Array
1d and multi d array

`unshift()`

`push()`
`pop()`
`shift()`
`splice(index,howManyElements,replacement)`
`slice(starts,ends)`

## Spread operator

```
let thisArray = [true, true, undefined, false, null];
let thatArray = [...thisArray];
// thatArray equals [true, true, undefined, false, null]
// thisArray remains unchanged, and is identical to thatArray
```

### indexOf
if the element exists inside an array, indexOf() will return an index number. but
if the element does not exist, then it would return a negative number.

```
function quickCheck(arr, elem) {
  // change code below this line
  return arr.indexOf(elem)>0;
  // change code above this line
}

// change code here to test different cases:
console.log(quickCheck(['squash', 'onions', 'shallots'], 'mushrooms'));
```

### for loop


```
function filteredArray(arr, elem) {
  let newArr = [];
  for(var i = 0;i < arr.length;i++){
    // if elem is not found in the current nested array, push it to the new array.
    if(!arr[i].find(element=>element===elem)){
      newArr.push(arr[i]);
    }

  }
  // change code above this line
  return newArr;
}

// change code here to test different cases:
console.log(filteredArray([[3, 2, 3], [1, 6, 3], [3, 13, 26], [19, 3, 9]], 3));
```
### hasOwnProperty()

`hasOwnProperty()`

`element in array`

```
let users = {
  Alan: {
    age: 27,
    online: true
  },
  Jeff: {
    age: 32,
    online: true
  },
  Sarah: {
    age: 48,
    online: true
  },
  Ryan: {
    age: 19,
    online: true
  }
};

function isEveryoneHere(obj) {
  // change code below this line
  return ("Alan", "Jeff", "Sarah","Ryan") in users;
  // change code above this line
}

console.log(isEveryoneHere(users));
```



### Iterate through keys of an object.
Use for loop or use ` Object.keys()`
```
for (let user in users) {
  console.log(user);
};

// logs:
Alan
Jeff
Sarah
Ryan

```

### reverse a string

use `split` and `join` to achieve this function.

```
function reverseString(str) {
  let wordList=[];
  for(let i = str.length-1;i>-1;i--){
	  wordList.push( str.split('')[i]);
  };
  return wordList.join('');
}
```

### Factorize a Number
```
function factorialize(num) {
  if(num===0){
    return 1;
  }
  for (let i=num;i>1;i--){
    num*=(i-1);

  }
  return num;
}

factorialize(5);
```

### returning longest word length.
```
function findLongestWordLength(str) {
  let wordList = str.split(' ');
  let length = 0;
  for(let i=0;i<wordList.length;i++){
	  if(wordList[i].length>length){
	  length = wordList[i].length;
	  };
  }


  return length;
}

findLongestWordLength("The quick brown fox jumped over the lazy dog");

```


### Return Largest Numbers in Arrays

```
function largestOfFour(arr) {
  // declare variable
	let largestArr = [];
    // loop through each element in arr.
	arr.forEach(
		array =>{
			//let num equals to the first number in the current list.
			let num = array[0];
            // for loop through the current array.
			for(let i=0;i<array.length;i++){
                // if any number in the list is bigger than num, then assign that
                // number to variable num, until the largest number is assigned.  
                if(array[i]>num){
					num=array[i];
				};
			}
			largestArr.push(num);
		}
	)


  return largestArr;
}
largestOfFour([[4, 5, 1, 3], [13, 27, 18, 26], [32, 35, 37, 39], [1000, 1001, 857, 1]]);
```


`.endsWith()`


### Confirm the ending

```
function confirmEnding(str, target) {
  // "Never give up and good luck will find you."
  // -- Falcor
  return str.slice(str.length - target.length) === target;

}

confirmEnding("Bastian", "n");
```
### Repeat a String Repeat a String

```
function repeatStringNumTimes(str, num) {
  // repeat after me
  let str_copy = str;
  if(num < 0){
    return "";
  }
  for(let i =0;i<num-1;i++){
    str+=str_copy;

  }
  return str;


}

repeatStringNumTimes("abc", 3);
```

### Finders Keepers

```
function findElement(arr, func){
  return arr.find(element => func(element));  
}

findElement([1, 2, 3, 4], num => num % 2 === 0);
```


### Title case a sentence

```
function titleCase(str) {
	str=str.toLowerCase();
	console.log(str.split(" "));
	const str1=str.split(" ").map(
		element => element[0].toUpperCase()+element.slice(1)
	);

  return str1.join(" ");

}


titleCase("I'm a little tea pot");
```

### Slice and Splice

```
function frankenSplice(arr1, arr2, n) {
  // It's alive. It's alive!
  let localArray = arr2.slice();
  for(let i=0;i<arr1.length;i++){
    localArray.splice(n,0,arr1[i])
    n++;
  }
  return localArray;
}



frankenSplice([1, 2, 3], [4, 5, 6], 1);

```

### fitting a number in between two numbers.



```
function getIndexToIns(arr, num) {
  arr.sort(function(a, b) {
    return a - b;
  });

  for (var a = 0; a < arr.length; a++) {
    if (arr[a] >= num)
      return a;
  }

  return arr.length;
}

```

### Chunky Monkey
```
function chunkArrayInGroups(arr, size) {

  var temp = [];
  var result = [];

  for (var a = 0; a < arr.length; a++) {
    if (a % size !== size - 1)
      temp.push(arr[a]);
    else {
      temp.push(arr[a]);
      result.push(temp);
      temp = [];
    }
  }

  if (temp.length !== 0)
    result.push(temp);
  return result;
}
```
