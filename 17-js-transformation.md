JavaScript Transformation by [Sebastian McKenzie](http://twitter.com/sebmck)
---

- JS Transformation: you put JS in, you get JS out
- ES6 transpilier: 6to5 --> so many name changes --> Babel
- AST: (Abstract Syntax Tree) group of deeply nested objects that express an element
- *Parser*: turns code into AST
- *Transformer*: Manipulates AST (where the tricky stuff happens)
- *Generator*: Converts & executes
- allows you to write in one context and interpreter will replace for you
- ES2015 is awesome, browser support is not

### Arrow Functions

- `var multiply = (num) => num * num`
- implicit return
- inherits arguments
- can't "new it": `new foo = () => {}` so `new foo;` should be illegal
- do **not** use transpilers as a basis to learn new language features

### Application Optimization

- React.js --> JSX

### Browser Compatibility

- fixes IE8 which has a ton of issues
- automate compatibility w/Babel functions

## Emojification

- unicode point escapes: `var \u{1f605} = "whatever"` <-- this means emojis in our codes!

> You don't even need comments in this stage, you can just represent your code in emojis

- `npm install babel babel-plugin-emojification`