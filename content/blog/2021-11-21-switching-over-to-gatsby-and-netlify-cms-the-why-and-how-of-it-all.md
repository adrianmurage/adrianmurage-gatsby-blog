---
layout: blog
title: Switching Over to Gatsby and Netlify CMS. The Why and How of It All.
date: 2021-11-21T09:49:41.566Z
description: "Breakdown my exprience switching from Jekyll to Gatsby. "
---


In this post, I'll be going over:

* Why I am switching from Jekyll to Gatsby
* The technicalities of the switch
* The gotchas I came across

## Why stop using Jekyll to begin with

[Jekyll](https://jekyllrb.com/) was actually pretty good for my use case. But eventually, it all boiled down to two simple things. 

1. I wanted to move away from a technical writing process ie. have a CMS where I could quickly write up content.
2. I wanted the possibility of making a really impressive blog one day and the Gatsby option is being used by [JoshComeau](https://www.joshwcomeau.com/) and the React element of Gatsby has the promise to help make that a reality.
3. I vaguely remember trying to set up a CMS for my Jekyll blog and failing. I couldn't find a resource that had a good enough guide at the time. Is there a good chance I just didn't look in the right places? Yes. Am I going to go back there and keep looking? Nop

## Switching over to Gatsby

This part was actually surprisingly easy. I remember looking for React resources or how to create something in react and then finding an article by [Mohammed Asker](https://www.mohammedasker.com/) that walked through [How to Build a Blog with Gatsby and Netlify CMS – A Complete Guide](https://www.freecodecamp.org/news/how-to-build-a-blog-with-gatsby-and-netlify-cms/) and my mind went, "This is something I should do". And so on a random Sunday on week 11/14 of a semester where I have fallen so far behind it's scary, I decided to follow through the article and set up my Gatsby blog.

## Setup gotchas

I came across two of these that I think are worth mentioning. 

### 1. Git Gateway error

In the section where Mohammed mentions [How to configure the backend](https://www.freecodecamp.org/news/how-to-build-a-blog-with-gatsby-and-netlify-cms/#how-to-configure-the-back-end) it's important to note that the branch should be the same as your default branch which nowadays is mostly the `main` branch.

So the code snippet in that section in my case was:

```yaml
backend:
  name: git-gateway
  branch: main
```

The error came up when I tried to log in to my admin dashboard in the [how to access the cms](https://www.freecodecamp.org/news/how-to-build-a-blog-with-gatsby-and-netlify-cms/#how-to-access-the-cms) section.

The error was a GitGateway error and I found the solution on this [Netlify forum](https://answers.netlify.com/t/git-gateway-error/12220) 

### 2. CMS confirmation invite link not working

This particular error is mentioned by Mohammed in his article under the [how to access the cms](https://www.freecodecamp.org/news/how-to-build-a-blog-with-gatsby-and-netlify-cms/#how-to-access-the-cms) section.

To make it work seamlessly you would need to pay for Netlify to attain the ability of editing the links in Netlify's settings to route to the correct URL. 

If you are using the free version like me, you would need to use a hack.

The hack is simple: add the admin route to the URL like so:`https://yoursite.com/admin/#confirmation_token=random_characters`

## Bonus

When you're done with Mohammed's article and you try and create a post, you will realize that you actually cannot save drafts on and the only option availabe to you is to publish your work. 

This wasn't ideal for me as I like to create rough drafts, walk away from them and then come back with a fresh eye as an 'editor' to polish my work before publishing it to the interwebs. 

So at first, I was on the lookout for how to enable saving drafts when I came across the [Publish Mode](https://www.netlifycms.org/docs/configuration-options/#publish-mode) configuration option that was mentioned on the [Netlify Forum](https://answers.netlify.com/t/solved-how-can-i-save-my-post-as-draft/2672/3).

This feature actually gave me wayyy more than I bargained for and I think it works pretty well out of the box 

To enable it you simply add the below line of code in your `static/admin/config.yml`

```yaml
publish_mode: editorial_workflow
```

\
And that gives you an entire publication workflow tab where you can manage drafts, drafts under review and published articles.