---
layout: post
title:  responsive design basics.
date:   2019-01-19 16:40
categories: Thinkful
tags: javascript
---

* content
{: toc}


`Media queries`


```css
@media only screen and (min-width: 640px) {

  .foo {
    /* do something to
    override default settings*/
  }
}

@media only screen and (min-width: 800px) {

  .foo {
    /* do something to
    override settings at previous threshold settings*/
  }
}
```

The classic grid: 960px, twelve columns

<img src = "https://tf-curricula-prod.s3.amazonaws.com/curricula/6e8033080cefd638fd9ad37c3b230d99/WEB-DEV-001/v1/assets2/1.6.2_responsive_grids/grid_annotated_design.png")

That can be expressed as a percentage: 60/960 = 0.0625, which means that the width of a single column is 6.25% of its parent row. Fluid columns scale up or down with row width.

The gutter can be expressed as a percentage of the parent row, then, as: 20/960 = 0.02083333333.. ~= 0.0208 which is 2.08%.

note that the 2.08% gutter is split in half on the left and right
```
.col-3, .col-4, .col-6, .col-12 {
  float: left;
  padding-left: 1.04166666%;
  padding-right: 1.04166666%;
}
```

[starting point](https://repl.it/@JizongL/CSS-responsive-grid-challenge-1) of this challenge.

Check out this [Challenge](https://repl.it/@JizongL/CSS-responsive-grid-challenge)

## Keywords to explore

[Responsive images](https://alistapart.com/article/responsive-images-in-practice)

## Good articles to read

[Which One: Responsive Design, Device Experiences, or RESS?](https://www.lukew.com/ff/entry.asp?1509) by [Luke Wroblewski](https://www.lukew.com/about/)

[Multi-Device Web Design: An Evolution](https://www.lukew.com/ff/entry.asp?1436)


## Media
The `@media` rule is used in media queries to apply different styles for different media types/devices.

## Responsive Patterns
[A collection of patterns and modules for responsive designs](https://bradfrost.github.io/this-is-responsive/patterns.html)
by [Brad Frost](http://bradfrost.com)


## Book Collections

[Automic Design](https://shop.bradfrost.com)

## quiz

* Explaining the principles of responsive design (mobile-first, content-driven, responsive)

* Using media queries to override default styles

* Analyzing and explaining the float: left; approach to implementing a responsive grid

* Coding up designs that call for more than one layout, depending on the width of the viewport
