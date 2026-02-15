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

#### Example

```javascript
// using literals
const arrayWithLiterals = [1, 2, 3, 4, 5];
console.log(arrayWithLiterals);

// using constructor
const arrayWithConstructor = new Array(1, 2, 3, 4, 5);
console.log(arrayWithConstructor);
```

### Output

```
[ 1, 2, 3, 4, 5 ]
[ 1, 2, 3, 4, 5 ]
```

## Array Operations

### Accessing Array Elements

We can access elements of arrays by their indexes.

#### 1. Get first elemet of array.

#### Example

```javascript
const array = [1, 2, 3, 4, 5];
console.log(array[0]);
```

#### Output

```
1
```

#### 2. Get last element of array.

#### Example

```javascript
const array = [1, 2, 3, 4, 5];
console.log(array[array.length - 1]);
```

#### Output

```
5
```

#### 3. Access random element of array

#### Example

```javascript
const array = [1, 2, 3, 4, 5];
console.log(array[2]);
console.log(array[1]);
console.log(array[4]);
```

#### Output

```
3
2
5
```

#### 4. Get length of array

#### Example

```javascript
const arr = [1, 2, 3, 4, 5];
console.log(arr.length);
```

### Modifying Array Elements

We can also add and modify array element by their indexes and methods.

#### 1. Modify array element by index

#### Example

```javascript
const arr = [1, 2, 3, 4, 5];
arr[0] = 10; // modify value of 0 index to 10
console.log(arr);
```

#### Output

```
[ 10, 2, 3, 4, 5 ]
```

#### 2. Adding element to array

There are several methods available to add elements to array.

- `pop()`
- `unshift()`:

#### 1. `push()` add new element to the end of the array.

#### Example

```javascript
const arr = [1, 2, 3, 4, 5];
console.log(arr);
arr.push(10);
console.log(arr);
```

#### Output

```
[ 1, 2, 3, 4, 5 ]
[ 1, 2, 3, 4, 5, 10 ]
```

#### 2. `unshift()` add new element to the starting of the array.

#### Example

```javascript
const arr = [1, 2, 3, 4, 5];
console.log(arr);
arr.unshift(10);
console.log(arr);
```

#### Output

```
[ 1, 2, 3, 4, 5, 10 ]
[ 10, 1, 2, 3, 4, 5 ]
```

### Removing element from array

There are several methods available to remove elements from array.

- `pop()`
- `shift()`
- `splice()`

#### 1. `pop()` remove last element from the end of the array.

#### Example

```javascript
const arr = [1, 2, 3, 4, 5];
console.log(arr);
arr.pop();
console.log(arr);
```

#### Output

```
[ 1, 2, 3, 4, 5 ]
[ 1, 2, 3, 4 ]
```

#### 2. `shift()` remove first element from the stating of the array.

#### Example

```javascript
const arr = [1, 2, 3, 4, 5];
console.log(arr);
arr.shift();
console.log(arr);
```

#### Output

```
[ 1, 2, 3, 4, 5 ]
[ 2, 3, 4, 5 ]
```

#### 3. `splice()` remove or replce elements to a specific range from the array and **return** new array. It takes two arguements **start**(index) and **deleteCount**(range).

#### Example

```javascript
const arr = [1, 2, 3, 4, 5];
console.log(arr);
const newArr = arr.splice(1, 3); // return new array
console.log(newArr);
```

#### Output

```
[ 1, 2, 3, 4, 5 ]
[ 2, 3, 4 ]
```

### Array Methods

