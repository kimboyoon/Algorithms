# Array 배열

## push, pop, unshift, splice

```js
const strings = ['a', 'b', 'c', 'd']
// 4*4 = 16 bytes of the storage 

// push 마지막에 추가
strings.push('e') // ['a','b','c','d','e']
// O(1)

// pop 마지막꺼 하나 제거
strings.pop() // ['a','b','c']
// O(1)

// unshift 맨 앞에 추가
strings.unshift('x') // ['x','a','b','c','d']
// O(n) 원래 배정되어 있던 인덱스를 다시 새로 배정해야 함 

// splice 배열 중간에서 추가, 삭제
strings.splice(2, 0, 'alien') // 인덱스 2에서 0개를 삭제하고 alien을 추가한다
// ['a','b','alien','c','d']
// O(n)
```

### Static vs Dynamic array

- JS는 Dynamic array로 크기를 미리 알 필요가 없다. 컴퓨터가 메모리를 할당해주기 때문
- 그러나 C++과 같은 Static 은 미리 크기를 알아야 한다. 할당해주기 위해
- 그래서 속도는 더 빠름.

### 문자열 뒤집기

```js
function reverse (str) {
    // check input
    if (!str || str.length < 2 || typeof str !== 'string') {
        // undefined or one letter
        return 'no string'
    }

    const backwards = [];
    const totalItems = str.length - 1

    for (let i = totalItems; i >= 0; i--) {
        backwards.push(str[i])
    }

    return backwards.join('')
}

function reverse2 (str) {
    return str.split('').reverse().join('')
}

const reverse3 => str => str.split('').reverse().join('' )

const reverse4 => str => [...str].reverse().join('' )
```

### merge array

```js
function mergeSortedArray (array1, array2) {
    const mergedArray = []
    let array1Item = array1[0]
    let array2Item = array2[0]
    let i = 1
    let j = 1
    
    // check input
    if (array1.length === 0) {
        return array2
    }
    if (array2.length === 0) {
        return array1
    }

    while (array1Item || array2Item) {
        if (!array2Item || array1Item < array2Item) {
            mergedArray.push(array1Item)
            array1Item = array1[i]
            i++
        } else {
            mergedArray.push(array2Item)
            array2Item = array2[i]
            j++
        }
    }

    return mergedArray
}
```

## pros and cons

- pros
    - Fast lookups
    - Fast push/pop
    - Ordered

- cons
    - Slow inserts
    - Slow deletes
    - Fixed sizes (if using static array)