# Chapter - 2 Data types and Type system

## What is Data types ?

In Javascript every value has type. It means every value belongs to a type.
These types define what type of values is being store - number, string, boolean, etc.

### Types of Data types

**1. Primitive Types**: Primitive is a data that is not `object` and has no methods or properties. These are copied directly.
   There are types of primtive data types:

- number
- string
- boolean
- null
- undefined
- symbol
- bigint

**2. Reference Types**: Reference is a data that is `object` and has methods or properties. These are not copied directly, but by reference.
   There are 3 types of reference data types:

- object
- srray
- function

> Reference Types will discussed later in detail.

## `typeof` Operator

`typeof` operator is used to check the data type of value. Returns data type of value.

```javascript
// Primitive

typeof "John"; // Returns string
typeof ("John" + "Doe"); // Returns string
typeof 3.14; // Returns number
typeof 33; // Returns number
typeof (33 + 66); // Returns number
typeof true; // Returns boolean
typeof false; // Returns boolean
typeof 1234n; // Returns bigint
typeof Symbol(); // Returns symbol
typeof x; // Returns undefined

// Referenced Types
typeof {} // object
typeof [] // this is an array but its types is object
typeof function(){} // function
```

Facts

- typeof null === "object" is a bug, but has existed since the early days of JS.

## Type Coercion(auto conversion)

Type coercion is the automatic or implicit conversion of values from one data type to another (such as strings to numbers).

```javascript
"5" + 1; // "51" → number converted to string
"5" - 1; // 4 → string converted to number
true + 1; // 2
null + 1; // 1
undefined + 1; // NaN
```

## Lose vs Strict Equality

Eqaulity operators checks weather its two operand are equal or not. Return **boolean** (true if both operand is equal or false if not eqaul).

There are two types of operators are used for equality check.

1. `==` operator: compares values with type conversion. **Lose Equality check**.
2. `===` operator: Compares values + type (no conversion). **Strict Equality check**.

```javascript
"5" == 5; // true (Loose equality check)
"5" === 5; // false (Strict equality check)
```

> Tip: Always use `===` for acurate comparison.

## NaN - Not a Number

NaN (Not a Number) is a numeric data type that means an undefined value or value that cannot be represented, especially results of floating-point calculations.

```javascript
typeof NaN; // number
```

## Truthy and Falsy Values

Every value in JavaScript has an inherent boolean "truthiness" or "falsiness," which means they can be implicitly evaluated to true or false in boolean contexts. It is useful for conditional statements or logical operations.

### Falsy Values

Falsy values are values that evaluate to `false` when used in a Boolean. JavaScript has a fixed list of falsy values

- false
- 0 (and -0)
- 0n (BigInt zero)
- "" (empty string)
- null
- undefined
- NaN
- document.all (used for backward compatibility)

```javascript
console.log(false); // false
console.log(0); // false
console.log(0n); // false
console.log(""); // false
console.log(null); // false
console.log(undefined); // false
console.log(NaN); // false
console.log(document.all); // false
```

### Truthy Values

Truthy values are values that are evaluated to be `true` when used in a Boolean. Simply put, any value that is not a falsy value is considered truthy.

Some truthy values are:

- Any non-zero number(1, 2.3, -2)
- Non empty string
- Objects and Arrays
- Functions
- Symbols
- Bigint greater than 0n

```javascript
console.log(true); // true
console.log(8); // true
console.log("abc"); // true
console.log({}); // true
console.log([]); // true
console.log(344n); // true
```
