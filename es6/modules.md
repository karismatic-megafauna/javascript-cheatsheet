# Modules
A fancy way of saying file that exports something. The word "module" in the
context of ES6 is really talking about _how_ something is either imported or
exported.

## Default Export / Import
The main rule with a default export is that there can only be one per module.

It's clearer with an example:

```js
// util.js -> module definition

const usefulUtil = () => {
	return 'such useful, much util. wow.';
}

export default usefulUtil;
```

```js
// App.js -> module usage

import superUsefulUtil from './util.js';

console.log(superUsefulUtil);
```

There are some immediately odd things that you will probably notice, the module
that we are exporting is calling the function `usefulUtil`, but where the
function is actually used we are calling it `superUsefulUtil`. This is a feature
of default exports, they don't have to match the name of the exported function
as you can only have one per file.

This is both a blessing and a curse. It allows us to avoid shotgun surgery when
refactoring at the cost of cognitive overhead as you have to keep track of the
`N` differently named functions that are all acutally the same function.

## Named Export / Import
Named exports are simple, you are exporting the function exactly as it is named.
Nothing fancy.

Building on our example...let's say our util module grows and has 2 exported
functions:
```js
// util.js -> module definition

export const usefulUtil = () => {
	return 'such useful, much util. wow.';
}

export const anotherUsefulUtil = () => {
	return 'such useful, much another. wow.';
}
```

```js
// App.js -> module usage

import { usefulUtil, anotherUsefulUtil } from './util.js';

console.log(usefulUtil, anotherUsefulUtil);
```

While the module definition changes very little, the usage is significantly
different. Now you _must_ import functions from the `util` module _exactly_ as
they are named.

## Mixed Usage of Named and Default
