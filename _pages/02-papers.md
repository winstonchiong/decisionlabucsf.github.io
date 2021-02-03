---
layout: page
permalink: /papers/
title: papers
description: 
years: [2021, 2020, 2019, 2018, 2017, 2016, 2014, 2013, 2011, 2010, 2007, 2006, 2005]
---

{% for y in page.years %}

<h3 class="year">{{y}}</h3>

{% for paper in site.data.publications %}

{% if y == paper.year %}
<div id = "{{ paper.title | replace: ' ', '-' | remove: '.' }}" class="clearfix" width="100%" style="padding-top: 5px; padding-bottom: 40px; clear: both;">
<img style="float: left; width: 25%; padding-right: 20px; padding-bottom:40px;" src="{{ paper.image | prepend: '/assets/img/' | prepend: site.baseurl | prepend: site.url }}" alt="publication image {% if paper.imagealt %}- {{paper.imagealt}}{% endif %}"> 
<div valign="top" style="overflow: hidden">
  {{paper.authors | markdownify | remove: '<p>' | remove: '</p>'}}<br>
  {% if paper.pmid %}
    <a href="https://pubmed.ncbi.nlm.nih.gov/{{paper.pmid}}" target="_blank">{{paper.title}}</a>
  {% elsif paper.file %}
    <a href="{{ paper.file | prepend: '/assets/papers/' | prepend: site.baseurl | prepend: site.url }}" target="_blank">{{paper.title}}</a>
  {% else %}
    {{paper.title}}
  {% endif %}
  {{paper.details | markdownify}}
  {% if paper.openaccess %}<i class="ai ai-open-access ai-fw"></i> <a href="{{paper.openaccess}}" target="_blank">Open Access</a><br>{% endif %}
  {% if paper.file %}<i class="far fa-file-alt fa-fw"></i> <a href="{{ paper.file | prepend: '/assets/papers/' | prepend: site.baseurl | prepend: site.url }}" target="_blank">{{paper.filetype}}</a><br>{% endif %}
  {% if paper.pmcid %}<i class="fas fa-landmark fa-fw"></i> <a href="https://www.ncbi.nlm.nih.gov/pmc/articles/{{paper.pmcid}}" target="_blank">PubMed Central {{paper.pmcid}}</a><br>{% endif %}
  {% if paper.contentshare %}<i class="fas fa-door-open fa-fw"></i> <a href="{{paper.contentshare}}" target="_blank">Content Sharing link</a><br>{% endif %}
  {% if paper.doi %}<i class="ai ai-doi ai-fw"></i> <a href="https://doi.org/{{paper.doi}}" target="_blank">{{paper.doi}}</a><br>{% endif %}
  {% if paper.github %}<i class="fab fa-github fa-fw"></i> <a href="{{paper.github}}" target="_blank">GitHub</a><br>{% endif %}
  {% if paper.biorxiv %}<i class="ai ai-biorxiv ai-fw"></i> <a href="{{paper.biorxiv}}" target="_blank">bioRxiv preprint</a><br>{% endif %}
  {% if paper.psyarxiv %}<i class="ai ai-psyarxiv ai-fw"></i> <a href="{{paper.psyarxiv}}" target="_blank">PsyArXiv preprint</a><br>{% endif %}  
  {% if paper.preregistered %}<i class="ai ai-preregistered ai-fw"></i> <a href="{{paper.preregistered}}" target="_blank">Preregistration</a><br>{% endif %}
  {% if paper.opendata %}<i class="ai ai-open-data ai-fw"></i> <a href="{{paper.opendata}}" target="_blank">Open Data</a><br>{% endif %}
  {% if paper.openmaterials %}<i class="ai ai-open-materials ai-fw"></i> <a href="{{paper.openmaterials}}" target="_blank">Open Materials</a><br>{% endif %}
    </div>
</div>

{% endif %}
{% endfor %}
{% endfor %}

