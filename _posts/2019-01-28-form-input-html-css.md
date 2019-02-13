---
layout: post
title:  Javascript Thinkful prep course note
date:   2019-01-28 10:18
categories: Thinkful
tags: form input css html
---
* content
{: toc}


## Anatomy of Forms and inputs

`<fieldset>` and `<legend>`

* The `<fieldset>` element is used to group together related inputs and labels.

* The for attribute goes on a label, and its value should be set to the ID of the input it's for.

While the label element requires opening and closing tags, inputs do not.






```javascript
<label for="first-name">First name</label>
<input id="first-name" name="first-name" type="text">
```

if `<label>` wraps around input, no need `for id`.

```html
<label>First name
  <input id="first-name" type="text">
</label>
```

We lean slightly towards the first method because when the label wraps the input, margin-right behavior is surprising — we think of labels as coming before the input, but if you set a right margin on a label wrapping an input, that margin right will appear to come after the input, not the label.


### Input attributes

`placeholder` `required` `pattern`
```javascript
 <input type="tel" pattern="[0-9/-]*" name="phone" id="phone" placeholder="888-888-8888" title="A typical U.S. phone number" required/>
 ```



 The main difference between the `placeholder` and `value` attributes is that the value attribute value text stays in place when a control has focus unless a user manually deletes it.

 [value vs placeholder](https://codepen.io/shayhowe/pen/lHnFm)

 `required`
Validation also occurs specific to a control’s type. For example, an `<input>` element with a type attribute value of email will require not only that a value exist within the control, but also that it is a valid email address.

### Type

 `type='email'` will be valid if the user inputs text that has an @ with text before and after

 input type also provide some accessibility by dictating the kind of keyboard a smartphone will display for a user:

### The `<select>` and `<option>` elements.

pre-select an individual <option> by adding the `selected` attribute.

`<optgroup>`element to wrap multiple <option> elements under a given group name.

when designing forms: keep them short, simple, and as semantic as possible

### textarea tags

`<textarea>`

`<textarea>` element differs from the `<input>` element in that it can accept larger passages of text spanning multiple lines

the type attribute doesn’t apply here, but the name attribute is still used.

```html
<textarea name="comment">Add your comment here</textarea>
```
### Other input types
`radio`

`checkbox`

[drop-down list](https://codepen.io/shayhowe/pen/fvzDK)

[Multiple Selections](https://codepen.io/shayhowe/pen/DoEKh) Just added multiple inside select tag.

[hidden input](https://www.w3schools.com/tags/tryit.asp?filename=tryhtml5_input_type_hidden)

[submit button](https://codepen.io/shayhowe/pen/evnop)

[File input](https://codepen.io/shayhowe/pen/pngud)Unfortunately, styling an `<input>` element that has a

type attribute value of file is a tough task with CSS

## Key words to look up
` Form processing` (a deeper topic to explore)
check out [PHP5 Tutorial](https://www.w3schools.com/php/default.asp)



## Download and Links
[Wave accessibility tool](http://wave.webaim.org/)

[Creating Accessible Forms](https://webaim.org/techniques/forms/#ensure)

Be sure to include important cues or instructions in associated labels or at the beginning of the form.

[A form of madness](http://diveinto.html5doctor.com/forms.html) must read this one.

## quiz

* Following accessibility best practices for forms

* Validating form inputs

* Creating and describing forms and form elements

* Learning new input types
