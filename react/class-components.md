# React Class Component
A react class component is an ES6 class that is defined in the React Library and
is used when building React Components that need lifecycle methods or internal
state.

## Constructor
The constructor is where we set up our initial state. It is rarely used for
anything more than this.

```jsx
constructor(props) {
  super(props)
  this.state = {
    id: 0,
  }
}
```

## State
State is used to track things internal to this component _or_ it's children as
the state can be passed as props. It can be changed via the `this.setState`
function provided by React and accessed anywhere in the React component via
`this.state`

And we change with the `setState` function provided to us by React:
```jsx
changeId = () => {
  const randomId = Math.random() * (100 - 0);
  this.setState({ id: randomId })
}
```

## Default Props
Default props are a way of defining props if the component is not passed any.
Here is how it is done:

```
class Greeting extends React.Component {
  // ...
}

Greeting.defaultProps = {
  name: 'Mary'
};
```

`name` will be defaulted to "Mary" if not passed to `<Greeting />` when the
element is created.

## Lifecycle Methods
These are special methods that are exposed by React that happen at certain
events such as mounting, unmounting, recieving props, updating. These are
extremely powerful and often used for hitting endpoints or performance tweaking.
The [official react
docs](https://reactjs.org/docs/react-component.html#the-component-lifecycle) are a great resource for this.

## Class Methods
These are functions that are definined on the class. They have access to the
proper `this`.

## Render Method
This is a special method that is called by React when a render is wanted. This
is where your view is constructed in the form of JSX.
