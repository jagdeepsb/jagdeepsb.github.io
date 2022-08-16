---
layout: page
permalink: /
title: about
nav: about
years: [2022, 2021]

# <!--description: <a href="https://ai.google/" target="_blank">Google AI</a> -->
# address: <a href="https://www.google.com/maps/place/Googleplex/@37.4220656,-122.0862837,17z/data=!3m1!4b1!4m5!3m4!1s0x808fba02425dad8f:0x6c296c66619367e0!8m2!3d37.4220656!4d-122.0840897" class="page-description" target="_blank">Googleplex, Mountain View, California, USA </a>
---

<div class="col p-0 pt-4 pb-4">
  <h1 class="pb-3 title text-left font-weight-bold" id="ABOUT">Jagdeep Singh Bhatia</h1>
  <h6 class="m-0 mb-2" style="font-size: 0.83em;">{{ page.description }}</h6>
  {% if page.address %}
      <h6 class="m-0 mb-2" style="font-size: 0.83em;">{{ page.address }}</h6>
  {% endif %}
</div>

<!-- Introduction -->

<div style="display: flex; flex-wrap: wrap;">
    <div class="text-justify p-0">
        <div class="col-xs-12 col-sm-6 p-0 pt-2 pb-sm-2 pb-4 pl-sm-4 text-center" style="float: right;">
          <img class="profile-img img-responsive" style="width: 90%;" src="{{ 'me.jpg' | prepend: '/assets/img/' | prepend: site.baseurl | prepend: site.url }}">
        </div>

        <p>
            Hey there! I'm Jagdeep, a sophomore at MIT studying computer science. 
        </p>

        <p>
            I'm interested in thinking about some of the more nuanced problems in AI (interpretability, robustness, generalizability) and applying those ideas to designing intelligent embodied systems. I'm really proud of 
            <a href="https://evolutiongym.github.io/" target="_blank">EvoGym</a>,
            a benchmark for design and control co-optimization for voxel-based soft robots which I built with the 
            <a href="https://cdfg.mit.edu/" target="_blank">Computational Design and Fabrication Group</a>
            at MIT. I spent this winter designing debiasing algorithms at 
            <a href="https://themisai.io/" target="_blank">Themis AI</a>,
            and this summer, I'll be working on similar challenges at 
            <a href="https://scale.com/" target="_blank">Scale</a>. My work has been featured in Scientific American, Wired, Forbes, IEEE Spectrum, and MIT News. 
        </p>
    </div>
</div>

<div class="col text-justify p-0">
    <p>
        In my free time I love running, playing card games, and making bad puns.
    </p>
</div>

<!-- News -->

<div class="news mt-3 p-0" id="NEWS">
  <h1 class="title mb-4 p-0">news</h1>
  {% assign news = site.news | reverse %}
  {% for item in news limit: site.news_limit %}
    <div class="row p-0">
      <div class="col-sm-2 p-0">
        <!-- <span class="badge light-green darken-1 font-weight-bold text-uppercase align-middle date ml-3">
          {{ item.date | date: "%b %-d, %Y" }}
        </span> -->
        <span class="badge burgundy font-weight-bold text-uppercase align-middle date ml-3">
          {{ item.date | date: "%b %Y" }}
        </span>
      </div>
      <div class="col-sm-10 mt-2 mt-sm-0 ml-3 ml-md-0 p-0 font-weight-light text">
        <p>{{ item.content | remove: '<p>' | remove: '</p>' | emojify }}</p>
      </div>
    </div>
  {% endfor %}
</div>

<!-- publications -->

<br/>
<div class="news mt-3 p-0" id="PUB">
  <h1 class="title mb-4 p-0">publications</h1>
  {% for y in page.years %}
    <div class="row m-0 p-0" style="border-top: 1px solid #ddd; flex-direction: row-reverse;">
      <div class="col-sm-1 mt-2 p-0 pr-1">
        <h3 class="bibliography-year">{{y}}</h3>
      </div>
      <div class="col-sm-11 p-0">
        {% bibliography -f papers -q @*[year={{y}}]* %}
      </div>
    </div>
  {% endfor %}
</div>