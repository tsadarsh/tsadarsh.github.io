---
layout: page
title: Projects
permalink: /projects/
---

Here are some of the projects I've worked on. Feel free to explore them on my GitHub!

<div class="projects-grid">
  {% assign projects = site.data.projects %}
  {% for project in projects %}
  <div class="project-card">
    <h3>{{ project.title }}</h3>
    <p>{{ project.description }}</p>
    <div>
      {% for link in project.links %}
        <a href="{{ link.url }}" class="project-link" target="_blank">{{ link.label }}</a>
      {% endfor %}
    </div>
    {% if project.tags %}
    <div class="project-tags">
      {% for tag in project.tags %}
        <span class="project-tag">{{ tag }}</span>
      {% endfor %}
    </div>
    {% endif %}
  </div>
  {% endfor %}
</div>

## Project Ideas

I'm always working on new things! If you're interested in collaborating or have project ideas, feel free to reach out on [GitHub](https://github.com/tsadarsh){:target="_blank"} or [LinkedIn](https://www.linkedin.com/in/tsadarsh/){:target="_blank"}.
