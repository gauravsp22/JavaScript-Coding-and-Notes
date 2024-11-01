For dedicated programmers looking to learn javascript.
All the the core concepts of JavaScript can be found here 
with coding challenges to solidify your knowledge.

Best of luck on your coding journey ; ) 

#### improvement contributions are appreciated.
##### I am sharing here some important questions below for practice:  
---


### 1. Merge Two Objects in JavaScript

Write a function that takes two objects and returns a new object with combined key-value pairs. If both objects contain the same key, the value from the second object should overwrite the value in the first object.

#### Example

Given two objects:

```javascript
const obj1 = { a: 1, b: 2, c: 3 };
const obj2 = { b: 2, c: 4, d: 5 };
```

The merged output should be:

```javascript
{ a: 1, b: 2, c: 4, d: 5 }
```

#### Solution

##### Way 1: Using a `for...in` Loop

```javascript
function mergeObjects(obj1, obj2) {
    for (let key in obj2) {
        obj1[key] = obj2[key];
    }
    return obj1;
}

const mergedResult1 = mergeObjects(obj1, obj2);
console.log(mergedResult1); // Output: { a: 1, b: 2, c: 4, d: 5 }
```

##### Way 2: Using the Spread Operator

```javascript
function mergeObjects1(obj1, obj2) {
    return { ...obj1, ...obj2 };
}

const mergedResult2 = mergeObjects1(obj1, obj2);
console.log(mergedResult2); // Output: { a: 1, b: 2, c: 4, d: 5 }
```



### 2. Transform Array of Objects in JavaScript

Convert an array of objects, where each object contains an `id` and `name` property, into an object where each key is an `id` from the original array, and the corresponding value is an object with the `name` property.

#### Example

**Input**

```javascript
let arr1 = [{ id: 1, name: 'A' }, { id: 2, name: 'B' }];
```

**Output**

```javascript
{ 1: { name: 'A' }, 2: { name: 'B' } }
```

#### Solution

##### Way 1: Using a `for...of` Loop

```javascript
function transformArrayOfObject(arr) {
    let obj = {};
    for (const element of arr) {
        obj[element.id] = { name: element.name };
    }
    return obj;
}

console.log(transformArrayOfObject(arr1)); 
// Output: { 1: { name: 'A' }, 2: { name: 'B' } }
```

##### Way 2: Using `Array.prototype.reduce`

```javascript
function transformArrayOfObject1(arr) {
    return arr.reduce((acc, item) => {
        acc[item.id] = { name: item.name };
        return acc;
    }, {});
}

console.log(transformArrayOfObject1(arr1)); 
// Output: { 1: { name: 'A' }, 2: { name: 'B' }
```
