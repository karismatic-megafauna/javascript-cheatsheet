# Spread and Rest
The spread syntax is a way of expanding out an array, object or function
parameters. It's really useful for copying and combining data! [The
Docs](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Spread_syntax)
are really good on this topic!

## For Objects
For objects the syntax is pretty straightforward:

```js
const firstObj = {
  name: 'george',
  mood: 'curious',
}

const secondObj = {
  species: 'monkey',
  type: 'fictional',
}

const pet = { ...firstObj, ...secondObj }

console.log(pet)
// {
//   name: 'george',
//   mood: 'curious',
//   species: 'monkey',
//   type: 'fictional',
// }
```

In this example we combined two obejects togeather into a new one via the spread
operator.

## For Arrays
If you understand the above concept for obeject literals, then you understand it
for Arrays as well! This is really useful when wanting to add arrays together.

```js
const arrayOne = ['Hello', 'from']
const arrayTwo = ['other', 'side']

const lyric = [...arrayOne, 'the', ...arrayTwo];
// 'Hello', 'from', 'the', 'other', 'side'
```

Also, notice that both arrayOne and arrayTwo are not mutated!

## For Functions
Not nearly as used but still convenient is function argument spreading:

```js
const myFunction = (a, b, c) => {
  console.log('a:', a)
  console.log('b:', b)
  console.log('c:', c)
}
const args = ['1', '2', '3']
myFunction(...args)
```

# What is this Rest thing anyways
Commonly confused with the over powered pokemon move made popular by Snorlax,
`rest` actually referrs to the remaining arguments in a function and is used for
collecting them into an array. While the syntax is identecial, this is _not_ the
same as spread and is actually the exact opposite. So if you see the spread
syntax in a function _definition_  as opposed to the usage, then you are
acutally seeing the "rest" parameter.

```js
const myFunction = (a, b, ...theRest) => { // <- rest
  console.log('a:', a)
  console.log('b:', b)
  console.log('theRest:', theRest)
}
const args = ['1', '2', '3', '4', 'shut', 'the', 'door']
myFunction(...args) // <- spread

// Our arguments would look like this:
// a -> 1,
// b -> 2,
// theRest -> ['3', '4', 'shut', 'the', 'door']
```
