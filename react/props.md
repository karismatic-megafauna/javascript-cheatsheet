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

We are calling the "Card" component and assinging values to specific slots.
Order does not matter with Props as the variables are named.

Here is how that Card component might be defined:
```jsx
const Card = (props) => {
  const { title, body, rating } = props;
  return (
    <div>
      <h1>{title}: {rating}</h1>
      <p>{body}</p>
    </div>
  )
}
```
