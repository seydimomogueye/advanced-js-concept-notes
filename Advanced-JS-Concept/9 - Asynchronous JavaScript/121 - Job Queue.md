# 121 - Job Queue

Callback Queue: Task Queue
```js
setTimeout(() => {console.log("1. TEST 1")}, 1)
setTimeout(() => {console.log("2. TEST 2")}, 2)
```

Job Queue: Microtask Queue 

smaller and has a more higher priority than Task queue,
it's mean the event loop start looking Job queue before callback queue.

```js
Promise.resolve("hi").then((data) => {console.log("3. " + data)})
```

```js
console.log("4)
```

Result:
```js
// => 4, 3. Hi, 1. TEST 1, 2. TEST 
```

