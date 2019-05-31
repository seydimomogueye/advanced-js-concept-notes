# Big O (Asymthotic Analysis)

## What is Good Code.

1. Readable.
2. Scalable. (Big O)

```js
const nemo = ['nemo'];

function findNemo1(array) {
  for (let i = 0; i < array.length; i++) {
    if (array[i] === 'nemo') {
      console.log('Found NEMO!');
    }
  }
}

findNemo1(nemo);
````

Resources:
- [For loop](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for)


## Big O scalability.

```js
const fish = ['dory', 'bruce', 'marlin', 'nemo'];
const nemo = ['nemo'];
const everyone = ['dory', 'bruce', 'marlin', 'nemo', 'gill', 'bloat', 'nigel', 'squirt', 'darla', 'hank'];
const large = new Array(10).fill('nemo');

function findNemo2(fish) {
  let t0 = performance.now();
  for (let i = 0; i < fish.length; i++) {
    if (fish[i] === 'nemo') {
      console.log('Found NEMO!');
    }
  }
  let t1 = performance.now();
  console.log("Call to find Nemo took " + (t1 - t0) + " milliseconds.");
}

findNemo2(everyone)
```

Who's code is better ?
The time can't be the unit measurement because it depend of machine caracteriscs.
so how to know which code is better ?

Bio O is the language used to know which algorith is the longest to run.

## O(n)
```js
findNemo2(elements) 
// The number of operations increase with the number of elements
// O(n) --> Linear time.
// n == element number.
// number of operations
// /\
// |.    x
// |   x
// | x
// |_ _ _ _ _ _ _ _ _> number of elements

```

## O(1)

```js
function compressFirstBoxe(boxes) {
	console.log(boxes[0]);
}
// How many steps or operation the functions takes ? n, but how many element the function takes,
// it will return one operation. 
// O(1) --> It's a Constant Time 

// number of operations
// /\
// |.    
// |   
// | x x x x
// |_ _ _ _ _ _ _ _ _> number of elements
```

```js
function logFirstTwoBoxes(boxes) {
	console.log(boxes[0]); // O(1)
	console.log(boxes[1]); // O(1)
}
logFirstTwoBoxes(boxes) // O(2)
// number of operations
//   /\
// 3 |    
// 2 | x x x x   
// 1 |
// 0 |_ _ _ _ _ _ _ _ _> number of elements
```

```js
function funChallenge(input) {
  let a = 10; // O(1)
  a = 50 + 3; // O(1)

  for (let i = 0; i < input.length; i++) { // O(n)
    anotherFunction(); // O(n)
    let stranger = true; // O(n)
    a++; // O(n)
  }
  return a; // O(1)
}
// O(3 + 4n) => O(4(1+n))
```

- What is the difference between big oh, big omega and big theta notations?
```
Let 𝑓,𝑔 be two arbitrary functions.

Definition of Big O

𝑓=𝑂(𝑔) if there exists integer 𝑁 and constant 𝐶>0, such that 𝑓(𝑛)<𝐶𝑔(𝑛) for 𝑛>𝑁.

Example:

𝑓(𝑛)=𝑛2−𝑛

𝑔(𝑛)=𝑛2

We claim that 𝑓=𝑂(𝑔). Then, we pick 𝐶=1 and 𝑁=1.Therefore, for n >1,we have 𝑓(𝑛)=𝑛2−𝑛<𝑛2=𝑔(𝑛).

Definition of Big Ω

𝑓=Ω(𝑔) if 𝑔=𝑂(𝑓)

Definition of Big 𝜃

𝑓=𝜃(𝑔) if 𝑓=𝑂(𝑔) and 𝑓=Ω(𝑔)
```

```js
function anotherFunChallenge(input) {
  let a = 5; // O(1)
  let b = 10; // O(1)
  let c = 50; // O(1)
  for (let i = 0; i < input; i++) { // O(n)
    let x = i + 1; // O(n)
    let y = i + 2; // O(n)
    let z = i + 3; // O(n)

  }
  for (let j = 0; j < input; j++) { // O(n)
    let p = j * 2; // O(n)
    let q = j * 2; // O(n)
  }
  let whoAmI = "I don't know"; // O(1)
} 
// O(4 + (n + n + n + n) + (n + n + n))
// O(4 + 4n + 3n)
// O(4 + 7n)
```

## Simplify Big O.

In interview, we have to give answer from Big-O complexity charts. 

ex: O(4 + 7n) ==> O(n)
ex: O(4(1+n)) ==> O(n)

so, we have to follow 4 rules:
Rule 1: Worst case. (Big O always talk about this case.)

Rule 2: Remove constans
```js
function printFirstItemThenFirstHalfThenSayHi100Times(items) {
    console.log(items[0]); // O(1)

    var middleIndex = Math.floor(items.length / 2); // O(1)
    var index = 0; // O(1)

    while (index < middleIndex) { // O(n/2)
        console.log(items[index]);
        index++;
    }

    for (var i = 0; i < 100; i++) { // O(n) where n = 100 => 100
        console.log('hi');
    }
}
// BIG O = O(2 + n/2 + 100)
// => BIG O = O(n/2 + 102)  remember we have to express big o with something in thc cheat-cheet
// BIG O = O(n/2 + 1). // replace 102 to 1
// BIG O = O(n/2 + 1). // We only interested by when it's scales, getting larger and larger, so we don't care about 100 or 1 for sample if n = 1 million it's neglectable to add 100. Divided by two has a decreased significant effect => O(n + 1), and because 1 is insignificant => O(n)


function compressBoxesTwices(boxes) {
	boxes.forEach(function(boxes) {
		console.log(boxes)
	});

	boxes.forEach(function(boxes) {
		console.log(boxes)
	})
}
// number of operations
//   /\	   x
// 3 |	 x 
// 2 | x  
// 1 | 
// 0 |_ _ _ _ _ _ _ _ _> number of elements
//=> O(2n) => in interview we drop the constant => O(n)
```

Rule 3: Different terms for inputs
```js
// 1. function compressBoxesTwice(boxes) {
	boxes.forEach(function(boxes, boxes2) { // => depend on boxes length
		console.log(boxes)
	});

	boxes2.forEach(function(boxes) { // => depend on boxes2 length
		console.log(boxes)
	})
}
// 1. => O(n)
// 2. => O(n + m)
```

## O(n^2)
```js
const boxes = ['a', 'b', 'c', 'd', 'e'];
function logAllPairsOfArray(array) {
  for (let i = 0; i < array.length; i++) {
    for (let j = 0; j < array.length; j++) {
      console.log(array[i], array[j])
    }
  }
}

logAllPairsOfArray(boxes)
// => O(n * n) => O(n^2) - Quadratic time.
// number of operations
//   /\
// 9 |
// 8 |      x(9, 3)
// 7 |
// 6 |
// 5 |
// 4 |  x(4, 2)
// 3 |	  
// 2 |  
// 1 |   
// 0 |_ _ _ _ _ _ _ _ _> number of elements

/ 1. function compressBoxesTwice(boxes) {
	boxes.forEach(function(boxes, boxes2) { // => depend on boxes length
		console.log(boxes)
    boxes2.forEach(function(boxes) { // => depend on boxes2 length
		console.log(boxes)
	})
	});
}
// 1. => O(n)
// 2. => O(n * m)
```

Rule 4: Drop Non Dominant.
