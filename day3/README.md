# Easy way to add a dark theme in your website

## What is a dark theme?

A dark theme displays dark color in the maximum of the UI, reducing strain in our eyes. Recently, a dark theme is a common trend, that can be seen on most websites and apps.

Here in this blog, I am going to share one of the easy ways to add a dark theme when we click a button.

`Turn Your webpage from here:`

![Button Light](https://ishanbagchi.github.io/Ishan-Tech-Blog/day3/images/button-light.PNG)

`To here:`

![Button Dark](https://ishanbagchi.github.io/Ishan-Tech-Blog/day3/images/button-dark.PNG)

> Our main concern is to change the theme, so we are not focusing on beauty and other functionality.

## HTML

We are just creating a button, so we need just a single `button` tag in the HTML file. 

```html
<button id="myBtn">Push Me</button>
```

## CSS

The below code is used to create the basic light theme on the page. 

```CSS
* {
    margin: 0;
    padding: 0;
    border: none;
    box-sizing: border-box;
}

body {
    font-family: 'Open Sans', sans-serif;
    background: #ededed;
    min-height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
}

button {
    color: #000;
    background: #fff;
    border: solid .12rem #121212;
    display: flex;
    align-items: center;
    justify-content: center;
    height: 2rem;
    width: 4rem;
    border-radius: 7%;
}
```

The below code is concerned about the UI(User Interface) of the dark-theme.

```css
.dark-mode {
    background: #121212;
}

.dark-mode > button {
    background: #000;
    color: #fff;
    border-color: #ededed;
}
```

## JavaScript

This is the main script involved in giving the dark-theme to our website when the `push me` key is pressed.

```javascript
document.getElementById("myBtn").addEventListener("click", function() {
    var element = document.body;
    element.classList.toggle("dark-mode");
});
```

Walla! Our fully functioning toggle dark theme is completed. Isn't it short and simple? 

> There is a small limitation, link to your JavaScript file in the `body` tag, and not in the `head` tag of your HTML code. 

You can check the full functioning button by pressing this [here](https://ishanbagchi.github.io/Ishan-Tech-Blog/day3/button.html).
