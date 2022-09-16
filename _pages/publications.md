---
title: "CoNI Lab - Publications"
layout: gridlay
excerpt: "CoNI Lab -- Publications."
sitemap: false
permalink: /publications/
---


# Publications

## Highlights

See full list of [journal papers](#journal-papers-full-list) and
[book chapters](#book-chapters) or go to
[Pubmed Search](https://www.ncbi.nlm.nih.gov/pubmed/?term=(Sotiropoulos+SN+[au]+)+|+(Sotiropoulos+Stamatios+[au])){:target="_blank"}.

{% assign number_printed = 0 %}
{% for publi in site.data.publist %}

{% assign even_odd = number_printed | modulo: 2 %}
{% if publi.highlight == 1 %}

{% if even_odd == 0 %}
<div class="row">
{% endif %}

<div class="col-sm-6 clearfix">
 <div class="well">
  <pubtit>{{ publi.title }}</pubtit>
  <img src="{{ site.url }}{{ site.baseurl }}/images/pubpic/{{ publi.image }}" class="img-responsive" width="45%" style="float: left" />
  <p>{{ publi.description }}</p>
  <p><em>{{ publi.authors }}</em></p>
  {% if publi.news1 == 1 %}
  <br>
  {% endif %}
  <p><strong><a href="{{ publi.link.url }}" target="_blank">{{ publi.link.display }}</a></strong></p>
  <p class="text-danger"><strong> {{ publi.news1 }}</strong></p>
 </div>
</div>

{% assign number_printed = number_printed | plus: 1 %}

{% if even_odd == 1 %}
</div>
{% endif %}

{% endif %}
{% endfor %}

{% assign even_odd = number_printed | modulo: 2 %}
{% if even_odd == 1 %}
</div>
{% endif %}

<p> &nbsp; </p>


## Journal Papers Full list

{% for publi in site.data.publist %}

  {{ publi.title }} <br />
  <em>{{ publi.authors }} </em><br /><a href="{{ publi.link.url }}" target="_blank">{{ publi.link.display }}</a>

{% endfor %}

<p> &nbsp; </p>


## Book Chapters

MR diffusion tractography.  <br />
<em> TEJ Behrens, SN Sotiropoulos, S Jbabdi</em><br />
<a href="https://www.elsevier.com/books/diffusion-mri/johansen-berg/978-0-12-396460-1"
target="_blank">In Diffusion MRI, 2nd Edition:From quantitative measurement to in-vivo neuroanatomy, Academic Press, 2013</a>


Mapping connections in humans and non-human primates: aspirations and challenges for diffusion imaging. <br />
<em>Van Essen DC, Jbabdi S, Sotiropoulos SN, Chen C, Dikranian K,
Coalson T, Harwell H, Behrens TE, Glasser MF</em><br />
<a href="https://www.elsevier.com/books/diffusion-mri/johansen-berg/978-0-12-396460-1"
target="_blank">In Diffusion MRI, 2nd Edition:From quantitative measurement to in-vivo neuroanatomy, Academic Press, 2013</a>


<p> &nbsp; </p>
