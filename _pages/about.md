---
title: "Home"
layout: gridlay
sitemap: false
permalink: /
---

<style>
.jumbotron{
    padding:3%;
    padding-bottom:10px;
    padding-top:10px;
    margin-top:10px;
    margin-bottom:30px;
}
</style>

{% for member in site.data.pi %}
<div class="jumbotron">
<div class="row">
<div class="col-sm-4">
  <img src="{{ site.url }}{{ site.baseurl }}/images/teampic/{{ member.photo }}" width="100%" style="max-width:250px"/>
</div>
<div class="col-sm-8 col-xs-12">
  <h3>{{ member.name }}</h3>
  <h4><i>{{ member.info }}</i></h4>
  {% if member.email %}<a href="mailto:{{ member.email }}" target="_blank"><i class="fa fa-envelope-square fa-3x"></i></a> {% endif %}
  {% if member.cv %} <a href="{{ site.url }}{{ site.baseurl }}/{{ member.cv }}" target="_blank"><i class="ai ai-cv-square ai-3x"></i></a> {% endif %}
  {% if member.scholar %} <a href="{{ member.scholar }}" target="_blank"><i class="ai ai-google-scholar-square ai-3x"></i></a> {% endif %}
  {% if member.github %} <a href="{{ member.github }}" target="_blank"><i class="fa fa-github-square fa-3x"></i></a> {% endif %}
  {% if member.researchgate %} <a href="{{ member.researchgate }}" target="_blank"><i class="ai ai-researchgate-square ai-3x"></i></a> {% endif %}

  <h6>{{ member.short_intro }}</h6>
  <ul style="overflow: hidden">
  {% if member.number_educ == 1 %}
  <li> {{ member.education1 | replace: "-","&#8211;"}} </li>
  {% endif %}
  {% if member.number_educ == 2 %}
  <li> {{ member.education1 | replace: "-","&#8211;"}} </li>
  <li> {{ member.education2 | replace: "-","&#8211;"}} </li>
  {% endif %}
  {% if member.number_educ == 3 %}
  <li> {{ member.education1 | replace: "-","&#8211;"}} </li>
  <li> {{ member.education2 | replace: "-","&#8211;"}} </li>
  <li> {{ member.education3 | replace: "-","&#8211;"}} </li>
  {% endif %}
  {% if member.number_educ == 4 %}
  <li> {{ member.education1 | replace: "-","&#8211;"}} </li>
  <li> {{ member.education2 | replace: "-","&#8211;"}} </li>
  <li> {{ member.education3 | replace: "-","&#8211;"}} </li>
  <li> {{ member.education4 | replace: "-","&#8211;"}} </li>
  {% endif %}
  {% if member.number_educ == 5 %}
  <li> {{ member.education1 | replace: "-","&#8211;"}} </li>
  <li> {{ member.education2 | replace: "-","&#8211;"}} </li>
  <li> {{ member.education3 | replace: "-","&#8211;"}} </li>
  <li> {{ member.education4 | replace: "-","&#8211;"}} </li>
  <li> {{ member.education5 | replace: "-","&#8211;"}} </li>
  {% endif %}
  {% if member.number_educ == 6 %}
  <li> {{ member.education1 | replace: "-","&#8211;"}} </li>
  <li> {{ member.education2 | replace: "-","&#8211;"}} </li>
  <li> {{ member.education3 | replace: "-","&#8211;"}} </li>
  <li> {{ member.education4 | replace: "-","&#8211;"}} </li>
  <li> {{ member.education5 | replace: "-","&#8211;"}} </li>
  <li> {{ member.education6 | replace: "-","&#8211;"}} </li>
  {% endif %}
  </ul>
</div>
</div>
</div>
{% endfor %}

{% if site.data.awards %}
<div class="jumbotron">
### Awards and Grants
<ul>
{% for award in site.data.awards %}
 <li> {{ award.name | replace: "-","&#8211;"}} </li>
{% endfor %}
</ul>
</div>
{% endif %}


{% if site.data.news %}
<div class="jumbotron">
### News
<ul>
{% for article in site.data.news %}
 <li> {{ article.headline }} </li>
{% endfor %}
</ul>
</div>
{% endif %}


{% if site.data.seminars %}
<div class="jumbotron">
### Seminars
<ul>
{% for article in site.data.seminars %}
 <li> {{ article.headline }} </li>
{% endfor %}
</ul>
</div>
{% endif %}


<div class="jumbotron">
### Preprints, Journal and Conference Papers
{% bibliography --query @misc %}
{% bibliography --query @inproceedings %}
</div>

<div class="jumbotron">
### Regular and invited talks
{% bibliography --query @incollection[keywords ^= invited] %}
{% bibliography --query @incollection[keywords != invited] %}
</div>

<div class="jumbotron">
### Teaching

* Lecturer (Teaching Fellow), École des Mines de Saint-Étienne (EMSE) 
    * Big data clustering --Jan, 2022
    * Introduction to Natural Language Processing (NLP) -- Jan, 2022

* Teaching Assistant, École des Mines de Saint-Étienne (EMSE) 
    * Deep Learning practical class --2021
</div>


<div class="jumbotron">
### Services

* Reviewer
    * WiML, IEEE CASE, EMNLP, AISTATS.

* Volunteering
    * (April 25-20, 2022) The 10th International Conference on Learning Representations (<a href='https://iclr.cc/Conferences/2022' target='_blank'>ICLR-22</a>)
    * (March 28-30, 2022) The 25th International Conference on Artificial Intelligence and Statistics (<a href='http://aistats.org/aistats2022/' target='_blank'>AISTATS-22</a>)
    * (Aug. 23-27, 2021) IEEE International Conference on Automation Science and Engineering (<a href='https://case2021.sciencesconf.org/' target='_blank'>IEEE CASE-21</a>)
    * (Oct. 2020 - 2021) Mentor on AI for Coral Reef Conservation in the Vamizi Island, Mozambique (<a href='https://fecn.unilurio.ac.mz/en/ai-coralreef/' target='_blank'>AI for Coral Reef</a>)
    * (April 13-15, 2021) The 24th International Conference on Artificial Intelligence and Statistics (<a href='https://case2021.sciencesconf.org/' target='_blank'>AISTATS-21</a>)
* Affiliations
    * Blacks in AI, Masakhane.
</div>


<div class="jumbotron">
  <h4>Sponsors</h4>
  <div style='display:block; text-align:center; margin-left:auto; margin-right:auto;'>
 {% for funder in site.data.funders %}<a href="{{ funder.url }}" target="_blank"><img src='{{ site.url }}{{ site.baseurl }}/images/logopic/{{ funder.image }}' style='max-height: 80px; max-width: 200px; margin: 1%'/></a>{% endfor %}
  </div>
</div>
