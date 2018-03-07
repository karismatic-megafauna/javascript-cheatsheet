# JSX
[The original documentation](https://reactjs.org/docs/introducing-jsx.html) by
React is really great.

The best way of thinking about JSX is like `js` but just with some `xml`
flavoring! In fact, JSX is _liteally_ an XML-like syntax over some functions
exposed by React.

Check out this code:
```jsx
// Define
const TheMotto = ({ city, motto }) => {
  return (
    <div>
      {city} : {motto}
    </div>
  )
};

// Use
<TheMotto city="Wakanda" motto="Wakanda forever" />
```

All that XML / HTML stuff is JSX. And here is what it would look like witout it:
```js
const TheMotto = ({ city, motto }) => {
  return React.createElement(
    "div",
    null,
    city,
    " : ",
    motto
  );
};

React.createElement(TheMotto, { city: "Wakanda", motto: "Wakanda forever" });
```
You can play with this more here -> [babeljs transpiler playground](https://babeljs.io/repl/#?babili=false&browsers=&build=&builtIns=false&code_lz=MYewdgzgLgBAKgCwKYFkRSiGBeGAKAbxmAEsoBPAGhgFt1MYBfAShwD4YCAoGGAJyRQArnzD4evGAB4AJiQBubCbwCQBUhUYwAXAToYQjCSqkB6OYonMujANxcuUxKnpYN5bACIA6gEMA1r5gMr6etK5efoHBvjAAZiAC8kh8YaZKQA&debug=false&forceAllTransforms=false&shippedProposals=false&circleciRepo=&evaluate=false&fileSize=false&lineWrap=true&presets=react&prettier=false&targets=&version=6.26.0&envVersion=)

If, at the end of the day you prefer the `createElement` interface, go for it!!
However, I'll stick with JSX :P

## Some background
JSX used to be a rather contraversal topic as it was seen as combining things
that the web development community had already said was best practice to keep
separate.

However, nearly 5 years after [Pete Hunt's
talk](https://www.youtube.com/watch?v=x7cQ3mrcKaY) on rethinking best practices
we see that JSX resonated with the community and has been heavily adopted not
only by users of React but by creators of other languages such as
[Vue.js](https://vuejs.org/).
