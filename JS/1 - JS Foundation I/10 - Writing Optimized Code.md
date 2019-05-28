# Writing Optimized Code

Writing efficient code to help the profiler and compiler to make better optimization.

Be careful with:

- eval
- argument
- for in
- with
- delete
- +Hidden classes.
- +Inline Caching.

## Inline Caching

```js
function findUser(user) {
  return `found ${user.first_name} ${user.first_name}`;
}

const userData = {
  first_name: "John",
  last_name: "Doe"
};
findUser(userData); // inline caching: instead of looking the userData var all the time, it will cache the resuklt and save "John Doe"
```

## Hidden classes

```js
function Anima(x, y) {
  this.x = x;
  this.y = y;
}

const o1 = new Animal(1, 2);
const o2 = new Animal(3, 4);
// Here is OK !
// cmp: okay ! o1 and o2 have the same hidden class, i will handle that ! // => FAST

o1.a = 30;
o1.b = 130;
o2.b = 100;
o2.a = 30;

// cmp: different order ! humm ... not same hidden class, it's two separate things. // => SLOW
// TODO: assigne a and b property in constructor. and add it to the same order.
```

**delete issue**

```js
delete o1.x; // cmp: hum.. object x not in o1, it 's in a separate class. => SLOW
```

Write predictible code to help human and compiler.
