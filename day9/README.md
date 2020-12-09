# Important Interview Questions: Javascript Version - Part 1

Here are some of the javascript questions asked in interviews.

## What is JavaScript?

Javascript is a scripting language that adds functionality to a web page for example javascript adds animations on clicking a button. JavaScript is also an Object-based Programming language.

## State the difference between javascript and java

Java | JavaScript
-|-
It is Object-Oriented Programming language | It is an Object-based Scripting language
Java applications can run in any virtual machine(JVM) or browser|JavaScript code used to run only in the browser, but now it can run on the server via Node.js
Supports multithreading|Does not support multithreading

## What are Javascript datatypes?

Following are the JavaScript Data types:

+ Number
+ String
+ Boolean
+ Arrays
+ Object
+ Undefined
+ Null

## What is the use of the isNaN function?

This function returns true when the argument passed is not a number.

## Between JavaScript and an ASP script, which is faster?

Javascript is a client-side language and does not require assistance from the web. On the other hand, ASP is a server side language and hence is slower than JavaScript. (For details on ASP check the [doccumentation](https://home.ubalt.edu/abento/452/asp/index.html).)

## What is Negative Infinity?

A number in JavaScript which is derived by dividing a negative number by zero is called Negative Infinity.

## Is it possible to break JavaScript Code into several lines?

In a string statement, a backslash can be given at the end of the 1st line to move the rest in the next line.

```javascript
doccument.write('First line. \Second line.')
```

And if you change to a new line when not within a string statement, then javaScript ignores the break in the line.

```javascript
const number =
40
```

## Which company developed JavaScript?

Netscape is a software company that developed JavaScript.

## What are undefined and undeclared variables?

**Undefined** occurs when a variable has been declared but no value is assigned to it. Undefined is not a keyword.

**Undeclared** occurs when we try to access a variable that is not defined using the `const`, `var` or `let` keyword.

```javascript
let undefinedVariable

console.log(undefinedVariable) // undefined
console.log(undeclaredVariable) // ReferenceError: undeclaredVariable is not defined
```

## Write the code for adding new elements dynamically?

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <title>Dynamic elements</title> 
    <script type="text/javascript"> 
        function addNode() { 
            var newP = document.createElement("p"); 
            var textNode = document.createTextNode(" This is a new text node"); 
            newP.appendChild(textNode); 
            document.getElementById("oldP").appendChild(newP); 
        } 
    </script>
</head> 
<body> 
    <p id="oldP">firstP<p> 
</body> 
</html>
```
