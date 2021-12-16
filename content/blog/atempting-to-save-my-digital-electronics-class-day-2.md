---
layout: blog
title: Atempting to Save my Digital Electronics Class | Day 2
date: 2021-12-16T18:46:59.528Z
---
## Figuring out the Not Gate

The whole idea is to start from Nand and build out any other gate you would require from there. Took me a while to figure out. I think that has a lot to do with how tired I am as I try to do all this but yeah. In the end, the Not gate was achieved through fanning out one input to the Nand gate as shown below:

![](/images/uploads/screenshot-3-.png)

The resulting HDL code looked like this:
```hdl
// This file is part of www.nand2tetris.org
// and the book "The Elements of Computing Systems"
// by Nisan and Schocken, MIT Press.
// File name: projects/01/Not.hdl

/**
 * Not gate:
 * out = not in
 */

CHIP Not {
    IN in;
    OUT out;

    PARTS:
    // Put your code here:
    Nand(a=in, b=in, out=out);
}
```

I was pleased as now I have all I need to go forward with the rest of the gates.