# Chapter - 1 Variables and Declarations

## Variables in Javascript

Variables are containers that hold data.
They help us store, reuse, and update information in JavaScript — from simple values like
numbers to complex data like arrays and objects.

In javascript we can create variables with `var`, ` let` and `const` keywords.

1. **var**

- Old and risky. We cannot create variables with **var** in modern javascript.
- Functional scoped.
- Can be redeclared and reassigned.
- Hoisted to the top with undefined value

```javascript
var a = 1;
```

2. **let**

- Modern and safe. We create variables with **let** in javascript.
- Block scoped.
- Can not be redeclared, but reassignable.
- Hoisted, but stays in the Temporal Dead Zone (TDZ)

```javascript
let a = 1;
```

3. **const**

- Modern and safe. We create variables with **const** in javascript.
- Hoisting not applied.
- Block scoped.
- Can not be redeclared and reassignable.
- Hoisted, but stays in the Temporal Dead Zone (TDZ).

```javascript
const a = 1;
```

> Note: We can also declare variables without any keywords. But this is not good method to declare any variable instead use `let` and `const`.

## Scopes in Javascript

The scope is the current context of execution in which values and expressions are "visible" or can be referenced

### Types of scopes

1. Global Scope - Global variables can be accessed from anywhere in a JavaScript program.
2. Block Scope - Variables defined inside a block `{}` are not accessible (visible) from outsize the block.
3. Function Scope - Variables defined inside a function are not accessible (visible) from outside the function.

## Temporal Dead Zone

Variables declared with `let`, `const` or `class` is said to be in a **temporal dead zone(TDZ)** from the start of the block until code execution reaches the place where the variables is declared and initialized.

Inside TDZ, the variables has not been declared and initialzed with any value, and any attempt to access them will result in **ReferenceError**. The variable initialzed with value when execution reaches the place where variable is declared. If no initial value was specified with the variable declaration, it will be initialized with a value of `undefined`.

#### Facts

Variable decalred with `var` keyword does't have **temporal dead zone**.
Variables declared with `var` keyword return `undefined` if they are accessed before they are declared.

## Hoisting

Javasript prepares memory before running code.
It moves all declarations to the top and initialize later - this is called hoisting.

#### Facts

- Variables declared with `var` is hoisted and set to undefined.

```javascript
console.log(a); // undefined
var a = 10;
```

- Variables declared with `let` & `const` is also hoisted but not initialized. So accessing them early give **RefecenceError** because of **temporal dead zone**.

```javascript
console.log(a); // ReferenceError
let a = 10;
```

or

```javascript
console.log(a); // ReferenceError
const a = 10;
```
