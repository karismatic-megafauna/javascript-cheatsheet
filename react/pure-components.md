# Pure (Stateless) Components
These are simple UI components that do little more than take some information
and display it. They are stateless and do not have access to the react
lifecycle. As we move further away from complex business logic we start seeing
more of these components.

Here is what one looks like:
```jsx
const Card = ({ title, body, rating }) => (
  <div>
    <h1>{title}: {rating}</h1>
    <p>{body}</p>
  </div>
)
```

_* note *_
This example component uses an implicit return and argument destructuring,
without using these, this is what `Card` would look like:
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
