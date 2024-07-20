---
layout: page
permalink: /publications/
title: publications
description: Publications of the aLLMA Lab team (since 2024).
years: [2024]
nav: true
---

<div class="publications">

{% for y in page.years %}
  <h2 class="year">{{y}}</h2>
  {% bibliography -f papers -q @*[year={{y}}]* %}
{% endfor %}

</div>
