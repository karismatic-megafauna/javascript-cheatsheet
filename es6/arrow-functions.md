# Arrow Functions
Arrow functions are a conscise way of defineing a funciton in ES6. They are
useful for 2 reasons:
- they are terser and make writing anonomyous functions less cluttery
- they retain their `this` context

When looking at [the docs on MDN about
Functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions)
it says this:
> Arrow functions capture the this value of the enclosing context

What they are saying here is `this` behaves more like how you would expect it to
behave. And that is great!

## Syntax
Here is the es5 function syntax:

```js
function printMessage(msg) {
  console.log(`Pssst... ${msg}`)
}
```

And here is the es6 Arrow syntax:
```js
const printMessage = (msg) => {
  console.log(`Pssst... ${msg}`)
}
```

This is a pretty easy syntax to pick up but it does have an interesting and
slightly hard to pick up caveat...

## The Confusing Stuff: Implicit vs Explicit Returns
Possibly the most common bug or source of confusion with arrow funcitons is the
implicit vs explict return coupled with adding a debugger. Let's go over the
syntax first then describe the trap nearly every developer falls into.

### Implicit Syntax
Let's say you have a function that returns some simple JSX, you could write that
function with the implicit syntax like this:

```jsx
const MyDiv = msg => <div>{msg}</div>
```

If you needed more space, but still wanted to have an _implicit_ return, you
would add some parenthesis `(` around the stuff you want to return:

```jsx
const MyDiv = msg => (
  <div>{msg}</div>
)
```

### Explicit Syntax
And if you like to explicity return, you would use curly braces `{` and the
`return` keyword:

```jsx
const MyDiv = msg => {
  return (
    <div>{msg}</div>
  )
}
```

That all make sense? Great!!! Let's dive into the "trap" I am trying to
illustrate...

## The Debugger Bugger
Imagine there is a bug in this function and you want to put a `debugger`
statement in this code. In the implicit case, a curious thing will happen...

```jsx
const MyDiv = msg => (
  debugger;
  <div>{msg}</div>
)
```

You get this fun compliation failure:
> Syntax error: Unexpected token

So to see what is going on in this code you _must_ convert it to a fat arrow
before proceeding...and here is the trap!

```jsx
const MyDiv = msg => {
  debugger;
  <div>{msg}</div>
}
```

See, I converted the `(` to a `{` and now my code compiles correctly without a
syntax error and I can inspect the code, but if you were to look at your UI at
this point you would see that your div with a message would be missing
`\(^___^)/`

What went wrong?

A simple mistake was made, the `return` was forgotten:

```jsx
const MyDiv = msg => {
  debugger;
  return <div>{msg}</div>
}
```

This is the code you wanted, and forgetting this return is one of the worst
experiences ever because you are likely dealing with some broken code anyways
and to figure out what is going wrong, you seem to "break" it even more! How
terrible! :( :( :(

Be careful of this caveat of arrow functions and be sure to know what you are
returning!
