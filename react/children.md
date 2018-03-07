# Children
Children is a reserved prop for what is in-between the two tags of a React
Component. This is really useful when building out components that mimic how we
build things in HTML.

Take this example:
```jsx
// Usage
<SuperCard name="T'Challa" alias="Black Panther">
  <p>The black pather is from Wakanda and is hella dope</p>
</SuperCard>
```

```jsx
// Definition
const SuperCard = ({ name, alias, children }) => (
  <div>
    <div className="header">
      <h1>{name}</h1>
      <h2>{name}</h2>
    </div>
    <div className="body">
      {children}
    </div>
  </div>
)
```

Here, we see that we have a third `prop` that seems to come from thin air,
`children`. In this case it is actually referring to the following code:

`<p>The black panther is from Wakanda and is hell dope</p>`

And this code gets rendered inside the div with the className of body in the
`SuperCard`. It's a very good pattern and can do much more than this!

Max Stoiber [has a great blog post on
children](https://mxstbr.blog/2017/02/react-children-deepdive/). If you are
interested in some of the more advanced aspects of the topic, give it a read!
