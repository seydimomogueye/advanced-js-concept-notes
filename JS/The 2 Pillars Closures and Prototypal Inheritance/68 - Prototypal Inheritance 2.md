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
```

- Kiki can borrow a method to dragon like:

```js
const singLizard = dragon.sing.bind(lizard);
```

-- Or we can make full inheritance

```js
lizard.__proto__ = dragon;
dragon.isPrototypeOf(lizard);
```
