---
layout: page
permalink: /publications/
title: publications
description: 
years: [2018, 2017, 1935, 1905]
---

{% for y in page.years %}
  <h3 class="year">{{y}}</h3>
  {% for paper in site.data.publications %}
    {% if paper.year == {{y}} %}
<div class="row" style="padding-top: 60px; margin-top: -60px;">
<img class="col one left" src="{{ paper.image | prepend: '/assets/img/' | prepend: site.baseurl | prepend: site.url }}">
{{paper.citation | markdownify}}
</div>

    {% endif %}
  {% endfor %}
{% endfor %}
