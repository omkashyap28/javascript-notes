# Chapter - 3 Javascript Operators

Operators are the symbol or keywords used to perform operations on values and variables. Also manipulate data in various ways.

There are many types of Operators in Javascript:

1. Arithmatic Operators
2. Comparison Operators
3. Logical Operators
4. Assignment Operators
5. Unary Operators
6. Ternary Operators

### 1. Arithmetic Operators

Arithmetic operators are operate on numeric values and used for mathematical calculations.
|Operator | Name | Description |
|---------|------|-------------|
|`+` | Addition | Used to add/concatinate two operands |
`-` | Substraction | Used to substract two numeric operands |
|`*` | Multiplication | Returns the multiplication value of two numeric operands |
| `/` | Division | Return qeustiont |\
| `%` | Modulas | Returns the reminder after division of two numeric operands |
| `**` | Exponentiation | Returns the power value of operand |

```javascript
console.log(10 + 10); // 20
console.log("Java" + "script"); // Javascript
console.log(20 - 10); // 10
console.log(10 * 10); // 100
console.log(100 / 5); // 20
console.log(10 % 5); // 0
console.log(2 ** 3); // (2 * 2 * 2) = 8
```

### 2. Comparison Operators

Comparison operators are used to make comparisons between two operands of any data types and return `boolean` (`true` if operands are equal and `false` if operands are not equal).  
|Operator | Name | Description |
|---------|------|-------------|
| `==` | Equal | Returns `true` if operands are equal |
| `!=` | Not Equal | Returns `true` if operands are not equal |
| `===` | Strict Equal | Return `true` if oprands are equal and same types |
| `!==` | Not Strict Equal | Return `true` if operands are not equal but same types.
| `<` | Smaller than | Return `true` if left operand is less than right operand |
| `>` | Greater than | Return `true` if left operand is greater than right |
| `<=` | Smaller than or Equal | Return `true` if left operand is less than or equal to right operand |
| `<=` | Greater than or Equal | Return `true` if left operand is greater than or equal to right operand |

```javascript
console.log(10 == "10"); // true
console.log(100 == 100); // true
console.log(10 === "10"); // false

console.log("Javascript" != "java"); // true
console.log("Javascript" !== "java"); //

console.log(213 < 45); // false
console.log(45 < 213); // true
console.log(1000 <= 1000); // true
```

### 3. Logical Operators

Logical operators are used with `boolean` values, they return `true` or `false`. However, the `&&`, `||`, and `??` operators actually return the value of one of the specified operands.
|Operator | Syntax | Name | Description |
|---------|------ |------|-------------|
| `\|\|` | `expr1 \|\| expr2` | Logical Or | Returns `expr1` if it can be converted to `true`; otherwise, returns `expr2`. Thus, when used with Boolean values, returns `true` if either operand is `true`; if both are `false`, returns `false` |
| ?? | `expr1 ?? expr2` | Nullish Coalescing | Returns `expr1` if it is neither `null` or `undefined`; otherwise, returns `expr2` |
| ! | `!expr1` | Logical Not | Returns false if its single operand can be converted to true; otherwise, returns true |

```javascript
console.log(true && true); // true
console.log(true && false); // false
console.log(false && true); // false
console.log(5 > 3 && 10 > 8); // true

console.log(true || false); // true
console.log(false || false); // false
console.log(5 > 10 || 10 > 8); // true

console.log(null ?? "default"); // "default"
console.log("value" ?? "default"); // "value"
console.log(undefined ?? "default"); // "default"

console.log(!true); // false
console.log(!false); // true
console.log(!(5 > 3)); // false
```

### 4. Assignment Operators

Assignment Operators assign value to its left operand based on the value of its right operand.
|Operator | Name | Description |
|---------|------|-------------|
| `=` | Assignment | Assing value of right operand to left operand |
| `+=` | Addition Assignment | Perform addition/concatination on two operand and assign the result in left operand |
| `-=` | Subtraction assignment | Perform substraction on two operand and assign the result to left operand |
| `*=` | Multiplication Assignment | Perform multiplication on two operand and assign the result to left operand |
| `/=` | Division Assignment | Perform division on two operand and assign the result to left operand |
| `%=` | Remainder Assignment | Perform remainder on two operand and assign the result to left operand |
| `**=` | Exponentiation assignment | Perform exponentiation on two operand and assign the result to left operand |

```javascript
let a = 10;
a += 5; // a = 15
a -= 3; // a = 12
a *= 2; // a = 24
a /= 4; // a = 6
a %= 4; // a = 2
a **= 3; // a = 8
```

### 5. Unary Operators

Unary operators work with a single operand.

| Operator | Name        | Description                                 |
| -------- | ----------- | ------------------------------------------- |
| `++`     | Increment   | Increases the value of operand by 1         |
| `--`     | Decrement   | Decreases the value of operand by 1         |
| `+`      | Unary Plus  | Converts operand to a number                |
| `-`      | Unary Minus | Converts operand to a number and negates it |

```javascript
let x = 5;
x++; // x = 6
x--; // x = 5
console.log(+true); // 1
console.log(+"5"); // 5
console.log(-true); // -1
console.log(-"5"); // -5
```

### 6. Ternary Operator

The ternary operator is a conditional operator that takes three operands and returns a value based on a condition.

```javascript
let age = 18;
let status = age >= 18 ? "Adult" : "Minor";
console.log(status); // Adult

let score = 85;
let grade = score >= 90 ? "A" : score >= 80 ? "B" : "C";
console.log(grade); // B
```

## Difference between `typeof` and `instanceof`

`typeof` returns a string representing the data type of a value, while `instanceof` checks if an object is an instance of a specific class or constructor.

```javascript
typeof 5; // "number"
typeof "hello"; // "string"
typeof {}; // "object"

const arr = [1, 2, 3];
arr instanceof Array; // true
arr instanceof Object; // true

const obj = {};
obj instanceof Array; // false
obj instanceof Object; // true
```

`typeof` works with primitives and objects, but `instanceof` only works with objects and requires a constructor function for comparison.
