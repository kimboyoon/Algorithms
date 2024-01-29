# How to solve problems?

1. Analytic skills

2. Coding skills

3. Technical skills

4. Communication skills


# Step by step

1. Write down the key points at the top.
    - Sorted arrays, etc..

2. Make sure you double check.
    - inputs, outputs,

3. What is the most important value of the problem.
    - Time complexity or Space complexity

4. Don't be annoying and too many questions.

5. First thing that comes into mind it shows that able to think well. Just speak about it.
    - for exmaple, Big O

6. Tell me this approach is not the best.

```js
// for example,
// const array1 = ['a', 'b', 'c', 'x']
// const array2 = ['y', 'z', 'i', ]
// return false
// ------------
// const array1 = ['a', 'b', 'c', 'x']
// const array2 = ['x', 'y', 'z']
// return true

// 2 parameters, arrays, no size limit
// return true or false
// 접근법을 먼저 설명
// 배열의 개수가 몇 개인지? 예를 들어 5개 이하라면, BIGO나 공간 시간 복잡도 고려할 필요x

function containsCommonItems (arr1, arr2) {
    for (let i = 0; i < arr1.length; i++) {
        for (let j = 0; j < arr2.length; j++) {
            if (arr1[i] === arr2[j]) {
                return true
            }
        }
    }
    return false
}

// O(a*b)
```

7. find the better solution.
8. before coding, write down the step you're going to do.

```js
// array1 ==> obj {
// a: true,
// b: true,
// c: true,
// x: true
// }

// array2[index] === obj.properties

function containCommonItem2 (arr1, arr2) {
    // separate the loops
    // O(n^2) 에서 O(a+b) 로 시간 복잡도를 줄일 수 있다

    // 1) use first array and create object where properties === items in the array
    let map = {};
    for (let i = 0; i < arr1.length; i++) {
        if (!map[i]) {
            const item = arr1[i];
            map[item] = true;
        }
    }

    console.log(map) // map = { a: true, b: true, c: true, x: true}

    // 2) loop second array and check if item in second array exists on created object.
    for (let j = 0; j < arr2.length; j++) {
        if (map[arr2[j]]) {
            return true;
        }
    }
    return false;
}

// O(a+b) Time complexity
```

15. JS를 이용한 가독성을 높히려면? Readable

```js
function containCommonItem3 (arr1, arr2) {
    return arr1.some(item => arr2.includes(item))
}
```


