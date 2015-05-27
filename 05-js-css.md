JavaScript CSS by [Parsha Pourkhomami](http://twitter.com/parshap)
---

> This talk is about ideas

## CSS limitations:

- no way to define constants or vars
- can't extend the lang
- bad dependency mgmnt
- no code sharing/reuse
- no interoperability with the rest of our front end/JS code
- Solved by a variety of CSS Preprocessors (but still have issues)

### Problems:

Stylus:

```css
form
  color #ccc
  .field input
  .field textarea
    font Comic Sans
```

if we swap the top two lines:

```css
form
  .field input
  color #ccc
  .field textarea
    font Comic Sans
```

Stylus thinks our color delectation is a selector: `form color #ccc`

- LESS has 8 different ways to import dependencies
- LESS and Sass have opposite variable assignment from Sass (LESS uses the **last** assignment of the variable, Sass uses the assignment **above** the variable being implemented):
- White space sensitive math: `margin: 10px - 2px` vs. `margin: 10px -2px`

## Using JS to express CSS Better

CSS:

```css
.button {
  color: red;
}
```

JS:

```js
var styles = {
  ".button": {
    color: "red",
  }
}
```

- can't assign multiple values to the same property but can set property fall backs
- can express media queries
- can express @ rules
- pretty much just using literals **(JSON)**

## How to Use in Browser

```js
> toCSS(styles)
".button {
  color: red,
  ...
}"
```

## Advantages

- JS has built-in variables -- can use them to define constants in one place
- JS has math built-in w/less semantics issues
- Code reuse (can create functions)

A mixin created in JS:

```js
function createButtonStyles(baseColor {
  return {
    color: baseColor,
    ":hover": {
    color: mix(baseColor, "#000");
    }
  }
})
```

- when using canvas, easy to share values
- can use modules to create multiple files and import dependences (constants, functions, style declaration sets)
- can use NPM for modules (utility mods)

## Disadvantages

- making extra network request to build your styles
- super experimental thinking

## Taking over the Browser

- **Prereq: We need a CSS AST (abstract syntax tree)**
- CSS feature queries: `@supports` --> test if a device supports a certain CSS feature

```css
@supports (display: flex) {
  div {
    display: flex;
  }
}

@supports not (display: flex) {
  div {
    float: left
  }
}
```

- not many browsers support this CSS feature yet, but we can do this in JS and use JS feature detection
- Flexbox polyfill (already an NPM module)

