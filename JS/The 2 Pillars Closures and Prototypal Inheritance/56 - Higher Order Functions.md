# Higher Order Functions

## Why ?

Don't repeat yourself:

- ex:

```js
function letAdamLogin() {
  let array = [];
  for (let i = 0; i < 1000000; i++) {
    array.push(i);
  }
  return "access granted to Adam.";
}

function letEvaLogin() {
  let array = [];
  for (let i = 0; i < 1000000; i++) {
    array.push(i);
  }
  return "access granted to Adam.";
}

letAdamLogin();
letEvaLogin();
```

- function with params

```js
const giveAccessTo = user => "Access Granted to " + user;

function letUserLogin(user) {
  // ++ | Now we tell the function what data to use.
  // More flexibility.
  let array = [];
  for (let i = 0; i < 1000000; i++) {
    array.push(i);
  }
  return giveAccessTo(user);
}
```

- High order function
  Not just admin, but manager, teacher, ... and many other roles with different permissions check.

```js
const giveAccessTo = user => "Access Granted to " + user;

function authenticate(verify) {
  let array = [];
  for (let i = 0; i < verify; i++) {
    array.push(i);
  }
  return giveAccessTo(person);
}

function letPersonLogin(person, fn) {
  if (person.level === "admin") {
    return fn(person);
  } else if (person.level === "user") {
    return fn(person);
  }
}

// function letAdminLogin(user) {
//   // ++ | Now we tell the function what data to use.
//   // More flexibility.
//   let array = [];
//   for (let i = 0; i < 10000000; i++) {
//     array.push(i);
//   }
//   return giveAccessTo(user);
// }

// function letUserLogin(user) {
//   // ++ | Now we tell the function what data to use.
//   // More flexibility.
//   let array = [];
//   for (let i = 0; i < 10000000; i++) {
//     array.push(i);
//   }
//   return giveAccessTo(user);
// }
```

Exercise:

```JS
// Try.
const multiplyBy = (n, m) => n* m
const multiplyByTwo = (n, fn) => fn(2, n)
const multiplyByTen = (n, fn) => fn(10, n)

// Draft
const multiplyBy = function (n) {
  return function (m) {
    return n * m
  }
}
const multiplyByTwo = multiplyBy(2)
const multiplyByTen = multiplyBy(10)
console.log(multiplyByTwo(5))
console.log(multiplyByTen(7))

// Final Result
const multiplyBy = (n) => (m) => n * m
multiplyBy(4)(6)
// const multiplyByTwo = multiplyBy(2)
// const multiplyByTen = multiplyBy(10)
// console.log(multiplyByTwo(5))
// console.log(multiplyByTen(7))
```
