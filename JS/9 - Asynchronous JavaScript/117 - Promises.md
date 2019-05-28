# 117 - Promises

def: A promess is an object that may produce a single value some time in the future.
---

states of a promise:
---
1. Fullfil
2. Rejected
3. Pending

Callback samples:
---
```js
el.addEventListener("click", submitForm);

// Callback paramid of DOM.
movePlayer(100, 'LEFT', function () {
	movePayer(100, 'RIGHT', function () {
		movePlayer(50, 'UP', function () {})
	})
})
```

Promise sample
---
```js
movePlayer(100, 'LEFT')
	.then(() => movePlayer(100, 'RIGHT'))
	.then(() => movePlayer(50, 'UP'))
```

Let's start.
---

```js
consr promise = new Promise((resolve, reject) => {
	const condition = true;
	if (condition) {
		resolve("SOLVED")
	} else {
		reject("ERROR")
	}
});

promise
	.then(res => res + "!")
	.then(res => console.log(res))) // chaining results.
// => SOLVED !
	.catch() // Catch any errot that the promise may have only for then above him.
	.then()
	.then()

const promise2 = new Promise((resolve, reject) => {
	setTimeout(resolve, 100, "HI");
});

const promise3 = new Promise((resolve, reject) => {
	setTimeout(resolve, 1000, "POOKIE");
});

const promise4 = new Promise((resolve, reject) => {
	setTimeout(resolve, 3000, "It is what you looking for ?");
});

Promise.all([promise, promise2, promise3, promise4])
	.then((values) => {
		console.log(values);
	}); // the response is instante because, they have already be runned !
```

Concret Example
---

```js
const urls = [
	'https://jsonplaceholder.typicode.com/users/',
	'https://jsonplaceholder.typicode.com/posts/',
	'https://jsonplaceholder.typicode.com/albums/',
]

Promise.all(urls.map(url => {
	return fetch(url).then((res) => res.json()
})).then(results => {
	console.log(results[0]);
	console.log(results[1]);
	console.log(results[2]);
}).catch(error => {
	console.log(error);
})
```
