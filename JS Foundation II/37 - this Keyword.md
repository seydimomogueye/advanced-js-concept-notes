# this Keyword

this is a object that the function is a property of.

```js
someObj.someFunction(this);
// someObj ==> this
```

```js
function a() {
  console.log(this); // => Windows object.
} <==> window.a() // window => this
```

```js
function b() {
  "use strict";
  console.log(this); // => undefined.
}
```

# Why `this` object ?

1. Gives methods access to their object.
2. Execute the same code for the multiple objects.

```js
function importantPerson() {
  console.log(this.name);
}
const name = "Sunny";
const o1 = {
  name: "Cassy",
  importantPerson
};
const o2 = {
  name: "Jacob",
  importantPerson
};
//
importantPerson(); // => sunny because window.importantPerson();
```

**this => Who's calling me ?**
