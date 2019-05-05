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
  return true;
}

function letPersonLogin(person, fn) {
  if (person.level === "admin") {
    fn(2000);
  } else if (person.level === "user") {
    fn(10000);
  }
  return giveAccessTo(person);
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
