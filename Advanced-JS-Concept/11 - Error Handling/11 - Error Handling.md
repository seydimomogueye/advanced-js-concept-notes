# 132 - Errors In JavaScript

```js
console.log(Error); // constructor function class
new Error('oops');
```

- Javascript has keyword `throw` to throw something and our javascript code stop running instead handling
the thrown error.

```js
throw new Error();
```

when the throw statement is encounter by the program, the execution of the current function will stop
and control will be past to the next part of the call stack.

- We can throw anything in javascript:

```js
throw 'string'
throw true
throw Error
throw new Error()
```

- We have tree(3) properties for error.
```js
const myError = new Error('oops');
myError.name // => Error
myError.message // => oops
myError.stack // => Error: oopsie at <anonymous>:1:17
```

- Javacript has many builtin constructor to handle errors:
```js
new SyntaxError // => Error on syntaxe.
new ReferenceError // => trying to get undefined variable.
```
they are natively thrown.
