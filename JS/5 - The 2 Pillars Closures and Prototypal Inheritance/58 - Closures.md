# Closures

- Function are 1st classes citizen
- Lexical scope: Before we run the code, the JS engine knows whiche variable is accessible based on where the code is written,
- Closure is a combination of those 2 things.

```js
function a() {
  // hof
  let grandpa = "grandpa"; // 1. after const one = a(); just b() remaining, and a() get pop of the stack
  return function b() {
    // hof
    let grandpa = "father";
    let r = 342432432; // 3. not used by c, GC will remove it.
    return function c() {
      // normal func
      let son = "son";
      return `${grandpa} ${father} ${son}`; // 2. why we still have access to grandpa though
    };
  };
}
// when a()
```

- run a, a get push into the stack, and create variable env, grandpa, link to the global scope. When this get executed and removed everything gone but grandpa still remain because he goes to the boxe of closure in the memory heap.
- The garbage collector avoid to remove variable in closure box.
- closures called lexical scoping. where function is written and which variable ca he access ?
- where we wrie the function is important not where we call the function.

```js
function boo(string) {
  return function(name) {
    return function(name2) {
      console.log(`${string} ${name} ${name2}`);
    };
  };
}

const boo = string => name => name2 =>
  console.log(`${string} ${name} ${name2}`);

boo("hi"); // => Function
boo("hi")("Tim"); // => Function
boo("hi")("Tim")("becca"); // => Hi Tim becca

// Why getting exiting for this ? ex:
const booString = boo("hi");
// wait 5 years
const booStringName = booString("Tim"); // still able to remember string var value, because params are treated like local variables they are stored in var env.
```
