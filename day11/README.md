# Important Interview Questions: Javascript Version - Part 4

## What are all the types of Pop up boxes available in JavaScript?

+ **Alert Box**: Used to give an alert to the user.
+ **Confirm Box**: Used to verify or confirm something from the user. It consists of an _ok_ button, and a _cancel_ button. It returns true when ok is pressed and returns false for cancel.
+ **Prompt Box**: Used to accept input from the user.

```javascript
window.alert('Hi! I am an ALERT BOX!')

window.confirm('Please Confirm me. I am CONFIRM BOX!')

window.prompt('I am PROMPT BOX! I am the question', 'I am the default text!')
```

## What is the use of void(0)?

The void operator is often used merely to obtain the _undefined_ primitive value, usually using _"void(0)"_ (which is equivalent to "void 0"). In these cases, the global variable undefined can be used.

## How can a page be forced to load another page in JavaScript?

```html
<script language="JavaScript" type="text/javascript">
    location.href = 'link to be opened comes here'
</script>
```

## What is the data type of variables in JavaScript?

All variables in JavaScript are of the object data type.

## What is the difference between an alert box and a confirmation box?

+ **Alert Box** displays only one button that is the _OK_ button.
+ **Confirm Box** displays two buttons. _OK_ button and a _Cancel_ button. Returns true for Ok and false for Cancel.

## What are escape characters?

Escape characters (Backslash) is used when working with special characters like single quotes, double quotes, apostrophes, and ampersands. Place backslash before the characters to make it display.

```javascript
console.log('Without 'escape' characters!')
// prints an error

console.log('With \'escape\' character!')
// prints: With 'escape' character!
```

## What are JavaScript Cookies?

When a browser requests a web page from a server, cookies belonging to the page are added to the request. This way the server gets the necessary data to "remember" information about users.

## Explain what is the pop() method in JavaScript?

The pop method removes the last element from an array and returns that value to the caller. pop is intentionally generic; this method can be called or applied to objects resembling arrays.

## Whether JavaScript has a concept level scope?

No. JavaScript does not have a concept-level scope. The variable declared inside the function has scope inside the function.

## Mention what is the disadvantage of using innerHTML in JavaScript?

- **The use of innerHTML very slow**: The process of using innerHTML is much slower as its contents as slowly built, also already parsed contents and elements are also re-parsed which takes time.
- **Content is replaced everywhere**: Either you add, append, delete or modify contents on a webpage using innerHTML, all contents are replaced, also all the DOM nodes inside that element are reparsed and recreated.
- **Can break the document**: There is no proper validation provided by innerHTML, so any valid HTML code can be used. This may break the document of JavaScript. Even broken HTML can be used, which may lead to unexpected problems.
- **Old content replaced issue**: The old content is replaced even if _object.innerHTML = object.innerHTML + ‘html’_ is used instead of object.innerHTML += ‘html’. There is no way of appending without reparsing the whole innerHTML. Therefore, working with innerHTML becomes very slow. String concatenation just does not scale when dynamic DOM elements need to be created as the plus’ and quote openings and closings becomes difficult to track.
