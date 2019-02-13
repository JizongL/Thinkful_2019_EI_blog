---
layout:post
title: Correlation with Javascript 
date: 2019-02-09 11:11
categories: Javascript
tags: javascript eloquent_javascript correlation
---

* content 
{: toc}


## Data Structure 

Use Object
Example here:The lycanthrope’s log


```javascript
let journal = [];

function addEntry(event,squirrel){
    journal.push({event,squirrel});
}


```

Add entry 

```javascript
let journal = [];

function addEntry(events, squirrel) {
  journal.push({events, squirrel});
}

addEntry(["work", "touched tree", "pizza", "running",
          "television"], false);
addEntry(["work", "ice cream", "cauliflower", "lasagna",
          "touched tree", "brushed teeth"], false);


```



![Phi table]("http://eloquentjavascript.net/img/pizza-squirrel.svg")

Formula 

$$
\Phi = \frac{n_{11}n_{00}-n_{10}n_{01}}
{\sqt{(n_{1.}n_{0.}n_{.1}n_{.0})}
$$

The notation $n_{01}$ indicates the number of measurements where the first variable (squirrelness) is false (0) and the second variable (pizza) is true (1). 

The value n1• refers to the sum of all measurements where the first variable is true, which is 5 in the example table. Likewise, n•0 refers to the sum of the measurements where the second variable is false.

## Computing Correlation 

```javascript
function = phi(table){
    return (table[3]*table[0]-table[2]*table[1])/
        Math.sqrt((table[2]+table[3])*
                    (table[0]+table[1])*
                    (table[1]+table[3])*
                    (table[0]+table[2])*
        )
}
console.log(phi([76, 9, 4, 1]));
// → 0.068599434
```


```


```