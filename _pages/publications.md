---
title: "CoNI Lab - Publications"
layout: gridlay
excerpt: "CoNI Lab -- Publications"
sitemap: false
permalink: /publications/
---

# Publications

## Highlights

See full list of [journal papers](#journal-papers-full-list), [book chapters](#book-chapters) and [PhD theses](#phd-theses) or go to
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
  {% if publi.extra_br == 1 %}
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

<style> li { padding: 10px 0px 0px; } </style>
## Journal Papers Full list
<ol>
{% for publi in site.data.publist %}
<li>
  {{ publi.title }} <br />
  <em>{{ publi.authors }} </em><br /><a href="{{ publi.link.url }}" target="_blank">{{ publi.link.display }}</a>
</li>
{% endfor %}
</ol>
<p> &nbsp; </p>


## Book Chapters
<ol>
<li>Probabilistic Tractography  <br />
<em>Girard G, Aydogan DB, Dell'Acqua F, Leemans A, Descoteaux M, Sotiropoulos SN</em><br />
<a href="https://shop.elsevier.com/books/handbook-of-diffusion-mr-tractography/dellacqua/978-0-12-818894-1"
target="_blank">In Handbook of Diffusion MR Tractography, Academic Press, 2024</a></li>

<li>Connectivity and Connectomics <br />
<em>Zalesky A, Sotiropoulos SN, Jbabdi S, Fornito A</em><br />
<a href="https://shop.elsevier.com/books/handbook-of-diffusion-mr-tractography/dellacqua/978-0-12-818894-1"
target="_blank">In Handbook of Diffusion MR Tractography, Academic Press, 2024</a></li>

<li>MR diffusion tractography  <br />
<em> Behrens TEJ, Sotiropoulos SN, Jbabdi S</em><br />
<a href="https://www.elsevier.com/books/diffusion-mri/johansen-berg/978-0-12-396460-1"
target="_blank">In Diffusion MRI, 2nd Edition:From quantitative measurement to in-vivo neuroanatomy, Academic Press, 2013</a></li>

<li>Mapping connections in humans and non-human primates: aspirations and challenges for diffusion imaging <br />
<em>Van Essen DC, Jbabdi S, Sotiropoulos SN, Chen C, Dikranian K,
Coalson T, Harwell H, Behrens TE, Glasser MF</em><br />
<a href="https://www.elsevier.com/books/diffusion-mri/johansen-berg/978-0-12-396460-1"
target="_blank">In Diffusion MRI, 2nd Edition:From quantitative measurement to in-vivo neuroanatomy, Academic Press, 2013</a></li>
</ol>

<p> &nbsp; </p>


## PhD Theses
<ol>
<li>Whole-brain imaging in rodents using MRI and 3D microscopy: A cross-scale, multi-modal approach<br/>
<em> Jenna Hanmer (supervised by: S. N. Sotiropoulos, T. Farr, P. S. Morgan) </em> <br/>
<a href="https://eprints.nottingham.ac.uk/" target="_blank">PhD
University of Nottingham</a>, 2025</li>

<li>Interpretability and annotation scarcity in deep medical image segmentation <br/>
<em> Golnar Khalili Zadeh Mahani  (supervised by: A. French, X. Chen,
S. N. Sotiropoulos) </em> <br/>
<a href="https://eprints.nottingham.ac.uk/78836" target="_blank">PhD University of Nottingham</a>, 2024</li>

<li>On noise, uncertainty and inference for computational diffusion MRI <br/>
<em> Jose Pedro Manzano-Patron (supervised by: S. N. Sotiropoulos, T. Kypraios) </em> <br/>
<a href="https://eprints.nottingham.ac.uk/74189" target="_blank">PhD University of Nottingham</a>, 2023</li>


<li>The numerical solution of neural field models posed on realistic cortical domains <br/>
<em> Sammy Petros (supervised by: S. Coombes, S. N. Sotiropoulos, P. Houston) </em> <br/>
<a href="https://eprints.nottingham.ac.uk/72417" target="_blank">PhD University of Nottingham</a>, 2023</li>


<li>On harmonisation of brain MRI data across scanners and sites <br/>
<em> Asante Ntata (supervised by: S. N. Sotiropoulos, O. Mougin) </em> <br/>
<a href="https://eprints.nottingham.ac.uk/74417/" target="_blank">PhD University of Nottingham</a>, 2023</li>


<li>Brain connectivity mapping with diffusion MRI across individuals and species <br/>
<em> Shaun Warrington (supervised by: S. N. Sotiropoulos) </em> <br/>
<a href="https://eprints.nottingham.ac.uk/65487" target="_blank">PhD University of Nottingham </a>, 2021</li>


<li>Examining structural and functional connectivity change in animal models of cerebrovascular disease <br/>
<em> Gerard Hall (supervised by T. Farr, S. N. Sotiropoulos) </em> <br/>
<a href="https://eprints.nottingham.ac.uk/65800" target="_blank">PhD
University of Nottingham</a>, 2021</li>


<li>Mapping connections in the neonatal brain with magnetic resonance imaging <br/>
<em> Elinor Thompson (supervised by: S. N. Sotiropoulos, M. Bastiani) </em> <br/>
<a href="https://eprints.nottingham.ac.uk/64848" target="_blank">PhD University of Nottingham</a>, 2021</li>


<li>Simulating Brain Resting-State Activity What Matters? <br/>
<em> Jonathan Hadida (supervised by: M. Woolrich, S. N. Sotiropoulos, S. Jbabdi) </em> <br/>
<a href="https://ora.ox.ac.uk/objects/uuid:5abd962a-b798-4530-947a-24eeafd568f3" target="_blank">DPhil University of Oxford</a>, 2018</li>


<li>Accelerating computational diffusion MRI using Graphics Processing Units  <br/>
<em> Moises Hernandez-Fernandez (supervised by: S. N. Sotiropoulos, M. Giles, S. Smith </em> <br/>
<a href="https://ora.ox.ac.uk/objects/uuid:a0ac63bc-bdd4-4d77-9344-d631e4d4297a" target="_blank">DPhil University of Oxford</a>, 2017</li>


<p> &nbsp; </p>
