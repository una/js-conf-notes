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

This is going too fast for me to keep up :) But its pretty awesome

Here are better notes from [Jennifer](https://gist.github.com/jennifer-mann/544da3863bbe47773d70)

```
var ClosureRegistry = (function() {
  function ClosureRegistry() {
    this._registry = ;
  };
  delegate(['get', 'set', 'args']{
    from: ClosureRegistry.prototype,
    to: function() { return this._registry; }
  });
  delegate(['push', 'pop']{
    from: ClosureRegistry.prototype,
    to: function() { return this.scopeForCurrentClosure(); }
  });

  ClosureRegistry.prototype.scopeForCurrentClosure = function() {
    return this._registry[this._registry.length - 1];
  };
  ClosureRegistry.prototype.func = function(name, params, body) {
    var _this = this;
    var scope = this.scopeForCurrentClosure().fork();
    this.set(name, function(){
      _this.push(scope);
      _this.args(params, arguments);
      var result = body();
      _this.pop();
      return result;
    });
  };
};

var Scope = (function() {
  function Scope(dict) {
    this._dict = dict || {};
  }
  Scope.prototype._forkDict = function(key) {
    var dict = this._dict;
    var F = function() {};
    F.prototype = Object.create(dict);
    F.prototype.constructor = F;
    F.prototype.__parent = dict;
    return new F();
  };
  Scope.prototype.get = function(key) {
    return this._dict[key];
  };
  Scope.prototype.set = function(key) {
    this._dict[key] = value;
  };
//  Scope.prototype.push = function(key) {
//    this._dict = this._forkDict();
//  };
//  Scope.prototype.pop = function(key) {
//    this._dict = this._dict.__parent;
//  };

  Scope.prototype.form = function() {
    return new Scope(this.//
  };

  Scope.prototype.args = function(names, values) {
    for (var i = 0, l = names.length, i < l, i++ ) {
      this.set(names[i]) //
    }
  };
  return Scope;
}());
```

- Building a function (which always has its own scope), to `push` it into the `parent scope []`, then `pop` it
- in < 70 lines of code, we have our own implementation of local vars
- [Github Link](https://github.com/nybblr/closures)