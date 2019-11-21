Javascript - features

## Features in JS we use
``` js
class Native
arrow => "function"
const {destruct: (it)} = object
const [head, ...tail] = [1,2,3,4]
import {es} from "modules"
``` 

## Tooling
- Babel
- core-js
- webpack
- Prettier
- ESLint

## Introduction
ES 2015+ (ES6)
Etma Script -> organization which standardize the JS.
All the Web depends on JS so the only development is to add and grow, removing is out of the question.

#### Resources
MDN
JS for the impatient programmers - Book (https://fktpm.ru/file/225-javascript-for-impatient-programmers.pdf)

### Variables declaration
- `var`
   a function can be invoked before it is defined and visible everywhere
- `let` -> mutable variables
- `const` -> immutable variables. You can still manipulate an array, but you cannot reassign it.


### class Native
```js
class Native {
  'use strict';

  // getters and setters
  get property() { return value };
  set property(val) { return this.value = val};

  shorthand() { return "definition" }
}

const obj = {
  shorthand() { return "it works" }
}

const n = new Native();
n.shorthand() // This is the way to create an instance method


class Native extends Base {
  constructor(..args) {
    // You need to call the parent ctor before using `this`
    super(...args);

    this.value = "initial"
  }
}

class Native extends Base {
  // Shorthand for this.value in the ctor. You can skip the ctor at all.
  eventHandler = event => {
    this //always proper this
  }
}
```

### Arrow Functions
They never rebind this -> they always get it lexically (from scope).
```js
const fn = arrow => "function";
fn()

// if we want to fetch all arguments we do it like this
const fn = (...args) => {
  console.log(args); // this is a array
}

```

### Destructuring

```js
const obj = {foo: 42};
const {foo} = obj;

const array: [head, ...tail] = [1,2,3];
head = 1
tail = [2,3]
```

### Imports - usually static
```js
import {es} from "modules"
import React, {useState} from 'react'
useState() => instead of React.useState()

import * as React from 'react'
import {Node} from 'graphql'
```

### Immutability helpers
```js
import update from 'immutability-helper';
```


### Exports
```js
export default class Context {} 
// You can have only one default class
import {Context} from "./fooo/bar"

import * as Context from "./path"
```

### Other
```js
if (foo.bar == null) // Check if it is null or undefined
foo?.bar -> is not the same as (foo && foo.bar)
```