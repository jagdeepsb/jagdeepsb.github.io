---
layout: page
permalink: /fun/
title: fun
nav: fun
---

<p class="mb-4 font-weight-normal text d-flex justify-content-between align-items-center">
  <span>Things I've made outside of research</span>
  <a class="back-home" href="{{ '/' | prepend: site.baseurl | prepend: site.url }}">&larr; back home</a>
</p>

<div class="making-page p-0">
  {% assign make = site.making | reverse %}
  {% for item in make %}
    <div class="fun-card" id="{{ item.idd }}">
      <h4 class="font-weight-bold mb-1">{{ item.title }}</h4>
      {% if item.materials %}
        <div class="mb-2">
          <span class="bold-theme">Materials: </span>
          <span class="font-weight-normal"><i>{{ item.materials }}</i></span>
        </div>
      {% endif %}
      <div class="font-weight-normal fun-card-text">
        {{ item.content | remove: '<p>' | remove: '</p>' | emojify }}
      </div>
      <div class="fun-gallery">
        {% for img in item.imgs %}
          <img src="{{ img | prepend: '/assets/img/' | prepend: site.baseurl | prepend: site.url }}" alt="{{ item.title }}" loading="lazy">
        {% endfor %}
      </div>
    </div>
  {% endfor %}
</div>
