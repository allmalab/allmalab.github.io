---
layout: team
permalink: /projects/
title: projects
description:
nav: true
---
{% for project in site.data.projects %}
  <!-- <div style="background-color: {{ project.color }}"> -->
  <div>
  <section class="section">
    {% if project.image %}
    <img src="/assets/img/team/{{ project.image }}" alt="person thumbnail" class="projectimage"/>
    {% endif %}
    <div class="content">
    
    <p class="paragraph">
    <div class="card-body">
      <h2 class="card-title">{{ project.name }}</h2>
      <p class="card-text">{{ project.description }}</p>
      {% if project.deliverables %}
      <div class="deliverables" style="background-color: #f0f0f0; padding: 15px; border-radius: 5px; font-size: 15px; line-height: 1.3;">
        <h3>Deliverables:</h3>
        <ul>
          {% for deliverable in project.deliverables %}
            <li>{{ deliverable }}</li>
          {% endfor %}
        </ul>
      </div>
      {% endif %}
      <!-- <p class="card-text">Read more <a href="/projects/{{ project.link }}">here</a>.</p> -->
    </div>
    </p>
    </div>
  </section>
  </div>
  <br>
{% endfor %}
