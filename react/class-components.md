# React Class Component

A react class component is an ES6 class that is defined in the React Library and
is used when building React Components that need lifecycle methods or internal
state.

```js
class Contact extends React.Component {
  constructor(props) {
    super(props)
    this.state = {
      loading: true,
      nameFromInterwebz: '',
    }
  }

  printId = (id) => {
    return `Here is my id: ${id}`
  }

  render() {
    const { loading } = this.state
    return (
      <div>
        { loading && printId(4) }
      </div>
    )
  }
}
```

# Constructor
The constructor is where we set up our initial state. It is rarely used for
anything more than this.

```js
  constructor(props) {
    super(props)
    this.state = {
      loading: true,
    }
  }
```

# State
State is used to control
