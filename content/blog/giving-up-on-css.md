---
layout: blog
title: " Giving up on Css"
date: 2021-11-26T17:56:04.587Z
description: ""
---
TL;DR 

In February 2020, I decided to teach myself Frontend development. I settled on two learning resources: [Freecodecamp](https://www.freecodecamp.org/) and [Frontend Masters](https://frontendmasters.com/) ([Github Student Developer Pack](https://education.github.com/pack)) and started out on my journey. \
\
The plan was to learn CSS, then learn some JavaScript, and eventually get into React to build out little projects.\
\
And I dived head first into it as seen from my activity map here:

![Freecodecamp activity](/images/uploads/freecodecamp.png)

It was great up until I started trying out challenges on [frontend mentor](https://www.frontendmentor.io/). My confidence immediately took a hit as things that seemed minor like the need for the reset below: 

```css
* {
  box-sizing: border-box;
}
html,
body {
  margin: 0;
  padding: 0;
}
```

Ultimately I built only one component, [the profile card component](https://www.frontendmentor.io/challenges/profile-card-component-cfArpWshJ). My version's code can be found on [GitHub](https://github.com/adrianmurage/profile-card-component) and deployed on [Github.io](https://adrianmurage.github.io/profile-card-component/). Here's an image, just to make your life a tad bit easier: 

![adrian murage's version of the profile card component ](/images/uploads/profile-card.png)

But somehow I gave up on learning how to use CSS for more complicated things. There were too many things that didn't make sense. 

If you view the deployed version, you'll notice one issue that I gave up on, making the circles on the top left and bottom right retain their position on larger screen sizes.