# Type Coercion

- When comparing two value, javascript engine force to type the compared one to the same type on the variable
  we wanna compare to.

ex:

```js
1 == "1"; // => true. JS Engine converte '1' to 1.
```

```js
if (0) {
  console.log(5);
}
// => undefined because 0 was converted
```

- == is not predictible.

## Links

- https://dorey.github.io/JavaScript-Equality-Table/
- https://developer.mozilla.org/fr/docs/Web/JavaScript/Les_diff%C3%A9rents_tests_d_%C3%A9galit%C3%A9
- https://www.ecma-international.org/ecma-262/5.1/#sec-11.9.3

```js
-0 === +0; // => true
```
