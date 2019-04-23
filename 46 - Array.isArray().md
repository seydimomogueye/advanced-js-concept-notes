# Arrays types.

example:

```js
var array = [1, 2, 3];
// same as
var array = {
  0: 1,
  1: 2,
  2: 3
};
// thus
typeof array; // => 'object'
```

- In new javascript we now have `Array.isArray` so instead of using typeof we use isArray from Array.
  example:

```js
Array.isArray([1, 2, 3]); // => true
Array.isArray({}); // => false
```
