# javascript

## Primitive types:

def: Data that only represente a single value. ex n = 5, in memory the value of n is number

- number
- boolean
- undefined: use as default value for any declaration variable.
- null
- Symbol: new in es6, use for object property, make sur that is unique. (For object property).
- Object

### Operator: typeof

ex: typeof {var}

## None primitive types:

### Array

```js
typeof [] => // 'object'
```

### Function

```js
typeof function () {} => // 'Function'
```

### diagram

- object {}
- array extends object
- function extends object
  function and array are object.

proof:

```js
function a() {
  return 5;
}
a.hi = "HI";
console.log(a.hi); // HI
```

### Wrapper object

Always creating wrapper object on primitive types:
ex: true.toString() // 'true' <=> Boolean(true).toString() // 'true'
