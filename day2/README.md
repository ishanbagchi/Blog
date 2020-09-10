# How to write a clean code.

> Any fool can write code that a computer can understand. Good programmers write code that humans can understand. <br>
> `-Martin Fowler`

There are two things- Programming and Good Programming. Programming is what we have all been doing, writing codes for the machines to understand. Now is the time to do good programming, the codes people can understand. We all know that even bad code works. But it takes time and resources to make a program good. Moreover, other developers mock you when they are trying to find what all is happening in your code. But it’s never too late to care for your programs.

> Here are some of the methods to write clean codes.

## Write DRY codes.

DRY is an acronym that stands for **Don’t Repeat Yourself**. If you are doing the same thing in multiple places, consolidate the duplicate code. If you see patterns in your code, that is an indication it is prime for DRYing. Sometimes this means standing back from the screen until you can’t read the text and literally looking for patterns.

`clean code`
```javascript
const MyOtherComponent = ({ type }) => (
  <OtherComponent type={type} className="colorful" foo={123} bar={456} />
);
const MyComponent = () => (
  <div>
    <MyOtherComponent type="a" />
    <MyOtherComponent type="b" />
  </div>
);
```
`bad code`
```javascript
const MyComponent = () => (
  <div>
    <OtherComponent type="a" className="colorful" foo={123} bar={456} />
    <OtherComponent type="b" className="colorful" foo={123} bar={456} />    
  </div>
);
```

Sometime DRYing code may increase your code size, but it increases maintainability. For eg, you can just change one line of the function which will be implemented all over the program.

## Use Intention-Revealing name

The names of the variable should be revealed so that others can understand the purpose of the variable. 

`clean code`

```javascript
var $elapsedTimeInDays;
var $daysSinceCreation;
```

`bad code`

```javascript
var $d; //elapsed time in days
```

## Make code speak

The code should have the ability to make people understand what is its purpose.

`clean code`

```javascript
if ($employee -> isEligibleForFullBenifits())
```

`bad code`

```javascript
// check to see if the employee is elegible for full benifits
if ($employee -> flags && self :: HOURLY_FLAG && $employee -> age > 65)
```

## Commented out code

We've all seen entire blocks of code containing multiple functions being commented out. Just delete that piece of commented-out code.

## Messy formatting of code

One of the most common ways to solve messy formatting is by using a linter.

## Here are some Do's and Dont's for clean code

```diff
+ Do's
```
* Use verbs for function names
* Use nouns for classes and attributes
* The smaller the better
* A function should only do one thing
* Don't comment bad code, rewrite it
* Explain your intention in comments

```diff
- Dont's
```
* Dead code
* Large classes
* Framework core modifications
* Overuse of static
* Magic numbers - replace with `const` or `var`
* Hard-coding

## Conclusion
I hope that I’ve helped you see the benefits of writing clean code and that you can even use some of the practical examples presented here. Once you embrace writing clean code, it will become second nature. You (and your future self) will soon appreciate the “write it and forget it” way of life.