---
title: "CoNI Lab - Team"
layout: gridlay
excerpt: "CoNI Lab: Team members"
sitemap: false
permalink: /team/
---

# Group Members


Jump to [staff](#staff), [alumni](#alumni),
[lab affiliates](#lab-affiliates), [collaborators](#collaborators).


## Staff
{% assign number_printed = 0 %}
{% for member in site.data.team_members %}

{% assign even_odd = number_printed | modulo: 2 %}

{% if even_odd == 0 %}
<div class="row">
{% endif %}

<div class="col-sm-6 clearfix">
{% if member.name != 0 %}
{% if member.personalweb  %}
<a href="{{ member.personalweb }}" target="_blank"><img src="{{
site.url }}{{ site.baseurl }}/images/teampic/{{ member.photo }}"
class="img-responsive" width="25%" style="float: left" /></a>
{% else %}
<img src="{{ site.url }}{{ site.baseurl }}/images/teampic/{{ member.photo }}" class="img-responsive" width="25%" style="float: left" />
{% endif %}
  <h4>{{ member.name }}</h4>
  <i>{{ member.info }}<br>email: <{{ member.email }}></i>
{% endif %}
  <ul style="overflow: hidden">


		 
  {% if member.number_educ == 1 %}
  <li> {{ member.education1 }} </li>
  {% endif %}

  {% if member.number_educ == 2 %}
  <li> {{ member.education1 }} </li>
  <li> {{ member.education2 }} </li>
  {% endif %}

  {% if member.number_educ == 3 %}
  <li> {{ member.education1 }} </li>
  <li> {{ member.education2 }} </li>
  <li> {{ member.education3 }} </li>
  {% endif %}

  {% if member.number_educ == 4 %}
  <li> {{ member.education1 }} </li>
  <li> {{ member.education2 }} </li>
  <li> {{ member.education3 }} </li>
  <li> {{ member.education4 }} </li>
  {% endif %}

  {% if member.number_educ == 5 %}
  <li> {{ member.education1 }} </li>
  <li> {{ member.education2 }} </li>
  <li> {{ member.education3 }} </li>
  <li> {{ member.education4 }} </li>
  <li> {{ member.education5 }} </li>
  {% endif %}


 {% if member.external_sites > 0  %}
  <div class="row">
	  {% if member.orcid  %}
	  <div class="col-sm">
	  	  <a href= "{{ member.orcid }}" target="_blank">
		  <img src="{{ site.url }}{{ site.baseurl }}/images/Orcid_icon.jpg" style="float: left; width:5%; margin-right:5%"></a>
		</div>
	  {% endif %}
	  {% if member.google_scholar  %}
  	  <div class="col-sm">
	  <a href= "{{ member.google_scholar }}" target="_blank">
		<img src="{{ site.url }}{{ site.baseurl }}/images/Google_icon.jpg" style="float: left; width:5%; margin-right:5%"></a>
		</div>
	  {% endif %}
	  {% if member.scopus  %}
	  <div class="col-sm">
	  	   <a href= "{{ member.scopus }}" target="_blank">
	       <img src="{{ site.url }}{{ site.baseurl }}/images/scopus_icon.jpg" style="float: left; width:5%; margin-right:5%"></a>
		  </div>
	  {% endif %}
	  {% if member.publons  %}
		  <div class="col-sm">
		  <a href= "{{ member.publons }}" target="_blank">
		  <img src="{{ site.url }}{{ site.baseurl }}/images/publons_icon.jpg" style="float: left; width:5%; margin-right:5%"></a>
		</div>
	  {% endif %}
	  {% if member.researchgate  %}
	  <div class="col-sm">
	  	   <a href= "{{ member.researchgate }}" target="_blank">
	       <img src="{{ site.url }}{{ site.baseurl }}/images/researchgate_icon.jpg" style="float: left; width:5%; margin-right:5%"></a>
		  </div>
	  {% endif %}
  </div>
  {% endif %}
  

  </ul>
</div>

{% assign number_printed = number_printed | plus: 1 %}

{% if even_odd == 1 %}
</div>
{% endif %}

{% endfor %}

{% assign even_odd = number_printed | modulo: 2 %}
{% if even_odd == 1 %}
</div>
{% endif %}



## Alumni

{% assign number_printed = 0 %}
{% for member in site.data.alumni_members %}

{% assign even_odd = number_printed | modulo: 2 %}

{% if even_odd == 0 %}
<div class="row">
{% endif %}

<div class="col-sm-6 clearfix">
  <img src="{{ site.url }}{{ site.baseurl }}/images/teampic/{{ member.photo }}" class="img-responsive" width="25%" style="float: left" />
  <h4>{{ member.name }}</h4>
  <i>Role: {{ member.info }}<br>
  Now {{ member.now }}
  <ul style="overflow: hidden">
  
   </ul>
</div>

{% assign number_printed = number_printed | plus: 1 %}

{% if even_odd == 1 %}
</div>
{% endif %}

{% endfor %}

{% assign even_odd = number_printed | modulo: 2 %}
{% if even_odd == 1 %}
</div>
{% endif %}

<p> &nbsp; </p>


## Lab Affiliates
{% assign number_printed = 0 %}
{% for member in site.data.associate_members %}

{% assign even_odd = number_printed | modulo: 2 %}

{% if even_odd == 0 %}
<div class="row">
{% endif %}

<div class="col-sm-6 clearfix">
  <img src="{{ site.url }}{{ site.baseurl }}/images/teampic/{{ member.photo }}" class="img-responsive" width="25%" style="float: left" />
  <h4>{{ member.name }}</h4>
  <i>Role: {{ member.info }}<br> email: <{{ member.email }}></i>
  <ul style="overflow: hidden">

  </ul>
</div>

{% assign number_printed = number_printed | plus: 1 %}

{% if even_odd == 1 %}
</div>
{% endif %}

{% endfor %}

{% assign even_odd = number_printed | modulo: 2 %}
{% if even_odd == 1 %}
</div>
{% endif %}

<p> &nbsp; </p>

## Collaborators
* [Saad Jbabdi](https://www.win.ox.ac.uk/people/saad-jbabdi){:target="_blank"}, University of Oxford, UK <br>
* [Alan Anticevic](https://medicine.yale.edu/lab/anticevic){:target="_blank"}, Yale University, USA <br>
* [Matthew Glasser](https://scholar.google.com/citations?user=hqA9AugAAAAJ&hl=en){:target="_blank"}, Washington University - St Louis, USA <br>
* [Stephen Smith](https://www.win.ox.ac.uk/people/stephen-smith){:target="_blank"}, University of Oxford, UK <br>
* [Stephen Coombes](https://www.maths.nottingham.ac.uk/plp/pmzsc){:target="_blank"}, University of Nottingham, UK <br>
* [Rogier Mars](https://www.win.ox.ac.uk/people/rogier-mars){:target="_blank"}, University of Oxford, UK <br>
* [Essa Yacoub](https://www.cmrr.umn.edu/facultystaff/yacoub){:target="_blank"},
University of Minnesota, USA <br>
* [Paul Morgan](https://orcid.org/0000-0002-5870-1446l){:target="_blank"}, Nottingham University Hospitals NHS Trust, UK <br>
* [Daniel Alexander](http://www0.cs.ucl.ac.uk/staff/D.Alexander){:target="_blank"}, University College London, UK <br>
* [Takuya Hayashi](https://www.bdr.riken.jp/en/research/labs/hayashi-t/index.html){:target="_blank"}, RIKEN, Japan <br>
* [Mark Jenkinson](https://researchers.adelaide.edu.au/profile/mark.jenkinson#my-research){:target="_blank"}, University of Oxford & University of Adelaide, Australia <br>
* [John Murray](https://medicine.yale.edu/lab/murray){:target="_blank"}, Yale University, USA <br>
* [Dorothee Auer](https://www.nottingham.ac.uk/medicine/people/dorothee.auer){:target="_blank"}, University of Nottingham, UK <br>

<p> &nbsp; </p>
