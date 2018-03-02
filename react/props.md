# Props
Props are a way of passing data to a React component, think of them as the
arguments of a function.

Take the following code:
```jsx
<Card
  title="Wakanda"
  body="is a pretty neat place"
  rating={5}
/>
```

The _props_ in the above code are `title, body, rating`, and their values are
`"Wakanda", "is a pretty neat place", 5`. In fact, they are quite literally just
an object that looks like this:

```js
{
  title: "Wakanda",
  body: "is a pretty neat place",
  rating: 5,
}
```

So _all_ react is doing is taking whatever key value pairs we pass it, putting
it in an object and passing that object along as the only argument to it's
definition. In factw

Speaking of the definition, here is how that `Card` component might be defined:
```jsx
const Card = (props) => {
  const title = props.title;
  const rating = props.rating;
  const body = props.body;

  return (
    <div>
      <h1>{title}: {rating}</h1>
      <p>{body}</p>
    </div>
  )
}
```

Notice how the argument to our funciton is called `props`. That is our object
that the JSX interface

Props are one of the most important parts of React as it allows for your
application to communicate with itself. Just remember...

### _Props are just named arguments!!!!_
