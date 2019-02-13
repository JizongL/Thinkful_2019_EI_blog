---
layout: post
title:  Questions to ask memtor
date:   2019-02-06 10:38
categories: Thinkful
tags: question memtor
---

* content
{: toc}

See questions from the comment of the following links.

[preventDefault](https://repl.it/@JizongL/eventpreventDefault-demo-jQuery-1)



### Question 1

```javascript
$('.js-form').submit(event => {
  // this stops the default form submission behavior
  event.preventDefault();
  const userTextElement = $(event.currentTarget).find('#user-text');
  $(".js-display-user-text").text(`user text is:  ${userTextElement.val()}`);
  userTextElement.val("");
});
```

what is this line for `userTextElement.val("");`?
