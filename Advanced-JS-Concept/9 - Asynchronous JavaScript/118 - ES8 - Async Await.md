# 118 - ES8 - Async Await

The benefit it is make the code more readable.

```js
// Basic promise
movePlayer(100, 'LEFT')
	.then(() => movePlayer(100, 'RIGHT'))
	.then(() => movePlayer(100, 'UP'))

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

// Async await
async function startPlayer() {
  await movePlayer(100, "LEFT");
  await movePlayer(100, "RIGHT");
  await movePlayer(100, "TOP");
}

const getData = async function () {
  const [users, posts, albums] = await Promise.all(urls.map(url => {
    return fetch(url).then((res) => res.json()
  }))

  console.log(users);
	console.log(posts);
	console.log(albums);
}

```