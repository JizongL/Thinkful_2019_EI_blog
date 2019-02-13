---
layout: post
title:  Jquery note
date:   2019-02-05 17:43
categories: Thinkful
tags: jquery javascript
---

* content
{: toc}

## Document Ojbect Model 
`.getElementsByTagName()`
`.getElementsById()`
`appendChild()`
`insertBefore()`
`document.createTextNode()`

## DOM Traversal and Manipulation 
e.g
`let paragraphElements = $('p')`
 
e.g 

 ```javascript
function doHelloWorld() {
  $('.js-hide-it').addClass('hidden');
  $('.js-hello-world').text('hello world from JS');
}

doHelloWorld();
 ```
css code for styling and DOM minapulation should be separated. 

### .find() and .parent()

Find a child
`const someChild = $('some-child-name')`

Then apply `parent()` or `find()`
`someChild.parent('some-child-name').removeClass('some-css-name')`

`someChild.find('some-child-name').addClass('some-css-name')`


 ### prop() Disable an element 

 ```
 $("button").prop("disabled",true);

 ```

 ### Change text inside an element
 `.html()`
 `.text()`

### remove element 
 `.remove`
`.appendTo()`

`.parent()`
`.children()`
give the class `target` its nth children a `style`
`target:nth-child(n)`

### Use animated class
[Animated.Css](https://daneden.github.io/animate.css/)

`animated hinge`

### event.currentTarget

```
$('.js-form').submit(event => {
  // this stops the default form submission behavior
  event.preventDefault();
  const userTextElement = $(event.currentTarget).find('#user-text');
  $(".js-display-user-text").text(`user text is:  ${userTextElement.val()}`);
  userTextElement.val("");
});
```


`event.currentTarget` has been replaced with `this`.
`this` is more common in jQuery.
`this` only refers to the element within the callback function. 


Finally, note that in the context of callback functions, this will not behave as expected if you use ES6 arrow functions. If you need `this` to refer to the event object, stick with the `function` keyword.

### $(this)


### .append() and .appendTo()
They perform the same task. 
`$( "<p>Test</p>" ).appendTo( ".inner" );`
`$( ".inner" ).appendTo( "<p>Test</p>" );`

### Toggle and hiding with delegation 
read the note from the following [link](https://repl.it/@JizongL/toggling-and-hiding-button?language=html&folderId=)


### link Inside the Event Handler Function
`pageX, pageY`
`type`
`which`
`data`

```javascript
$( "input" ).on(
    "change",
    { foo: "bar" }, // Associate data with event binding
    function( eventObject ) {
        console.log("An input value has changed! ", eventObject.data.foo);
    }
);
```
`target`
`namespace`
`timeStamp`
`preventDefault()`
`stopPropagation()`

var element = $( this );

### Handle multiple events
Use key:value syntax
The following has two events, `click` and `mouseover`serve as key and the functions as value, all triggered by the target "p"

[Check this link](https://repl.it/@JizongL/multipleeventslistening)

```javascript
$( "p" ).on({
    "click": function() { console.log( "clicked!" ); },
    "mouseover": function() { console.log( "hovered!" ); }
});
```