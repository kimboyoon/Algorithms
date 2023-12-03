# What is good code?

## Readable

## Scalable 확장 가능한


### O(n)

```js
const nemo = ['nemo'];

function findNemo (array) {
  for (let i = 0; i < array.length; i++) {
    if (array[i] === 'nemo') {
      console.log('Found NEMO!')
    }
  }
  let t1 = performance.now()
}

findNemo(nemo)
```

- linear 선형적이다

```js
// ES6
const allBoxes = boxes => {
    boxes.forEach(box => console.log(box))
}
```

### O(1)

- constant time
- 평면

```js
const firstBox = boxes => {
    console.log(boxes[0])
}
```


#### example

```js
// ex1

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

BIG O (3 + 4n) => BIG O (n)

// ex2

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

BIG O (n)
```

### Rules

#### 1. Worst Case

- 최악의 상황을 생각하자


#### 2. Remove constants

- 상수를 무시하자

#### 3. Different terms for inputs

- 중첩된 반복문

```js
// Log all pairs of array

const boxes = ['a','b','c','d','e']

function logAllPairsOfBoxes (array) {
  for (let i = 0; i < array.length; i++) {
    for (let j = 0; j < array.length; j++) {
      console.log(array[i], array[j])
    }
  }
}

logAllPairsOfBoxes(boxes)

BIG O (n^2)
```

#### 4. Drop Non Dominants

- 작은 수를 제외한다

