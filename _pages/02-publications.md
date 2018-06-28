---
layout: page
permalink: /publications/
title: publications
description: 
years: [2018, 2017, 2016, 2014]
---

{% for y in page.years %}

<h3 class="year">{{y}}</h3>

{% for paper in site.data.publications %}

{% if {{y}} == paper.year %}
<div width="100%" class="img_row">
<div class="profile col one left">
        <img width="25%" src="{{ paper.image | prepend: '/assets/img/' | prepend: site.baseurl | prepend: site.url }}" valign="top"> 
</div>
    <div valign="top">
  {{paper.authors | markdownify}}
  {% if paper.pmid %}
    <a href="https://www.ncbi.nlm.nih.gov/pubmed/{{paper.pmid}}" target="_blank">{{paper.title}}</a>
  {% elsif paper.pdf %}
    <a href="{{ paper.pdf | prepend: '/assets/pdf/' | prepend: site.baseurl | prepend: site.url }}" target="_blank">{{paper.title}}</a>
  {% else %}
    {{paper.title}}
  {% endif %}
  {{paper.details | markdownify}}
    </div>
</div>
{% endif %}
{% endfor %}
{% endfor %}

