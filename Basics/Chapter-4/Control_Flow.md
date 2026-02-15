# Chapter - 4 Control Flow

**Control flow** is the order in which the computer executes statements in a script.

Code run in order from first line of the file to last line,
unless you encounter structures that change that order, such as conditionals and loops.

1. Conditional Statements
2. Looping Statements
3. `break` and `continue` Statements

## 1. Conditional Statements

Conditional statements are used to make decision in programs based on given conditions.

### `if-else` statements

`if-else` statement execute a statement or a block of code if the specified condition is **truthy**. And if condition is **falsy** then another statement or block of code executes. `else` block is optional if you have something to run when condition is false then use `else` otherwise leave it.

```javascript
const age = 19;
if (age <= 18) {
  console.log("Adult");
} else {
  console.log("Teenager");
}
```

```
Teenager
```

#### `if-else if-else` leadder

when you have multiple statements to check and execute some code based on it. You have to use multiple `if` statements but it is not good practicre and also effect code redebility insted of multiple `if` statements use `if-else if-else` leadder. We can have any numbers of else if blocks.

```javascript
const score = 85;
if (score >= 90) {
  console.log("Grade A");
} else if (score >= 80) {
  console.log("Grade B");
} else if (score >= 70) {
  console.log("Grade C");
} else {
  console.log("Grade F");
}
```

```
Grade B
```

#### Nested `if-else`

Nested if-else is when you use `if-else` statements inside another `if-else` statement.

```javascript
const age = 20;
const hasLicense = true;

if (age >= 18) {
  if (hasLicense) {
    console.log("You can drive");
  } else {
    console.log("Get a license first");
  }
} else {
  console.log("You are too young to drive");
}
```

```
You can drive
```

### `switch` statements

`switch` statement is used to execute different blocks of code based on different conditions. It is more readable than multiple `if-else` statements.

```javascript
const day = 3;
switch (day) {
  case 1:
    console.log("Monday");
    break;
  case 2:
    console.log("Tuesday");
    break;
  case 3:
    console.log("Wednesday");
    break;
  default:
    console.log("Invalid day");
}
```

```
You can drive
```

> Note: Use `break` keyword to exit the switch block. Without `break`, the code will execute the next case (fall-through behavior).

## 3. Loops

Loops allows a block of code to run multiple times as log as a given condition is true. It help to reduce repetation, make code more readable and organized.

There are many types of loops available in Javascript:

1. `for` loop
2. `while` loop
3. `do-while` loop
4. `forEach` loop
5. `for-in` loop
6. `for-of` loop

> Note: `forEach`, `for-in` and `for-of` loops discuss later.

### 1. `for` Loops

`for` loop is a control flow loop that allows code to be executed repeatedly based on a condition. It consist of three parts: **initialization**, **condition** and **increament/decreament**.

#### Syntax

```
for (initialization; condition; increament/decreament) {
  // code...
}
```

#### Output

```javascript
// for loop begins when x=2
// and runs till x <= 4
for (let x = 2; x <= 4; x++) {
  console.log("Value of x:" + x);
}
```

#### Result

```
Value of x:2
Value of x:3
Value of x:4
```

### 2. `while` loop

`while` loop executes a block of code as long as specified condition is true. This loops evaluates the condition before each iteration and continues running as long as condition remains true. It consist of three parts: **initialization**, **condition** and **increament/decreament**.

#### Syntax

```
initialization
while(condition) {
   // code

   increament/decreament
}
```

#### Example

```javascript
let count = 0;
while (count <= 5) {
  console.log("Value of count:" + count);
  count++;
}
```

#### Output

```
Value of count:1
Value of count:2
Value of count:3
Value of count:4
Value of count:5
```

### 3. `do-while` loop

`do-while` loops is a type of `while` loop, but with a key difference. `do-while` loop guarantees that the block of the code inside the loop will executed atleast once regardless of condition if `true` or `false`.

#### Syntax

```
initialization
do {
   // code

   increament/decreament
} while(condition);
```

#### Examples

> If codition is true

```javascript
let count = 1;
do {
  console.log(count);
  count++;
} while (count <= 5);
```

Output

```
Value of count:1
Value of count:2
Value of count:3
Value of count:4
Value of count:5
```

> If codition is false

```javascript
let count = 1;
do {
  console.log(count);
  count++;
} while (count > 5);
```

#### Output

```
Value of count:1
```

## 3. `break` and `continue` statements

We already discussed about loops like what they are? and why use loops?. So lets discuss about some loops statements.

### `break` statement

Use `break` statement to terminate all iterations of loop. For example a loop which print numbers between 1 to 10 but have to stop remaining execution when number is 5, so we use `break` statement to stop the remaining execution of loop.

#### Example

```javascript
for (let i = 0; i <= 10; i++) {
  if (i === 5) break; // break loop if i is equal to 5
  console.log(i);
}
```

#### Output

```
0
1
2
3
4
```

### `continue` statement

Use `continue` statement to skip a specified iterations of loop. For example a loop which print numbers between 1 to 10 but have to skip single execution when number is 5, so we use `continue` statement to skip fifth execution and continues the remaining execution of loop.

#### Example

```javascript
for (let i = 0; i <= 10; i++) {
  if (i === 5) continue; // skip fifth iteration
  console.log(i);
}
```

#### Output

```
0
1
2
3
4
6
7
8
9
10
```
