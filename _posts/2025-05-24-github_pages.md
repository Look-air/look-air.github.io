---
title: "Github Pages is awesome"
date: 2025-05-24
image: /images/logos/github.png
excerpt: "The start was pretty straightforward. I needed a project to start something that can be visible. And there's nothing better than a website."
layout: blog
---
<img src="/images/blog/github_pages/website.jpg" alt="Image description" class="responsive-image">
<h1 style="margin-bottom: 5px;">{{ page.title }}</h1>
<p style="font-size: 0.9em; color: #666; margin-top: 0;">{{ page.date | date: "%B %d, %Y" }}</p>
The start was pretty straightforward. I needed a project to start something that could be visible. And there's **nothing better than a website**. After quick google search I cam across [**GitHub Pages**](https://pages.github.com/), not only it was free but I already had a Github account from CS50P certification. 

So without much waiting I used their tutorial for a quick setup. Just creating new repository with **username.github.io** where username is **your** username. And then adding simple index.md file inside root of that repository. That file could have somehting simple as "Hello" inside of it. Save it, wait few minutes for page rebuild and visit your site at username.github.io That's how simple it was. 

<img src="/images/blog/github_pages/repo_name.png" alt="Image description" class="responsive-image">

It was also really nice to see how fast deployment is on GitHub’s hosting service, didn't even wait a minute and it was ready. But since a Hello World simple text on a white background is not exactly what I had in mind, I decided to check out the free Jekyll themes available on GitHub [**here**](https://pages.github.com/themes/).

After the initial setup and tests, I decided to use the Modernist theme.
```yaml
# _config.yaml
remote_theme: pages-themes/modernist@v0.2.0
plugins:
  - jekyll-remote-theme
```

However, I wanted some modifications—like my own buttons—and I didn't want to have the default ones provided by the theme. The easiest way was to copy the raw default.html from the Modernist theme project and disable them. This also allowed me to change settings and enable zooming on mobile devices, just find this **user-scalable=yes** in your _layouts\default.html and edit.
```html
<meta name="viewport" content="width=device-width, initial-scale=1, user-scalable=yes">
```

At this point, I wanted to try out the [**Github Desktop App**](https://www.virtualbox.org/). This app, combined with [**Visual Studio Code**](https://code.visualstudio.com/), made it a lot smoother and easier to play around with multiple files, doing a batch commit, and then a single push to the GitHub server. Also managing files like images and just copying them to the local repository structure made a difference in overal experience of building a site.

With this setup, I created other pages like Contact and Blog—all in Markdown with some HTML. For the index.md page, I wanted to use vector graphics of logos I got from CompTIA after passing their certs. For this, I asked Copilot to help me out with the proper way to reduce their size and center them in a row. This ended in the creation of a style.scss file that contains details about classes like avatar, logos, and buttons.

The Contact page is just details on how to reach me, so nothing fancy there-just a couple of links. The index.md page is mostly a welcome/about-me site, with a showcase of certifications. The Blog is the section I will probably have the most fun with. I hope this post is the first of many to come :)

Thanks to the great [**Guide for Jekyll**](https://jekyllrb.com), I was able to set up a proper blog system. I added pagination (in _config.yaml) to the blog so that it can feature a few posts per page and then display buttons for next/previous page. This has to be added in your \blog\index.html which is not the same index.md that is present in root of repository (our home page). By the way the index file in \blog folder needs to be HTML, markdown file will not work with pagination, I have learned that the hard way :)
```yaml
# _config.yaml
paginate: 5
paginate_path: "/blog/page:num"
```
I also made a few test posts to see how the layout would look and if the next/previous page buttons would function correctly. During that testing, I made the mistake of creating files with future dates, which made them invisible. After fixing the dates, everything worked. Currently there are no longer test posts present in my repo, after testing there was no point in keeping them.

Last but not least, I decided to buy a cheap domain—this was a good test of configuring DNS TXT, **A**, and **CNAME** records.

<img src="/images/blog/github_pages/CNAME.png" alt="Image description" class="responsive-image">

For now, that would be all.

**I plan on adding:**

* Latest blog post miniature on the home page

* A page with resources featuring all the software that is useful

* A similar page with useful links

* Redesigned buttons, since there might be more than three

Thanks for reading.

<img src="/images/logos/github.png" alt="Image description" class="responsive-image">