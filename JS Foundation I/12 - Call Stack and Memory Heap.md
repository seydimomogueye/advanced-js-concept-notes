# Call Stack and Memory Heap

## Memory Heaps

```js
const num = 610; // allocate memory for number variable. [in memory heap].
const string = "some string"; // allocate memory for a string.
const human = {
  name: "Momo",
  last_name: "Gueye"
}; // allocate memory for the object and his value.
```

## CAll Stack

How to call stack handle the example bellow ?

```js
function subsTwo(n) {
  return n - 2;
} // 1. Allocate memory to this function.

function calculate() {
  const sumTotal = 4 + 5;
  return subsTwo(sumTotal);
} // 2. Allocate memory to this function.

calculate(); // running the call stack in FILO mode.
```

### EXECUTION

```
Step 1:
// add -> Global
// read -> line 1 of Global
...
// read -> line n of Global

// add -> calculate
// read -> line 1 of calculate
...
// read -> line n of calculate

// add -> subsTwo
// read -> line 1 of subsTwo
...
// read -> line n of subsTwo

result: FIFO
|-------------|
| subsTwo()   |
|-------------|
| calculate() |
|-------------|
| Global      |
|-------------|

Step 2:
// pop: subsTwo()
// exe: calculate()
// exe: Global
```

NB

- Simple var can ususally be store on the stack and the objects in the memory heaps
- Stack overflow

# Garbage collection.

- JS is a garbage collected language, that's means when JS allocate memory, will cleaned up for us after execution.
- It freeze memory on the heaps to prevent memory leaks.
- User mark and sweep algorithm.

# Memory leaks.

How it happen ?

1. Infinite loops.

```JS
// Ex:
var array = [];
for (let i = 5; i > 1; i++) { // Infinite loop.
  array.push(i-1)
} //
```

2. Global variables.
3. Event listeners.

```JS
// Ex:
var el = document.getElementById("button");
add.eventListener('click', onClick);
// remove them when you don't need them.
```

4. SetInterval function.

```JS
// Ex:
setInterval(() => {
  // ref object here will never be handled by garbage collection.
}, 9)
```

# SINGLE THREADED.

JS is synchronous. One thing at the time.
