# 82 - More Constructor Functions

- Constructor function

```js
function Elf(name, weapon) {
  console.log(this); // => {}

  this.name = name;
  this.weapon = weapon;

  console.log(this); // => { name: [name], weapon: [weapon] }
}

Elf.prototype.attack = function() {
  return "attack with " + this.weapon;
};

const peter = new Elf("Peter", "stones");
peter.attack();
// peter.__proto__ points to Elf.prototype

const sam = new Elf("Sam", "fire");
sam.attack();
```
