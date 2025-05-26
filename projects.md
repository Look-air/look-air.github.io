---
layout: default
title: "Projects"
---

<h1 style="text-align:center;">Projects</h1>

<h5 style="text-align:center;">Welcome to my projects page. Below you’ll find a list of my work with a brief overview, a project image, and the date of the project’s release.</h5>

<ul class="projects-list" style="list-style: none; padding: 0;">
  {% for project in site.projects %}
  <li class="project-item" style="margin-bottom:20px;">
    <a href="{{ project.url }}" style="text-decoration: none; color: inherit;">
      <div style="display: flex; align-items: center; border-bottom: 1px solid #DDD; padding-bottom: 10px; margin-bottom: 10px;">
        {% if project.image %}
        <img src="{{ project.image }}" alt="{{ project.title }}" style="width: 100px; height: 100px; object-fit: cover; margin-right: 20px;">
        {% endif %}
        <div class="project-info">
          <h2 style="margin: 0;">{{ project.title }}</h2>
          <p class="project-date" style="font-size: 0.9em; color: #666;">{{ project.date | date: "%B %d, %Y" }}</p>
          <p>{{ project.excerpt }}</p>
        </div>
      </div>
    </a>
  </li>
  {% endfor %}
</ul>
