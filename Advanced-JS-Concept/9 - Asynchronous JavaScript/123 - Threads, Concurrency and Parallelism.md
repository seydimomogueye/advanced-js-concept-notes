# 123 - Threads, Concurrency and Parallelism

- JS

Web workon is a js program running on a differente thread, alongside of our main thread.
They don't have access to browser APIs and have some ablilities (location, setTimeout, ...)

- Node:

```js
const {spawn} = require("child_process");
```