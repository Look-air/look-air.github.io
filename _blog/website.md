---
title: "Github Pages"
date: 2025-05-24
image: /images/blog/website.jpg
excerpt: "Time has come to start my own website."
layout: default
---

# Building My GitHub Pages Site

The start was pretty straightforward. I needed a project to start something that can be visible. And there's nothing better than a website.

I have used https://pages.github.com/ tutorial for a quick setup. It was really nice to see how fast deployment is on github hosting service. 
But since Hello World simple txt on white background is not exactly the type of what I had in mind, I decided to reasearch free Jekyll themes available on Github https://pages.github.com/themes/

After initial setup and tests I decided on using modernist theme. However I wanted some modifications, like my own buttons, and I didn't want to have the default ones made by theme. 
The easiest way was to just copy raw default.html from Modernist theme project and disable them. This also allowed me to change setting and enable zooming in on mobile devices.
```html
<meta name="viewport" content="width=device-width, initial-scale=1, user-scalable=yes">
```

At this point I wanted to try out Github Desktop app https://github.com/apps/desktop
This combined with Visual Studio Code, which I used previously for CS50 Introduction to Python Course, made it a lot smoother and easier to play around with multiple files and doing a batch commit