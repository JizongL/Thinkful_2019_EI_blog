---
layout: post
title:  Free Code Camp Note
date:   2019-01-31 10:05
categories: code_collection
tags: css 
---

* content
{: toc}



### box-shadow for thumbnail

```css
#thumbnail{
  box-shadow: 0 10px 20px rgba(0,0,0,0.19), 0 6px 6px rgba(0,0,0,0.23);
}
```

### Gradual CSS Linear Gradient

```html
<style>
div{
  border-radious:20px;
  width:70%;
  height:400px;
  margin:50px auto;
  background:linear-gradient(35deg,#CCFFFF,#FFCCCC);
}
</style>

<div></div>
```
### Create stripes with `repeating-linear-gradient()`

```css
  div{ 
    border-radius: 20px;
    width: 70%;
    height: 400px;
    margin:  50 auto;
    background: repeating-linear-gradient(
      45deg,
      yellow 0px,
      yellow 40px,
      black 40px,
      black 80px
    );
  }

</style>

<div></div>
```

