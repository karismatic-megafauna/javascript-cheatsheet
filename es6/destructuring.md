# Destructuring
Is a really useful way of taking values out of an object and making them local
variables.

Take this example:
```js
const printPetName = (props) => {
  const firstName = props.firstName;
  const lastName = props.lastName;

  console.log(`Hey there ${firstName} ${lastName}!!`)
}

printPetName({ firstName: 'Chewbacca', lastName: 'Hinrichs' });
```

We are passing an object to `printPetName` and then pulling out the values at
the keys `firstName` and `lastName`. Destructuring helps us pull those values
out in a much more conscise way.

```js
const printPetName = (props) => {
  const { firstName, lastName } = props;

  console.log(`Hey there ${firstName} ${lastName}!!`)
}
```

And for the most conscise we can destructure in the arguments!

```js
const printPetName = ({firstName, lastName}) => {
  console.log(`Hey there ${firstName} ${lastName}!!`)
}
```

It is very common to see destructuring in this form, so get used to that
function signature!
