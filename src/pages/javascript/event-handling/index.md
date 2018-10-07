---
title: Event Handling
---

## Event Handling

Events are (in the context of JavaScript) actions or incidents which happen inside the browser window such as

* the user clicks on something or hovers over it
* the user presses a key
* the user drags and drops something
* the user submittes a form
* content finishes loading
* a video starts or stops playing
* an error occurrs

and many more.

When the event happens it sends a signal which your code can react to.

Events usually occur on a specific item in the browser window, such as an element, a group of elements, the HTML document in your current tab, or the browser window itself.

You can use JavaScript to attach an event handler (also called an event listener) to these items to "listen" for a particular event and run some code when the event happens.

Inside the event handler, you specify two things: the type of event you are listening for, and the code you want to run when the event occurs. 

```html
<button>Click Me!</button>
```

```js
const button = document.querySelector("button");

button.addEventListener("click", () => console.log("Clicked!"));
```

### Avoid inline event handlers

The earliest way of handling events was inline event handlers where you write your JavaScript as the element's attribute value.

```html
<button onclick="alert('I am an inline event handler!');"></button>
```

This can become unmaintainable and inefficient. Just like with inline styles in CSS, if you change your mind later you have to go through your HTML and change every inline event handler one by one; and you might miss one. It's better to select elements and add event listeners in your seperate JavaScript file. 