# 116 - How JavaScript Works

What is a program ?

- Allocate memory
- parse and execute scripts (Read / Run commands)

Javascript Engine

- v8: Read JS written and change it to machine executing instructions for the browser
- part 1: Memory heap
  - Global variables are bad because memry leaks happen if we forget to clean up.

- part 2: Call stack
  - single thread => it can have only one call stack.

JavaScript is single threaded language that can be not blocking.

```js
// 1. CALL STACK
// 2. WEB API
// 3. CALL BACK QUEUE
// 4. EVENT LOOP
// 5. EVENT LOOP PUT CALLBACK IN CALL STACK. 
```

```js
// How the code bellow runs ?
element.addEventListener('click', () => {
  console.log('click') ?
});

// 1. Add listener
// 2. Put function to callback queue
// 3. when event happen `click`, put call back into the stack.
```