# Chapter 6 Arrays in Javascript

Array are the ordered list of multiple values used to store multiple related data at place. Each value, known as **element**, is assigned at numeric position in the array called its **index**. Index starts at 0, so the first element is at 0 position, second at 1, and so on.

In javaScript array can hold any type of data, such as **number**, **strings**, **symbols**, **objects** or even other **arrays** which make it very flexible to use.

## Creating Array

There are two ways to create **Array** in javascript.

### 1. Using Literals

Creating an array using array literals invloves using square brackets `[]` to define and initialize array.

```javascript
const array = [1, 2, 3, 4, 5];
```

### 2. Using Array Constructor Function (with `new` keyword)

The **Array constructor** refers to a method of creating a array by invoking `Array()` contructor function with `new` keyword.

```javascript
const array = new Array(1, 2, 3, 4, 5);
```

Example

```javascript
// using literals
const arrayWithLiterals = [1, 2, 3, 4, 5];
console.log(arrayWithLiterals);

// using constructor
const arrayWithConstructor = new Array(1, 2, 3, 4, 5);
console.log(arrayWithConstructor);
```

Output

```text
[ 1, 2, 3, 4, 5 ]
[ 1, 2, 3, 4, 5 ]
```

## Array Operations

### Accessing Array Elements

We can access elements of arrays by their indexes.

#### Get first elemet of array

Example

```javascript
const array = [1, 2, 3, 4, 5];
console.log(array[0]);
```

Output

```text
1
```

#### Get last element of array

Example

```javascript
const array = [1, 2, 3, 4, 5];
console.log(array[array.length - 1]);
```

Output

```text
5
```

#### Access random element of array

Example

```javascript
const array = [1, 2, 3, 4, 5];
console.log(array[2]);
console.log(array[1]);
console.log(array[4]);
```

Output

```text
3
2
5
```

#### Get length of array

Example

```javascript
const arr = [1, 2, 3, 4, 5];
console.log(arr.length);
```

### Modifying Array Elements

We can also add and modify array element by their indexes and methods.

#### Modify array element by index

Example

```javascript
const arr = [1, 2, 3, 4, 5];
arr[0] = 10; // modify value of 0 index to 10
console.log(arr);
```

Output

```text
[ 10, 2, 3, 4, 5 ]
```

#### Adding element to array

There are several methods available to add elements to array.

- `pop()`
- `unshift()`:

#### push()

Add new element to the end of the array.

Example

```javascript
const arr = [1, 2, 3, 4, 5];
console.log(arr);
arr.push(10);
console.log(arr);
```

Output

```text
[ 1, 2, 3, 4, 5 ]
[ 1, 2, 3, 4, 5, 10 ]
```

#### unshift()

Add new element to the starting of the array.

Example

```javascript
const arr = [1, 2, 3, 4, 5];
console.log(arr);
arr.unshift(10);
console.log(arr);
```

Output

```text
[ 1, 2, 3, 4, 5, 10 ]
[ 10, 1, 2, 3, 4, 5 ]
```

### Removing element from array

There are several methods available to remove elements from array.

- `pop()`
- `shift()`
- `splice()`

#### pop()

Remove last element from the end of the array.

Example

```javascript
const arr = [1, 2, 3, 4, 5];
console.log(arr);
arr.pop();
console.log(arr);
```

Output

```text
[ 1, 2, 3, 4, 5 ]
[ 1, 2, 3, 4 ]
```

#### shift()

Remove first element from the stating of the array.

Example

```javascript
const arr = [1, 2, 3, 4, 5];
console.log(arr);
arr.shift();
console.log(arr);
```

Output

```text
[ 1, 2, 3, 4, 5 ]
[ 2, 3, 4, 5 ]
```

#### splice()

Remove or repalce elements to a specific range from the array and **return** new array. It takes two arguements **start**(index) and **deleteCount**(range).

Example

```javascript
const arr = [1, 2, 3, 4, 5];
console.log(arr);
const newArr = arr.splice(1, 3); // return new array
console.log(newArr);
```

Output

```text
[ 1, 2, 3, 4, 5 ]
[ 2, 3, 4 ]
```

### Array Static Methods

Array static methods are directly not accessible to instance of array, instead they are called directly on `Array` class.

There are several array static methods available in JavaScript.

- `Array.from()`
- `Array.fromAsync()`
- `Array.isArray()`
- `Array.to()`

#### Array.from()

`Array.from()` creates and **return** new, shallow-copy Array instance from **iterables** and **array-like** objects.

Syntax

```javascript
Array.from(iterables, mapFn);
```

- **Parameters**
  - **items**: An iterable or array-like object to convert to an array.
  - **mapFn(optional)**: A function to call on every element of the array.

Example

```javascript
const ans = Array.from("javascript");
console.log(ans);

const newAns = Array.from([1, 2, 3, 4], (x) => x + x);
console.log(newAns);
```

Output

```text
[ 'j', 'a', 'v', 'a', 's', 'c', 'r', 'i', 'p', 't' ]
[ 2, 4, 6, 8 ]
```

#### Array.fromAsync()

`Array.fromAsync()` method creates and **return** a new, shallow-copy Array instance from **async-iterables**, **iterables** and **array-like** objects.

Syntax

```javascript
Array.fromAsync(items, mapFn);
```

- **Parameters**
  - **items**: An iterable or array-like object to convert to an array.
  - **mapFn(optional)**: A function to call on every element of the array.

Example

```javascript
const asyncIterable = (async function* () {
  for (let i = 0; i < 5; i++) {
    await new Promise((resolve) => setTimeout(resolve, 10 * i));
    yield i;
  }
})();

Array.fromAsync(asyncIterable).then((result) => console.log(result));
```

Output

```text
[ 0, 1, 2, 3, 4 ]
```

#### Array.isArray()

`Array.isArray()` method **return** `boolean` value. `true` if passed arguement is **Array** either `false`.

Syntax

```javascript
Array.isArray(value);
```

- **Parameters**
  - **value**: The value to be checked.

Example

```javascript
console.log(Array.isArray([1, 2, 3, 4])); // array value
console.log(Array.isArray(null)); // not array value
```

Output

```text
true
false
```

#### Array.of()

`Array.of()` method creates and **return** a new Array instance from a variable number of arguments, regardless of number or type of the arguments.

Syntax

```javascript
Array.of(elements);
```

- **Parameters**
  - **elements**: Elements used to create the array.

Example

```javascript
const newArr = Array.of(1, "javascript", true, undefined);
console.log(newArr);
```

Output

```text
[ 1, 'javascript', true, undefined ]
```

### Array Instance Methods

Array instance methods are directly accessible to instance of array.

There are several array instance methods available in JavaScript but are going to discuss only most useful.

- `at()`
- `concat()`
- `entries()`
- `every()`
- `fill()`
- `filter()`
- `find()`
- `findIndex()`
- `findLast()`
- `findLastIndex()`
- `flat()`
- `flatMap()`
- `forEach()`
- `map()`
- `includes()`
- `join()`
- `keys()`
- `reduce()`
- `reverse()`
- `slice()`
- `sort()`
- `toString()`
- `values()`
- `with()`

#### at()

`at()` methods accept a integer value argument and **return** the item at that index, allowing for positive and negative integers. Negative integers count back from the last item in the array.

Syntax

```javascript
at(index);
```

- **Parameters**
  - **index**: Zero-based index of array element.

Example

```javascript
const programmingLaguages = ["JavaScript", "Python", "Java", "C++", "Ruby"];
console.log(programmingLaguages.at(3));
```

Output

```text
C++
```

#### concat()

`concat()` method concatinate two or more arrays and **return** new array.

Syntax

```javascript
concat(items);
```

- **Parameters**
  - **items**: Arrays or values to concatinate into new array.

Example

```javascript
const array1 = ["a", "b", "c"];
const array2 = ["d", "e", "f"];
const array3 = array1.concat(array2);
console.log(array3);
```

Output

```text
[ 'a', 'b', 'c', 'd', 'e', 'f' ]
```

#### entries()

`entries()` method **return** a new **array iterator** object that contains `key`/`value` pair for each index in an array.

Syntax

```javascript
entries();
```

- **Parameters**
  - **none**

Example

```javascript
const array = ["a", "b", "c"];
const iterable = array.entries();
console.log(iterable.next().value);
console.log(iterable.next().value);
```

Output

```text
[ 0, 'a' ]
[ 1, 'b' ]
```

#### every()

`every()` method **return** `false` if it finds a element in the array that does not stisfy the provided testing. Otherwise **return** `true`.

Syntax

```javascript
every(callbackFn);
```

- **Parameters**
  - **callbackFn**: A function to execute for each element in the array. The function is called with the following arguments:
    - **element**: The current element being processed in the array.
    - **index**: The index of the current element being processed in the array.

    - **array**: The array every() was called upon.

Example

```javascript
const array = [1, 30, 39, 29, 10, 13];
const res = array.every((currentValue) => {
  return currentValue < 40;
});
console.log(res);
```

Output

```text
true
```

#### fill()

`fill()` method changes all the elements within a range of indexes in an array to static value and **return** modified array.

Syntax

```javascript
fill(value, start, end);
```

- **Parameters**
  - **value**: Value to fill in array.
  - **start**: Zero-based index at which to start filling.
  - **end**: Zero-based index at which to end filling.

Example

```javascript
const array = [1, 2, 3, 4, 5];
const fillArray = array.fill(0, 2, 4);
console.log(fillArray);
```

Output

```text
[ 1, 2, 0, 0, 5 ]
```

#### filter()

`filter()` method creates a **shallow copy** of a portion of a given array, filtered down to just the elements from the given array that pass the test implemented by the provided function.

Syntax

```javascript
filter(callbackFn);
```

- **Parameters**
  - **callbackFn**: A function to execute for each element in array The function is called with the follwing arguments:
    - **element**: The current element being processed in the array.
    - **index**: The index of the current element being processed in the array.
    - **array**: The array filter() was called upon.

Example

```javascript
const values = [10, 2, 45, 29, 20, 34, 54, 13];
const result = values.filter((val) => {
  if(val % === 0) return val;
});
console.log(result)
```

Output

```text
[ 10, 2, 20, 34, 54 ]
```

#### find()

`find()` method return first element from the array that satisfies the provided testing. Return `undefined` if no value satisfy the test.

Syntax

```javascript
find(callbackFn);
```

- **Parameters**
  - **callbackFn**: A function to execute for each element in array The function is called with the follwing arguments:
    - **element**: The current element being processed in the array.
    - **index**: The index of the current element being processed in the array.
    - **array**: The array filter() was called upon.

Example

```javascript
const array = [5, 12, 8, 130, 44];
const found = array.find((element) => {
  return element > 10;
});
console.log(found);
```

Output

```text
12
```

#### findIndex()

`findIndex()` method return first element index from the array that satisfies the provided testing. Return -1 if no value satisfy the test.

Syntax

```javascript
findIndex(callbackFn);
```

- **Parameters**
  - **callbackFn**: A function to execute for each element in array The function is called with the follwing arguments:
    - **element**: The current element being processed in the array.
    - **index**: The index of the current element being processed in the array.
    - **array**: The array filter() was called upon.

Example

```javascript
const array = [5, 12, 8, 130, 44];
const found = array.findIndex((element) => {
  return element > 10;
});
console.log(found);
```

Output

```text
1
```

#### findLast()

`findLast()` method iterate an array in reverse order and return the first element from the array that that satisfies the provided test.

Syntax

```javascript
find(callbackFn);
```

- **Parameters**
  - **callbackFn**: A function to execute for each element in array The function is called with the follwing arguments:
    - **element**: The current element being processed in the array.
    - **index**: The index of the current element being processed in the array.
    - **array**: The array filter() was called upon.

Example

```javascript
const array = [5, 12, 8, 130, 44];
const found = array.findLast((element) => {
  return element > 10;
});
console.log(found);
```

Output

```text
8
```

#### findLastIndex()

`findLast()` method iterate an array in reverse order and return the first element index from the array that satisfies the provided test.

Sytax

```javascript
findIndex(callbackFn);
```

- **Parameters**
  - **callbackFn**: A function to execute for each element in array The function is called with the follwing arguments:
    - **element**: The current element being processed in the array.
    - **index**: The index of the current element being processed in the array.
    - **array**: The array filter() was called upon.

Example

```javascript
const array = [5, 12, 8, 130, 44];
const found = array.findLastIndex((element) => {
  return element > 10;
});
console.log(found);
```

Output

```text
3
```

#### flat()

`flat()` method creates and return a new array with all the sub-arrays elements concatenated recursively into it with a specific depth.

Syntax

```javascript
flat(depth);
```

- **Parameters**
  - **depth**: Maximum recurssion depth (1 by default).

Example

```javascript
const arr1 = [0, 1, 2, [3, 4]];
console.log(arr1.flat());
```

Output

```text
[ 0, 1, 2, 3, 4 ]
```

#### flatMap()

`flatMap()` method creates and returns a new array formed by applying a callback function to each element and then flattn the result by one level depth. Basically it is the combination of `map()` and `falt()`.

Syntax

```javascript
flatMap(callbackFn);
```

- **Paramenters**
  - **callbackFn**: A function to execute for each element in array The function is called with the follwing arguments:
    - **element**: The current element being processed in the array.
    - **index**: The index of the current element being processed in the array.
    - **array**: The array faltMap() was called upon.

Example

```javascript
const arr = [1, 2, 1];
const result = arr.flatMap((num) => (num === 2 ? [2, 2] : 1));
console.log(result);
```

Output

```text
[ 1, 2, 2, 1 ]
```

#### forEach()

`forEach()` method execute a provided function for each array elements.

Syntax

```javascript
forEach(callbackFn);
```

- **Parameters**
  - **callbackFn**: A function to execute for each element in array The function is called with the follwing arguments:
    - **element**: The current element being processed in the array.
    - **index**: The index of the current element being processed in the array.
    - **array**: The array forEach() was called upon.

Example

```javascript
arr.forEach((val) => {
  val += val;
  console.log(val);
});
```

Output

```text
2
4
6
8
10
```

#### map()

`map()` method creates new array poplated with the result of calling a callback function on every element of array.

Syntax

```javascipt
map(callbackFn);
```

- **Parameters**
  - **callbackFn**: A function to execute for each element in array The function is called with the follwing arguments:
    - **element**: The current element being processed in the array.
    - **index**: The index of the current element being processed in the array.
    - **array**: The array map() was called upon.

Example

```javascript
const arr = [1, 2, 3, 4, 5];
const newArr = arr.map((val) => {
  return val * 2;
});
```

Output

```text
[ 2, 4, 6, 8, 10 ]
```

#### includes()

`includes()` method **return** `true` when an array includes a certain value, otherwise **return** `false`.

Syntax

```javascript
includes(searchElement, fromIndex);
```

- **Parameters**
  - **searchElement**: The value to search.
  - **fromIndex**: Zero based array index at which start to search.

Example

```javascript
const arr = [1, 2, 3, 4, 5];
console.log(arr.includes(2));
console.log(arr.includes(7));
```

Output

```text
true
false
```

#### join()

`join()` method creates and return a new string by concatenating all the element of an array seperated by commas.

Syntax

```javascript
join(separator);
```

- **Parameters**
  - **seperator**(optional): A string to seperate each pair of array element.

Example

```javascript
const arr = ["Hello", "world"];
console.log(arr.join());
console.log(arr.join("-"));
```

Output

```text
Hello,world
Hello-world
```

#### keys()

`key()` method return a new **array iterator** object that contains key for each index in the array.

Syntax

```javascript
keys();
```

Example

```javascript
const arr = ["a", "b", "c"];
const iterator = arr.keys();
console.log(iterator.next().value);
console.log(iterator.next().value);
console.log(iterator.next().value);
```

Output

```text
0
1
2
```

#### reduce()

`reduce()` method executes a **reducer** callback function on each element of the array, in order, passing in the return value from the calculation on the preceding element. The final result of running the reducer across all elements of the array is a single value.

The first time that callback is run there is no return value in previous calculation, so reducer user index 0 element as initial value and iteration starts from index 1. You can also give an initial value, so the iteration starts from index 0.

Syntax

```javascript
reducer(callbackFn, initialValue);
```

- **Parameters**
  - **callbackFn**: - **callbackFn**: A function to execute for each element in array The function is called with the follwing arguments:
    - **accumulator**: The value resulting from previous call to **callbackFn**.
    - **currentValue**: The value of current element.
    - **currentIndex**: The index position of currentValue.
    - **array**: The array reduce() was called upon.
  - **initialValue**(optional): A value to which accumulator is initialize for the first time callback is called.
    Example

```javascript
const arr = [1, 2, 3, 4, 5];
const val = arr.reduce((accumulator, currentValue) => {
  return accumulator + cureentValue;
});
console.log(val);
```

Output

```text
24
```

#### reverse()

`reverse()` method reverse an array and return the reference of same array.

Syntax

```javascript
reverse();
```

- **Parameters**
  - **none**

Example

```javascript
const arr = [1, 2, 3, 4, 5];
arr.reverse();
console.log(arr);
```

Output

```text
[5, 4, 3, 2, 1]
```

#### slice()

`slice()` method return a shallow copy of an array into a new array selected from `start` index to `end` index (end not including).

Syntax

```javascript
slice(start, end);
```

- **Parameters**
  - **start**(optional): Zero-based index to start extraction.
  - **end**(optional): Zero-based index to end extraction.

Example

```javascript
const arr = [1, 2, 3, 4, 5];
const newArr = arr.slice(2, 4);
console.log(newArr);
```

Output

```text
[ 3, 4 ]
```

#### sort()

`sort()` method sort the elements of an array and return the reference of same array. Default sort order is ascending order.

Syntax

```javascript
sort(compareFn);
```

- **Parameters**
  - **compareFn**(optional): A function that determines the order of the elements. The function is called with following arguments.
    - **a**: The first element for comparisn.
    - **b**: The second element for comparisn.

Example

```javascript
const arr = [1, 2, 3, 4, 5];
// ascending order
arr.sort();
console.log(arr);

const arr2 = [5, 4, 3, 2, 1];
// descending order
arr2.sort((a, b) => {
  a - b;
});
console.log(arr2);
```

Output

```text
[5, 4, 3, 2, 1]
[1, 2, 3, 4, 5]
```

#### toString()

`toString()` method returns a string representing the specified array and its elements.

Syntax

```javascript
toString();
```

- **Parameters**
  - **none**

Example

```javascript
const arr = [1, 2, 3, 4, 5];
const stringArr = arr.toString();
console.log(stringArr);
console.log(typeof stringArr);
```

Output

```text
1,2,3,4,5
string
```

#### values()

`values()` method returns a new **array iterator** object that iterates te value of each item in the array.

Syntax

```javascript
values();
```

- **Parameters**
  - **none**

Example

```javascript
const arr = ["a", "b", "c"];
const iterator = arr.values();

console.log(iterator.next().value);
console.log(iterator.next().value);
console.log(iterator.next().value);
```

Output

```text
a
b
c
```

#### with()

`with()` method is copying version of bracket notation `[]` to change the value of a given index. It returns a new array with the element at the given index replaced with the given value.

Syntax

```javascript
with ((index, value));
```

- **Parameters**
  - **index**: Zero-based index at which to change the array.
  - **value**: Any value to be assigned to given index.

Example

```javascript
const arr = [1, 2, 3, 4, 5];
console.log(arr);
const newArr = arr.with(2, 10);
console.log(newArr);
```

Output

```text
[ 1, 2, 3, 4, 5 ]
[ 1, 2, 10, 4, 5 ]
```
