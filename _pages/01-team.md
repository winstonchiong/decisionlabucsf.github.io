---
layout: page
permalink: /team/
title: team
description: 
---

{% for person in site.data.members %}

<!-- The paddingtop and margin-top edits allow anchors to link properly. -->
<div id = "{{person.name}}" class="row" style="padding-top: 60px; margin-top: -60px;">
    <img class="col one right" src="{{ person.image | prepend: '/assets/img/' | prepend: site.baseurl | prepend: site.url }}">
    <div>
        <h4>{{person.name}}</h4> <br>
        {{person.position}} <br>
        <em>{{person.email}}</em> <br>
        {% if person.website %}
          <a href= "{{person.website}}">{{person.website}}</a> <br>
        {% endif %}
        {% if person.orcid %}
          <a href="http://orcid.org"><img class="inline-block" src="/static/img/orcid_logo.png"></a>
          <a href="http://{{person.orcid}}"> {{person.orcid}}</a> <br>
        {% endif %}
        {% if person.scholar %}
          <a href= "http://scholar.google.com/citations?user={{person.scholar}}"> Scholar Citations </a> <br>
        {% endif %}
        {% if person.twitter %}
          <a href= "http://twitter.com/{{person.twitter}}"> @{{person.twitter}} </a> <br>
        {% endif %}
    </div>
    <div class="col-sm-8">
        <p class="text-justify">{{person.description | markdownify}}</p>
    </div>
</div>
<hr>
{% endfor %}


### students
{% for student in site.data.students %}

<!-- The paddingtop and margin-top edits allow anchors to link properly. -->
<div id = "{{student.name}}" class="row" style="padding-top: 60px; margin-top: -60px;">
  <b>{{student.name}}</b> <br>
  {{student.position}} <br>
  <em>{{student.email}}</em> <br>
  {{student.description | markdownify}}
</div>

{% endfor %}