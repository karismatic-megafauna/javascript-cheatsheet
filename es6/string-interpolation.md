# Template Literals (String Interpolation)
There are a few features that are enabled with Template Literals, the most used
being the String Interpolation.

Using the back-tick (\` \`) instead of double or single quotes for strings allows
you to interpolate a variable. For instance:

```js
const myString = `some string with a value in it: ${value} - :)`
```

Using the dollar sign and brackets inside of the back-ticks allows you to render
a variable inside the string!

No more of doing this nasty and error prone string concatenation:

```js
const myString = "some string with a value in it " + value +  " - :)"
```
