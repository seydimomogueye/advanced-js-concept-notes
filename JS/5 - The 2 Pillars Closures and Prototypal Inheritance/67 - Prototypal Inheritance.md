# 67 - Prototypal Inheritance

- Array inherit of Object.
- Function inherit of Object.

```js
const array = [];
function a() {}
const o = {};

(array.__proto__.__proto__ === a.__proto__.__proto__) === o.__proto__;
```
