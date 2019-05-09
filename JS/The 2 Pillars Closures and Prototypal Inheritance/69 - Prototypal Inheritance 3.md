# 68 - Prototypal Inheritance 2

```js
const dragron = {
  name: "Tanya",
  fire: true,
  fight() {
    return 5;
  },
  sing() {
    if (this.fire) {
      return `I'm ${this.name} the breather of fire`;
    }
  }
};

let lizard = {
  name: "Kiki",
  fight() {
    return 1;
  }
};

lizard.__proto__ = dragon;

for (let prop in lizard) {
  if (lizard.hasOwnProperty(prop)) {
    console.log(prop); //=> name, fight
  }
  console.log(prop); //=> name, fire, fight and sing
}
```

**NB: To inherit never use `.__proto__ =`. Bad for performance.**

- The advantage: we have property that point to the same place of memory. => hasOwnProperty and haProperty
- o.**proto**.**proto** //=> null // null pointer, pointing to null.
