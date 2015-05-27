You Wont Believe This One Weird Way to Rewrite Closures by [Jonathan Martin](https://twitter.com/nybblr)
---

closure() === scope + statements;


### A Little History

- Fortran (c. 1957) has no global variables or closures
- x86 Assembly also had no global vars or closures
- Ruby : OO Programming lives on
- React's virtual DOM rewrote the entire idea of the DOM to speed it up -- let's do that with closures

- We're going to develop our own polyfill for going back to the simplicity of JS w/o closures

### RULES:

1. No function params, var, or variable assignment
2. No function memoization (no cache object)
3. We can access one global variable
4. We can use amnesic function bodies (don't remember their scoping rules, just buckets of statements)
5. We can use shortcut local variables


### Function Aliases:

- s() <-- set `scope.set.bind(scope);`
- f() <-- function
- g() <-- get

### Scope for global context:

```
var Scope = (function() {
  function Scope() {
  this._dict() = {};
  }

  //setting aliases
  Scope.prototype.get = function(key) {
    return this._dict[key];
  }

  Scope.prototype.set = function(key) {
    ...
  }

  Scope.prototype.pop = function() {
    this._dict = {};
  }

  ...

}
```

Making CHanges

```
Scope.prototype.push = function() {
  //any time we look up a variable we will get it, but when we try to set it, we get a new var w/o changing the parent:
  this._dict = this._forkDict();
}

// and then...

Scope.prorotupe._forkDict = function() {
  var dict = this._dict;
  var F = function() {};
  F.prototype = Object.create(dict);
  F.prototype.constructor = F;
  F.prototype._parent ...
}
```

This is going too fast for me to keep up :) But its pretty awesome

- Building a function (which always has its own scope), to `push` it into the `parent scope []`, then `pop` it
- in < 70 lines of code, we have our own implementation of local vars
- [Github Link](https://github.com/nybblr/closures)