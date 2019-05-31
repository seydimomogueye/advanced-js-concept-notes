# 47 - Pass By Value vs Pass By Reference

- primitives variables are passed by value.
- objects are passed by reference.

# examples:

## example 01:

```js
var a = 5; // a now has address on where this primitive value 5 sits in memory
var b = 10; // a now has address on where this primitive value 10 sits in memory
```

## example 02:

```js
var a = 5;
var b = a;

b++;
console.log(a); // 5
console.log(b); // 6 because of pass by value
```

js engine copying the primituve type value 5 and paste it to b.

pass by value: Copy the value, write that value somewhere else in the memory.

## Object: Pass by reference.

```js
let obj_01 = { name: "Yao", password: "123" };
let obj_02 = obj_01;
obj_02.password = "anotherpasswd";

console.log(obj_01); // { name: "Yao", password: "anotherpasswd" };
console.log(obj_02); // { name: "Yao", password: "anotherpasswd" };
```

- we not copy the value, we simply said this is where the object is in memory.
- obj_01 and obj_02 are somewhere in memory pointing to a place that contain the information { name: "Yao", password: "anotherpasswd" };
- assignment => obj_02 = {MEM_ADDR_TO_OBJ1}
- to avoid things like that:

```JS
let a = [1, 2, 4]
let b = [].concat(a)
// or
b = Object.assign([1], a)
// or
b = { ...a, 1 }
```

- what if we have object in object ?

```js
let o = {a: 1, b: 2 c: { deep: 'try to copy me.'}}
let o1 = Object.assign({}, o)
let o2 = { ...o }
```

if:

```js
obj.c = 5;
console.log(o); // => {a: 1, b: 2 c: 5}
console.log(o1); // => {a: 1, b: 2 c: { deep: 'try to copy me.'}}
console.log(o2); // => {a: 1, b: 2 c: { deep: 'try to copy me.'}}
```

but:

```js
obj.c.deep = "hahaha";
console.log(o); // => {a: 1, b: 2 c: { deep: 'hahaha'}}
console.log(o1); // => {a: 1, b: 2 c: { deep: 'hahaha'}}
console.log(o2); // => {a: 1, b: 2 c: { deep: 'hahaha'}}
```

how to deal with that ?

```js
let superClone = JSON.parse(JSON.stringify(o)); // if the object is big, performance issue will happen !
obj.c.deep = "hahaha";
console.log(o); // => {a: 1, b: 2 c: { deep: 'hahaha'}}
console.log(o1); // => {a: 1, b: 2 c: { deep: 'hahaha'}}
console.log(o2); // => {a: 1, b: 2 c: { deep: 'hahaha'}}
console.log(superClone); // => {a: 1, b: 2 c: { deep: 'try to copy me.'}}
```
