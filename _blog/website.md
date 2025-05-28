---
title: "Github Pages"
date: 2025-05-24
image: /images/blog/website.jpg
layout: default
---

# Building My GitHub Pages Site

The start was pretty straightforward. I needed a project to start something that can be visible. And there's nothing better than a website.
<!--more-->
I have used https://pages.github.com/ tutorial for a quick setup. It was really nice to see how fast deployment is on github hosting service. 
But since Hello World simple txt on white background is not exactly the type of what I had in mind, I decided to reasearch free Jekyll themes available on Github https://pages.github.com/themes/

After initial setup and tests I decided on using modernist theme. However I wanted some modifications, like my own buttons, and I didn't want to have the default ones made by theme. 
The easiest way was to just copy raw default.html from Modernist theme project and disable them. This also allowed me to change setting and enable zooming in on mobile devices (user-scalable=yes).
```html
<meta name="viewport" content="width=device-width, initial-scale=1, user-scalable=yes">
```

At this point I wanted to try out Github Desktop app https://github.com/apps/desktop
This app combined with Visual Studio Code, made it a lot smoother and easier to play around with multiple files and doing a batch commit and then a single push to the github server. 

With this I did other pages like contact and blog. All in markdown, with some html. For the index page I wanted to use vector graphics of logos I got from CompTIA after passing their certs. For this I asked copilot to help me out with proper way to reduce their size and center them in row. This ended in creation of style.scss that has details about classes like avatar, logos and buttons. 

Contact page is just details on how to reach me, so nothing fancy there, just a couple of links.
Index page is mostly a welcome/about me site, with a showcase of certifications.
Blog is the one I will be propably having the most fun with. This post is first from many to come I hope :)

At this stage webpage was simple. I do want to add a page with resources featuring all software that is useful, similar page with links. But the thing I want to create now is adding pagination to blog, so it can feature up to few posts and then present a button for next/previous page. Also I need to work out a good way to present these posts with date, title and miniature. Thanks for reading. 