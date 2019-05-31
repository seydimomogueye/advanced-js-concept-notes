# 120 - ES9 (ES2018) - Async

Finally
---

```js
Promise.all(urls.map(url => {
	return fetch(url).then((res) => res.json()
})).then(results => {
	console.log(results[0]);
	console.log(results[1]);
	console.log(results[2]);
}).catch(error => {
	console.log(error);
}).finally(() => {
  console.log("Finally")
})
```

For await of
---

```js
const urls = [
	'https://jsonplaceholder.typicode.com/users/',
	'https://jsonplaceholder.typicode.com/posts/',
	'https://jsonplaceholder.typicode.com/albums/',
]
const getData = async function () {
  const [users, posts, albums] = await Promise.all(urls.map(url => {
    return fetch(url).then((res) => res.json()
  }))

  console.log(users);
	console.log(posts);
	console.log(albums);
}

const getDataV2 = async function (urls) {
  const arrayOfPromises = urls.map(url => fetch(url));
  for await (let request of arrayOfPromises) {
    const data = await request.json();
    console.log(data);
  }
}

```