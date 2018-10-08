---
title: Event Handling
---

## Event Handling

Events are (in the context of JavaScript) actions or incidents which happen inside the browser window such as

* the user clicks on something or hovers over it
* the user presses a key
* the user drags and drops something
* the user submits a form
* content finishes loading
* a video starts or stops playing
* an error occurrs

and many more.

When an event happens it sends a signal which your code can react to.

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

This can become unmaintainable and inefficient. Just like with inline styles in CSS, if you change your mind later you have to go through your HTML and change every inline event handler one by one; and you might miss one. It's better to select elements and add event listeners in your seperate JavaScript file, where you can select multiple elements at the same time.

### The Event Object

Whenever you interact with the browser window, you create an event object. The event object has properties, such as the type of event (`click`, or `mousedown`), the target (`div` or `button`), and others. 




### Event Propagation and Bubbling

When you click on an element, you are really also clicking on its parent elements because they surround it. 

When you click on an element, the browser checks if it has an event handler attached to it and runs the handler. It then moves to the parent element and checks if it has an event handler, and repeats this until it reaches the `<html>` element. 

```html
<div class="one">
        <div class="two">
            <div class="three">
            </div>
        </div>
    </div>
```

```js
const divs = document.querySelectorAll("div");

function logDivs(e){
  console.log(this.classList.value);
}

divs.forEach(div => div.addEventListener("click", logDivs);
```

If you click on div three it will log `three, two, one` to the console. 

### Event Delegation

### References

["Introduction to events", MDN Web Docs](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/Events)

[Newman, Tovi "Let's meet the event object", LaunchSchool Medium Publication](https://medium.com/launch-school/javascript-lets-talk-about-events-572ecce968d0)

[Thakuria, Honey "Event Handling in JavaScript", freeCodeCamp Medium Publication](https://medium.freecodecamp.org/event-handling-in-javascript-with-examples-f6bc1e2fff57)

[Wilkie, Amber "A simplified explanation of event propagation in JavaScript", freeCodeCamp Medium Publication](https://medium.freecodecamp.org/a-simplified-explanation-of-event-propagation-in-javascript-f9de7961a06e)


