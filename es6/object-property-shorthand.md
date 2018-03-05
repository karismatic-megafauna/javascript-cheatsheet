# Object Property Shorthand
This is an extremely used feature of ES6 because it is so useful!

Let's imagine we had a function that returned an object to us:

```js
const getPet = (name, mood, species) => {
  return {
    name: name,
    mood: mood,
    species: species,
  }
}
```

If the name of the variable is the same as the key, then you don't have to write
the duplicate name, you can just write it like this:

```js
const getPet = (name, mood, species) => {
  return {
    name,
    mood,
    species,
  }
}
```

While this is pretty neat, there are [a few other cool
things](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Object_initializer)
that are added to object literals in es6 that are also useful! Check them out!

