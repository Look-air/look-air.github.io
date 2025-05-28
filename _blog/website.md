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
The easiest way was to just copy raw default.html from Modernist theme project and disable them. This also allowed me to change setting and enable zooming in on mobile devices (user-scalable=yes).
```html
<meta name="viewport" content="width=device-width, initial-scale=1, user-scalable=yes">
```

At this point I wanted to try out Github Desktop app https://github.com/apps/desktop
This app combined with Visual Studio Code, made it a lot smoother and easier to play around with multiple files and doing a batch commit and then a single push to the github server. 

Next thing I needed was to add a footer for every page, but the problem was I wanted to use Jekyll theme markdown language inside html code. I have tried:
```html
&#123;% raw %&#125;&#39;&#39;&#39;
© &#123;&#123; "now" | date: "%Y" &#125;&#125; All rights reserved.
&#123;% raw %&#125;&#39;&#39;&#39;
```
and
```html
{% capture footer_block %}
'''
© {{ "now" | date: "%Y" }} All rights reserved.
'''
{% endcapture %}
{{ footer_block | markdownify }}
```
None of them worked, they simply gave me a txt output without processing markdown footing theme notation.