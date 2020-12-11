# Important Interview Questions: Javascript Version - Part 3

## Explain how to read and write a file using JavaScript?

```javascript
const fs = require('fs')

fs.writeFile('index.js', 'Content of the file goes here', (error) => {
    if(error) {
        console.log(error)
    }
    console.log('file created!')
})

fs.readFile('input.js', (err, data) => {
    if(err) {
        console.log(err)
    }
    console.log(`The data in the file is: ${data.toString()}`)
})
```

1. First we require ___fs___ module (Node File System module) which reads and writes in a file.
2. The function _`writeFile()`_ is used to create a file. This function accepts 2 arguments and a function. The first one takes the name of the file, the second argument takes the data of the file, and lastly, the function takes the error (if any).
3. The function _`readFile()`_ is used to read a file. This function accepts the name of the file to be searched and then there is a function with two arguments. First for the error, and second for the data inside the file.

## What are all the looping structures in JavaScript?

The different looping structures in JavaScript are:

+ for loop
+ while loop
+ foreach loop
+ do ...while loop
+ for-in loop

## What is called Variable typing in Javascript?

JavaScript is a dynamically typed, that means values of a variable can be reassigned various time.

```javascript
var a // undefined
a = 'Hello World' // string
a = 30 // number
a = true // boolean
a = {} // object
```

## How can you convert the string of any base to integer in JavaScript?

In JavaScript _`parseInt()`_ function is used to convert the string to an integer. This function returns an integer of the base which is specified in the second argument of the `parseInt()` function. The `parseInt()` function returns Nan (not a number) when the string doesn’t contain number.

**Syntax**:

```javascript
parseInt(value, radix)
```

## Explain the difference between `==` and `===`?

+ `==` converts the variable values to the same type before performing the comparison. This is called type coercion.
+ `===` does not do any type conversion (coercion) and returns true only if both values and types are identical for the two variables being compared.

## What would be the result of `3+5+"7"`?

Since 3 and 5 are integers, they will add up to 8. Since 7 is a string, it will be concatenated to an integer. Then the result 60 will be printed.

## Explain how to detect the operating system on the client machine?

All the window.navigator properties can be listed by

```javascript
console.log(navigator)
```

## What do mean by NULL in Javascript?

The value `null` represents the intentional absence of any object value. It is one of JavaScript's primitive values and is treated as falsy for boolean operations.

## What is the function of the delete operator?

The delete keyword is used to delete a property as well as the value of an object.

```javascript
var student = {"name": "Ishan", "roll": 19}

delete student.roll // deletes the roll property
```

## What is an undefined value in JavaScript?

Undefined value means the

+ Variable used in the code doesn't exist
+ Variable is not assigned to any value
+ Property doesn't exist
