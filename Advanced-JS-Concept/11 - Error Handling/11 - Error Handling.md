# 132 - Errors In JavaScript

```js
console.log(Error); // constructor function class
new Error("oops");
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
throw "string";
throw true;
throw Error;
throw new Error();
```

- We have tree(3) properties for error.

```js
const myError = new Error("oops");
myError.name; // => Error
myError.message; // => oops
myError.stack; // => Error: oopsie at <anonymous>:1:17
```

- Javacript has many builtin constructor to handle errors:

```js
new SyntaxError(); // => Error on syntaxe.
new ReferenceError(); // => trying to get undefined variable.
```

they are natively thrown.

## 133 - Try Catch

2 methods to handle that.

1. `try {} catch(e){}`
   example:

```js
try {
  // thrown new Error("Oppsi") // stop as soon as a error happened.
  console.log("Working")
  thrown new Error("Oppsi")
} catch (error) {
  console.log(error);
} finally  {
  return  '_';
}
```

2. `catch(e){}`

Asynchronous code executed despite of a try catch
example:

```js
try {
  setTimeout(() => err, 1000); // still work, how to handle that ?
} catch (e) {}
```

## 134 - Async Error Handling

```js
Promise.resolve("asyncfail")
  .then(response => {
    throw new Error("#! error");
  })
  .then(response => {
    console.log(response);
  })
  .catch(err => {
    return err;
  })
  .then(response => {
    console.log(response); // print error received
  })
  .catch(err => {
    console.log("Final error");
  });

// example: 2
(async function() {
  try {
    await Promise.resolve("Opsi yes"); // catch this
    await Promise.reject("Opsi #1"); // catch this
    await Promise.reject("Opsi #2");
  } catch (e) {
    console.log(e);
  }
  console.log("is this still good ?");
})();
```

## 136 - Extending Errors

```js
class AuthError extends Error {
  constructor(message) {
    super(message);
    this.name = "Auth Error";
    this.favouriteSnacks = "grapes";
  }
}

// To avoid returning error with trace that will be use by bas people.
class DatabaseError extends Error {
  constructor(message) {
    super(message);
    this.name = "Database Error";
    this.favouriteSnacks = "grapes";
  }
}

class PermissionError extends Error {
  constructor(message) {
    super(message);
    this.name = "Permission Error";
    this.favouriteSnacks = "grapes";
  }
}

throw new AuthError('oopsie);
const a = new AuthError('oopsie);
a.favouriteSnacks // => grapes
```
