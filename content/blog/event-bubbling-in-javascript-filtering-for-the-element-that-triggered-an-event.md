---
layout: blog
title: "Event Bubbling in JavaScript: Filtering for the Element That Triggered
  an Event"
date: 2021-04-29T07:41:00.000Z
---
## The task I am attempting

Hello! Today I'm tackling the JavaScript logic for the Frontend Masters [JavaScript, HTML, and CSS Calculator Project](https://btholt.github.io/intro-to-web-dev-v2/js-project).

## Thinking through it

The instructor introduced us to Event Bubbling and how it might be useful for such a scenario. 

How I understand event bubbling is:

For a scenario like mine where I'm listening for clicks. The browser checks the element that was clicked for a click event handler executes it then moves up to the immediate ancestor(the elements parent) and repeats.

This is especially useful for a case where you have several child elements. Where you can set one event listener on the parent that will register all events that happen on its child elements, regardless of the level of nesting.

For a broader explanation see this [MDN article on event bubbling](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/Events#event_bubbling_and_capture).


For my calculator, I have a container div with the class `calculator`, the container div is then subdivided into row divs with the class `row` and inside each row I have the relevant buttons.

At this particular point, I'm focusing on the numeric buttons. 

I would like to be able to listen for clicks on the numeric buttons. Once I accomplish that, I'll think through how to display the values on the calculators display.

To listen to the click events, I added an event listener to the container div. I then needed a way to target just the clicks made on the numeric buttons. 

At first, I didn't quite know how to target the clicks made on the numeric buttons. A few google searches later... I found a solution on the [gomakethings website](https://gomakethings.com/checking-event-target-selectors-with-event-bubbling-in-vanilla-javascript/).

Out of the suggested ways to target clicks, I ended up choosing to add a `numbers` class to all the numeric buttons. I would then use this class to filter for only the clicks that had it. 

```javascript
event.target.matches('.number')
```

The full solution is included in the codepen below:

{% include codepen.html hash="YzNbQOa" %}

Happy coding!