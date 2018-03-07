# Destructuring
Is a really useful way of taking values out of an object and making them local
variables.

## The old way
The `dot notation` used to be the best way of pulling values out of objects.
Having to follow the `object.keyname` pattern on an unknown and growing number
of keys was painful and added a lot cruft for a relatively simple operation.
```js
const printPetName = (props) => {
  const firstName = props.firstName;
  const lastName = props.lastName;

  console.log(`Hey there ${firstName} ${lastName}!!`)
}

printPetName({ firstName: 'Chewie', lastName: 'Solo' });
```

We are passing an object to `printPetName` and then pulling out the values at
the keys `firstName` and `lastName`.

## Destructuring an Object
Destructuring helps us pull those values out in a much more conscise way.
```js
const printPetName = (props) => {
  const { firstName, lastName } = props;

  console.log(`Hey there ${firstName} ${lastName}!!`)
}
```
This basically takes the names of the keys in props and makes variables out of
them! So convenient!

## Destructuring the function arguments
One of the most common ways to destructure is in the function arguments.

```js
const printPetName = ({firstName, lastName}) => {
  console.log(`Hey there ${firstName} ${lastName}!!`)
}
```
It is very common to see destructuring in this form, so get used to that
function signature!


## Default Values
Finally, doing destructuring in the function arguments like this allows for us
to assign default values more logically:

```js
const printPetName = ({firstName = 'Chewie', lastName = 'Solo'} = {}) => {
  console.log(`Hey there ${firstName} ${lastName}!!`)
}

printPetName()
```
Personally, `({firstName = 'Chewie', lastName = 'Solo'} = {}) => {` is basically
alien jibberish to me. So I prefer to have my default values in two steps.

```es6
const printPetName = (props = {}) => {
  const { firstName = 'Chewie', lastName = 'Solo' } = props;

  console.log(`Hey there ${firstName} ${lastName}!!`)
}

printPetName()
```

Default values mixed with destructuring is an art and there really is no correct
answer, so just do what feels right for you and your team :)
