# 61 - Closures and Encapsulation

```js
const makeNuclearButton = () => {
  let timeWithoutDestruction = 0;
  const passTime = () => timeWithoutDestruction++;
  const totalPeaceTime = () => timeWithoutDestruction;
  const launch = () => {
    timeWithoutDestruction = -1;
    return "BOOM";
  };
  setInterval(passTime, 1000);

  return {
    launch,
    totalPeaceTime
  };
};

const ohno = makeNuclearButton();
ohno.totalPeaceTime();
ohno.launch();
```

- We don't wanna access to launch function, let's encapsulate it.

```js
const makeNuclearButton = () => {
  let timeWithoutDestruction = 0;
  const passTime = () => timeWithoutDestruction++;
  const totalPeaceTime = () => timeWithoutDestruction;
  const launch = () => {
    timeWithoutDestruction = -1;
    return "BOOM";
  };
  setInterval(passTime, 1000);

  return {
    totalPeaceTime
  };
};

const ohno = makeNuclearButton();
ohno.totalPeaceTime();
ohno.launch(); // => error
```
