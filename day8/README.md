# Arrow functions: All you need to know!

An arrow function is an alternative to a traditional function expression, but is limited and can't be used in all situations.

> Syntax of an arrow function
```javascript
const foo = (arg1, arg2, ..., argN) => expression
```

## Some examples:

> ## Add two numbers

```javascript
// Arrow function
const addArrow = (number1, number 2) => number1 + number2

// Traditional function
let addTraditional = function(a, b) {
  return a + b;
};

console.log(addArrow(5 , 7)) // 12
console.log(addTraditional(5 , 7)) // 12
```

> ## Multiline functions

We have to add curly braces if there are more than 1 line in a function.

```javascript
let add = (number1, number2) => {  // the curly brace opens a multiline function
    let result = number1 + number2;
    return result; // if we use curly braces, then we need an explicit "return"
};
```

> ## One argument function

If only one argument is passed through the function, the braces can be ommited

```javascript
let add = number => number + 10

console.log(add(5)) // 15
```

## Limitations of arrow functions:

+ Does not have its own bindings to this or super, and should not be used as methods.
+ Does not have arguments, or new.target keywords.
+ Not suitable for call, apply and bind methods, which generally rely on establishing a scope.
+ Can not be used as constructors.
+ Can not use yield, within its body.

I have mentioned the surface level facts of arrow functions. For more information visit the official arrow function [doccumentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions) of MDN.