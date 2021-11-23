---
layout: blog
title: "Codewars | Directions Reduction | JavaScript Solution "
tags:
  - practice
published: true
date: 2021-05-08T07:45:31.843Z
---
This kata got you struggling too huh? Don't stress I got you.

For good measure, if you're just passing by and have no idea what this is, you can find the kata instructions on [Codewars](https://www.codewars.com/kata/550f22f4d758534c1100025a/train/javascript).

## My solution.

I broke it down into these steps:

1. loop through the values of the array
2. identify invalid directions {North next to South} and {East next to west West}
3. remove invalid directions from the array
4. if there still exists invalid directions after completing the loop restart the loop. Else terminate the loop

I struggled for a while trying to figure out how to restart the loop. Eventually, I settled on a while loop. Where the while loop's control statement is a function that checks for the presence of invalid directions and returns a boolean.

like so:

```javascript
function dirReduc(arr) {
  // function to check for the presence of invalid directions
  function hasInvalidDirections(array) {
    count = 0;
    for (let i = 0; i < array.length - 1; i++) {
      if (
        (array[i] === "NORTH" && array[i + 1] === "SOUTH") ||
        (array[i] === "SOUTH" && array[i + 1] === "NORTH") ||
        (array[i] === "EAST" && array[i + 1] === "WEST") ||
        (array[i] === "WEST" && array[i + 1] === "EAST")
      ) {
        count++;
      }
    }
    return count > 0;
  }

  // while loop to restart the the nested for-loop
  while (hasInvalidDirections(arr)) {
    for (let i = 0; i < arr.length; i++) {
      if (
        (arr[i] === "NORTH" && arr[i + 1] === "SOUTH") ||
        (arr[i] === "SOUTH" && arr[i + 1] === "NORTH") ||
        (arr[i] === "EAST" && arr[i + 1] === "WEST") ||
        (arr[i] === "WEST" && arr[i + 1] === "EAST")
      ) {
        arr.splice(i, 2);
      }
    }
  }

  return arr;
}
```

## Other Solutions

I found these on the internet and thought they were interesting. So I'm leaving them here. When I cover the necessary topics I might come back to them. Hopefully I'll be able to grok them then.

One by [Andrew Losseff](https://losseff.xyz/katas/021-directions-reduction/javascript/).

And this one that was top voted in the kata solutions board:

```javascript
function dirReduc(plan) {
  var opposite = {
    NORTH: "SOUTH",
    EAST: "WEST",
    SOUTH: "NORTH",
    WEST: "EAST",
  };
  return plan.reduce(function (dirs, dir) {
    if (dirs[dirs.length - 1] === opposite[dir]) dirs.pop();
    else dirs.push(dir);
    return dirs;
  }, []);
}
```

This [freecodecamp forum discussion](https://forum.freecodecamp.org/t/stumped-on-this-kata-directions-reduction/240974/9) explains the use of a stack to solve the kata.

And that's it for today folks.
Happy coding!