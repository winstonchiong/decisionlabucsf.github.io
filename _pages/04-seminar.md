---
layout: default
title: seminar
permalink: /seminar/
description: 
---

<div class="post">
  <header class="post-header">
    <h1 class="post-title">{{ page.title }}</h1>
    <h5 class="post-description">{{ page.description }}</h5>
     <p> From May 2016 to March 2020 we co-hosted a twice-monthly Neuroethics 
     Seminar with <a href="https://publichealth.gsu.edu/profile/jalayne-arias/" 
      target="_blank">Jalayne Arias</a> at the UCSF Mission Bay campus. The aim 
      of the seminar was to engage neuroscientists and clinicians in broad, 
      interdisciplinary conversations about ethical and policy issues arising in 
      their work. These meetings generally followed one of three formats: (1) 
      case discussions arising from ethically complex clinical encounters or 
      research developments, (2) journal clubs drawn either from recent 
      neuroscience or neuroethics literature, and (3) works-in-progress to 
      refine upcoming grants, conference abstracts and manuscripts. </p>
      
      <p>These meetings were paused due to the COVID-19 pandemic, and 
      have since ended following Professor Arias's move to the Georgia State 
      School of Public Health. For current forums for discussion of ethical 
      issues in the biosciences, please see the events listed at 
      <a href="https://bioethics.ucsf.edu" target="_blank">bioethics.ucsf.edu</a>.
      </p>
  </header>

  <h2>meeting summaries: </h2>
  {% for session in site.pastsem reversed %}

  {% if forloop.index == 6 %}
    {% break %}
  {% endif %}

  {% if forloop.index != 1 %}
    <hr>
  {% endif %}

  <h3 id="{{session.date | date: "%Y-%m-%d" }}"><a href="{{ session.url }}">{{ session.title }}</a></h3>
  <p class="author">
    <span class="author">{{session.presenters}}</span><br>
    <span class="date"><em>{{ session.date | date: "%B %e, %Y" }}</em></span>
  </p>
  {% if session.image %}
  <div class="sem-image-container">
    <img style="width: 80%;" src="{{ session.image | prepend: '/assets/img/' | 
    prepend: site.baseurl | prepend: site.url }}" alt="photo of {{session.title}}">
    {% if session.caption %}
    <div class="image-caption">{{ session.caption }}</div>
    {% endif %}
  </div>
  {% endif %}
  <div class="content">
    {{ session.content }}
  </div>
  {% endfor %}
</div>

{% if site.pastsem.size > 5 %}
  {% assign mylimit = site.pastsem.size | minus: 5 %}
  <hr>
  <h2>previous meetings: </h2>

  {% for session in site.pastsem reversed limit:mylimit %}
<em>{{ session.date | date: "%B %e, %Y" }}</em> - <a href="{{ session.url }}">{{ session.title }}</a> ({{ session.presenters }})

  {% endfor %}

{% endif %}

<em>May 14, 2018</em> - Opioids in elder populations (Monroe Butler)

<em>April 16, 2018</em> - Patient and caregiver perspectives on physician assisted death in ALS (Catherine Lomen-Hoerth)

<em>April 2, 2018</em> - FAA regulations and preclinical Alzheimer's biomarkers (Matt Lawrence)

<em>March 25, 2018</em> - California End of Life Option Act working meeting

<em>March 12, 2018</em> - Brain death and the Jahi McMath case (Sharon Kaufman)

<em>February 12, 2018</em> - Cognitive testing and political leaders (Jalayne Arias)

<em>January 25, 2018</em> - Palliative medicine (Krista Harrison)

<em>January 11, 2018</em> - Ethical issues in the management of patients with dementia (Winston Chiong)



