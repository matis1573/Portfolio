---
layout: page
title: Projets
permalink: /projects/
---

# Mes Projets

Voici mes derniers projets.

<div class="projects-grid" style="display: grid; grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); gap: 20px;">
  
  {% for post in site.categories.projet limit:3 %}
  <a href="{{ post.url | relative_url }}" class="project-card" style="border: 1px solid #333; padding: 20px; border-radius: 8px; text-decoration: none; display: block; color: inherit;">
    <h3 style="margin-top: 0;">{{ post.title }}</h3>
    <p>{{ post.description }}</p>
    <span class="btn">Voir le projet</span>
  </a>
  {% endfor %}

</div>
