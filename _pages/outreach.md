---
layout: page
title: Outreach
permalink: /outreach/
description: Projects, datasets and pilots the DICE team has open-sourced!
nav: true
display_categories: [projects, datasets, demos]
horizontal: false
order: 2
---

<!-- <b>SAILING Members:</b> If you want to add your open-source project to this page, please refer to the <a href="https://github.com/sailing-lab/sailing-lab.github.io/blob/main/docs/open-source.md">instruction</a>. -->

Aiming to foster collaboration and drive progress within the research community, the team has compiled, curated, and released financial datasets and pilot applications. Moreover, it supervises MSc students on FinTech-related topics and participates in financial workshops and tasks.


<div class="projects">
  {% if site.enable_project_categories and page.display_categories %}
  <!-- Display categorized projects -->
    {% for category in page.display_categories %}
      <h2 class="category">{{ category }}</h2>
      {% assign categorized_projects = site.projects | where: "category", category %}
      {% assign sorted_projects = categorized_projects | sort: "importance" %}
      <!-- Generate cards for each project -->
      {% if page.horizontal %}
        <div class="container">
          <div class="row row-cols-2">
          {% for project in sorted_projects %}
            {% include projects_horizontal.html %}
          {% endfor %}
          </div>
        </div>
      {% else %}
        <div class="grid">
          {% for project in sorted_projects %}
            {% include projects.html %}
          {% endfor %}
        </div>
      {% endif %}
    {% endfor %}

  {% else %}
  <!-- Display projects without categories -->
    {% assign sorted_projects = site.projects | sort: "importance" %}
    <!-- Generate cards for each project -->
    {% if page.horizontal %}
      <div class="container">
        <div class="row row-cols-2">
        {% for project in sorted_projects %}
          {% include projects_horizontal.html %}
        {% endfor %}
        </div>
      </div>
    {% else %}
      <div class="grid">
        {% for project in sorted_projects %}
          {% include projects.html %}
        {% endfor %}
      </div>
    {% endif %}

  {% endif %}

</div>
