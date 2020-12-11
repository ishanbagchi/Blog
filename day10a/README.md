# Important Interview Questions: Javascript Version - Part 2

## What are global variables? How are these variables declared and what are the problems associated with using them?

A JavaScript global variable is declared outside the function or declared with the window object. It can be accessed from any function.

```javascript
var value = 50 // global variable

function foo() {
    alert(value)
}
```

The problems that are faced by using global variables are the clash of variable names of local and global scope. Also, it is difficult to debug and test the code that relies on global variables.

## What is a prompt box?

A prompt box is used to take input from the user by providing a text box. The syntax of the prompt box is:

```javascript
window.prompt("question or text", "default value")
```

## What is 'this' keyword in JavaScript?

`this` keyword has different values in different circumstances:

+ _In a method_, `this` refers to the **owner object**.
+ _Alone_, `this` refers to the **global object**.
+ _In a function_, `this` refers to the **global object**.
+ _In a function_, in strict mode, `this` is **undefined**.
+ _In an event_, `this` refers to the **element** that received the event.
+ _Methods like `call()`, and `apply()`_ can refer `this` to **any object**.

## Explain the working of timers in JavaScript? Also elucidate the drawbacks of using the timer, if any?

Timers are used to execute a piece of code at a set time or also to repeat the code in a given interval of time. This is done by using the functions _`setTimeout()`_, _`setInterval()`_ and _`clearInterval()`_.

+ **setTimeout(function, delay)**- This is used to set a timer, that calls the _function_ after the mentioned _delay_.
+ **setInterval(function, delay)**- This function is used to call the _function_ repeatedly after the mentioned _delay_ and only halts when canceled.
+ **clearInterval(id)**- This function instructs the timer to stop.

Timers are operated within a single thread, and thus events might queue up, waiting to be executed.

## Which symbol is used for comments in JavaScript?

```javascript
// double slash for single-line comment

/* 
Single slash and asterisk
for multi-line comments
*/
```

## What is the difference between _ViewState_ and _SessionState_?

__ViewState__ is specific to a page in a session.

__SessionState__ is specific to user-specific data that can be accessed across all pages in the web application.

## What is the `===` operator?

`===` (Triple equals) is a strict equality comparison operator in JavaScript, which returns false for the values which are not of a similar type. This operator performs type casting for equality. If we compare 2 with "2" using ===, then it will return a false value.

## How to submit a form using JavaScript?

If the form to be submitted has the id _`myForm`_ then we can use the code below to submit the form.

```javascript
document.getElementById("myForm").submit()
```

## Does JavaScript support automatic type conversion?

JavaScript is a _loosely typed_ language, which means that whenever an operator or statement is expecting a particular data-type, JavaScript will automatically convert the data to that type.

## How can the style/class of an element be changed?

A specific style can be added by

```javascript
document.getElementById("myText").style.fontSize = "20"
```

A class can be added by

``` javascript
document.getElementById("myText").className = "any-class"
```

> Will be coming with new questions soon. Till then, stay tuned.
