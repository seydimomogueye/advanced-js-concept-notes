# 60 - Closures and Memory

```js
function heavyDuty(index) {
  const bigArray = new Array(7000).fill(":-)");
  console.log("CREATED");
  return bigArray[index];
}

heavyDuty(688); // => CREATED
heavyDuty(688); // => CREATED
heavyDuty(688); // => CREATED
heavyDuty(688); // => CREATED
heavyDuty(688); // => CREATED
// run 4 times.
```

```js
heavyDuty2 = heavyDuty2();

function heavyDuty2() {
  const bigArray = new Array(7000).fill(":-)");
  console.log("CREATED AGAIN");
  return function(index) {
    return bigArray[index];
  };
}
heavyDuty2()(688); // => CREATED AGAIN
heavyDuty2()(700); // =>
heavyDuty2()(800); // =>
// just run 1 time with closure.
```
