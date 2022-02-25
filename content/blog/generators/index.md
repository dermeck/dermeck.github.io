---
title: Generator Functions Notes
date: "2022-02-24"
description: "Notes on the talk *Understanding Generator Functions & Using Redux Saga* "
---

*Notes on the talk "Understanding Generator Functions & Using Redux Saga"*

## What are Generators Functions?

Generator Functions are functions that can be exited and later re-entered. Their context (variable bindings) will be saved across re-entrances.

### Declaration
They are declared via `function*` keyword.

```javascript
function* generator() {git
  yield 1;
  yield 2;
}
```

- `yield` expression is used to pause/exit the function and return a value (it an also take in a value when the function is re-entered)
- `*yield` is used to delegate to another generator function

### How to run

- when the function is called it returns an iterable object called Generator
- when `next()` is called on this object the function body is executed untill the first `yield` is reached
- this call returns objects with properties `value` and `done`
- `next()` can be called again to proceed with the execution at this point


```javascript
const gen = generator(); // "Generator { }"

console.log(gen.next()// { value: 1, done: false }
console.log(gen.next()// { value: 2, done: false }
console.log(gen.next()// { value: undefined, done: true }
```

### Async example

Asynchronous functions which call next when done

```javascript
function request(url) {
    callfetch(url, function(response){
        it.next(response);
    });
}

function* main() {
    var result1 = yield request("url1");
    var data = JSON.parse(result1);

    var result2 = yield request("url2?id=" + data.id);
    var resp = JSON.parse(result2);
}

var it = main();
it.next(); // start
``` 

### Ressources:
- [Understanding Generator Functions & Using Redux Saga](https://www.youtube.com/watch?v=o3A9EvMspig)
- [MDN](https://developer.mozilla.org/de/docs/Web/JavaScript/Reference/Statements/function*)
