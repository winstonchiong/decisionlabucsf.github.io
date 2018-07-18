---
layout: page
permalink: /papers/
title: papers
description: 
years: [2018, 2017, 2016, 2014, 2013, 2011, 2010, 2007, 2006, 2005]
---

{% for y in page.years %}

<h3 class="year">{{y}}</h3>

{% for paper in site.data.publications %}

{% if y == paper.year %}
<div id = "{{paper.title}}" class="clearfix" width="100%" style="padding-top: 5px; padding-bottom: 40px; clear: both;">
<img style="float: left; width: 25%; padding-right: 20px; padding-bottom:40px;" src="{{ paper.image | prepend: '/assets/img/' | prepend: site.baseurl | prepend: site.url }}" alt="publication image {% if paper.imagealt %}- {{paper.imagealt}}{% endif %}"> 
<div valign="top" style="overflow: hidden">
  {{paper.authors | markdownify | remove: '<p>' | remove: '</p>'}}<br>
  {% if paper.pmid %}
    <a href="https://www.ncbi.nlm.nih.gov/pubmed/{{paper.pmid}}" target="_blank">{{paper.title}}</a>
  {% elsif paper.pdf %}
    <a href="{{ paper.pdf | prepend: '/assets/pdf/' | prepend: site.baseurl | prepend: site.url }}" target="_blank">{{paper.title}}</a>
  {% else %}
    {{paper.title}}
  {% endif %}
  {{paper.details | markdownify}}
  {% if paper.pmcid %}<i class="ai ai-open-access"></i> <a href="https://www.ncbi.nlm.nih.gov/pmc/articles/{{paper.pmcid}}" target="_blank">PubMed Central {{paper.pmcid}}</a><br>{% endif %}
  {% if paper.doi %}<i class="ai ai-doi"></i> <a href="https://doi.org/{{paper.doi}}" target="_blank">https://doi.org/{{paper.doi}}</a><br>{% endif %}
  {% if paper.github %}<i class="fab fa-github"></i> <a href="{{paper.github}}" target="_blank">GitHub</a><br>{% endif %}
  {% if paper.osf %}<i class="ai ai-osf"></i> <a href="{{paper.osf}}" target="_blank">Open Science Framework</a><br>{% endif %}
    </div>
</div>

{% endif %}
{% endfor %}
{% endfor %}

