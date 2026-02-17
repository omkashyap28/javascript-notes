# Chapter - 5 Function Statements & Expressions

Functions are the reusable block of code design to perform specific tasks when **invoked(call)** makes code more readable, reusable and modular. It can take some input and perform some actions.

`function` keyword is used to define function.

## Function Declaration

A **function declaration** (also known as **function defination** or **function statement**) consist of the `function` keyword.

Syntax

```javascript
function functionName() {
  // code
}
functionName(); // function invoke
```

- **function**: keyword used to declare function.
- **functionName**: Name of function (it can be any value).

## Function Expression

Function expression is very similar to **function declaration** but have a key difference. In function expression we can create a function with name, but function expression cannot have any name instead it is stored in a variables and can be use as anonymous function.

Syntax

```javascript
const abcd = function () {
  // code
};
```

## Function Parameters & Arguments

### 1. Parameters

Parameter are the placeholders for incoming data defined at function declaration stage similar to variables.

### 2. Arguments

Arguments are actual values for parameters given at the time of function invokation.

Syntax

```javascript
function greet(name) {
  // code
}
greet(`Javascript`);
```

- **function**: Keyword used to declare function.
- **greet**: Name of function
- **name:** Function parameter
- **\`javascript\`**: Argument of function

Example

```javascript
function greetUser(user) {
  console.log(`Hello, ${user}`);
}
greetUser(`John doe`);
```

Output

```text
Hello, John doe
```

### Types of Parameters

1. **Default parameters**: Provide default values to parameters so arguments become optional.
2. **Rest parameters**: Used for unkown numbers of parameters.
3. **Spread parameters**

> Note: **spread parameter** will duscuss leter.

## Types of Functions

### Named Function

A function that has its own name when declared. It’s easy to reuse and debug because the name shows up in error messages or stack traces.

Example

```javascript
function greet() {
  return "Hello!";
}
console.log(greet());
```

### Anomyous Function

A function that does not have a name. It is usually assigned to a variable or used as a callback. Since it has no name, it cannot be called directly.

Example

```javascript
const greet = function () {
  return "Hello!";
};
console.log(greet());
```

### Fat Arrow Function

A new way to write functions using the => syntax. They are shorter and do not have their own this binding, which makes them useful in some cases.

Example

```javascript
const greet = () => {
  return "Hello!";
};
console.log(greet());
```

### Immediately Invoked Function Expression (IIFE)

IIFE functions are executed immediately after their definition. They are often used to create isolated scopes.

Example

```javascript
(function () {
  console.log("Hello");
})();
```

### High Order Function

A function that either takes another function as a parameter or returns another function. These are common in JavaScript (e.g., map, filter, reduce).

Example

```javascript
function multiplyBy(factor) {
  return function (num) {
    return num * factor;
  };
}

const double = multiplyBy(2);
console.log(double(5));
```

### Callback Function

A callback function is passed as an argument to another function and is executed after the completion of that function.

Example

```javascript
function num(n, callback) {
  return callback(n);
}

const double = (n) => n * 2;

console.log(num(5, double));
```

### Pure Function

Pure functions return the same output for the same inputs and do not produce side effects. They do not modify state outside their scope, such as modifying global variables.

Example

```javascript
function pureAdd(a, b) {
  return a + b;
}

console.log(pureAdd(2, 3));
```
