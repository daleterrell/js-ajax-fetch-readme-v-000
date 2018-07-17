# JavaScript fetch()

## Overview

We'll use  `fetch()` and describe the problems that it helps solve. 

## Objectives

1. Explain how to use `fetch()` in modern browsers
2. Describe the differences between `fetch()`, `jquery.ajax()` and `XMLHttpRequest`
3. Get data from a remote endpoint using `fetch()`

## Introduction

Getting remote data in JavaScript has classically required a fair amount of plumbing to make things happen.

It's not that it's *hard* to get data out of `XMLHttpRequest`, but it does take quite a bit of setup. Let's make a simple request of the GitHub repository commits API.

```js
let xhr = new XMLHttpRequest();
xhr.open('GET', 'https://api.github.com/repos/jquery/jquery/commits');
xhr.responseType = 'json';

xhr.onload = function() {
  console.log(xhr.response);
};

xhr.onerror = function() {
  console.log('Booo');
};

xhr.send();
```

