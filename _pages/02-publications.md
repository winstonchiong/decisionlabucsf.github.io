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
<div id = "{{paper.title}}" class="clearfix" width="100%" style="padding-top: 5px; padding-bottom: 40px; clear: both;">
<img style="float: left; width: 25%; padding-right: 20px; padding-bottom:40px;" src="{{ paper.image | prepend: '/assets/img/' | prepend: site.baseurl | prepend: site.url }}" alt="publication image"> 
<div valign="top" style="overflow: hidden">
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

