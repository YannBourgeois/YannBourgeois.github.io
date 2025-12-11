---
layout: page
title: Methods in population genomics
description: Ongoing project
img: assets/img/toolbox.jpg
importance: 3
pretty_table: true
category: resources
---

There are many methods in population genomics. To help newcomers, we published a review on the main methods in the field, available [here](https://doi.org/10.1111/mec.15989) 

This simple graph should explain it all...

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/mec15989-fig-0001-m.jpg" title="A summary of an ideal popgen analytical pipeline" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Methods are interconnected, and there are attempts to incorporate this connectivity in more recent works (e.g. machine learning). Aspects that require 'back-and-forth' are indicated by double arrows. Results obtained from methods listed in different sections can be used to inform the next steps of an analysis (single arrows). There is no one-size-fits-all pipeline, and elements of this general framework may be entirely omitted from an analysis depending on the research question.
</div>

## A few more resources.

I try to regularly update the tables so they reflect the most recent methods. You can also check the [blog posts](https://yannbourgeois.github.io/blog/), where I pin reviews or articles that summarize recent methods.

I also design lectures and workshops in population genomics. I recently contributed with [Thibault Leroy](https://thibaultleroyfr.github.io/) to an  <a href="https://github.com/PhysaliaIntroPopGen/November2024">online Physalia course</a>.

In collaboration with Julie Orjuela at IRD, we designed a three-days workshop on population genomics. It is inspired by the one designed for Physalia, but also includes new material, particularly for demographic inference.
Data for workshops #1 and #2 can be found <a href="https://forge.ird.fr/itrop/training/training_genomique_pops"> at this address </a>

Workshop #1: [Population structure]({{ site.url }}/assets/html/Workshop_Day_1.html)

Workshop #2: [Demographic inference, introduction to ABC and likelihood approaches]({{ site.url }}/assets/html/Workshop_Day_2.html)

Workshop #3: [Selection and association scans]({{ site.url }}/assets/html/Workshop_Day_3.html)

I am also planning another set of workshops on spatial genomics. I recently started developing pipelines using [slendr](https://bodkan.net/slendr/), which is a R package interacting with tskit and SLiM, and can be very useful if your research has a spatial component and you want to test the robustness of your analyses. I will post it here once done.

##  Table 1: Summary of methods dedicated to infer population structure.
<table
  data-click-to-select="true"
  data-height="460"
  data-pagination="true"
  data-search="true"
  data-toggle="table"
  data-url="{{ '/assets/json/Table_1.json' | relative_url }}"
>
  <thead>
    <tr>
      <th data-checkbox="true"></th>
      <th data-field="Software" data-halign="left" data-align="center" data-sortable="true">Software</th>
      <th data-field="Class of method" data-halign="center" data-align="right" data-sortable="true">Class of method</th>
      <th data-field="Purpose" data-halign="center" data-align="right" data-sortable="true">Purpose</th>
      <th data-field="Specifics" data-halign="center" data-align="right" data-sortable="true">Class of method</th>
      <th data-field="Issues and warnings" data-halign="center" data-align="right" data-sortable="true">Issues/Warnings</th>
      <th data-field="Reference" data-halign="center" data-align="right" data-sortable="true">Reference</th>
      <th data-field="Link" data-halign="right" data-align="left" data-sortable="true">Link</th>    </tr>
  </thead>
</table>



## Table 2: Summary of methods dedicated to detect selection
<table
  data-click-to-select="true"
  data-height="460"
  data-pagination="true"
  data-search="true"
  data-toggle="table"
  data-url="{{ '/assets/json/Table_2.json' | relative_url }}"
>
  <thead>
    <tr>
      <th data-checkbox="true"></th>
      <th data-field="Software" data-halign="left" data-align="center" data-sortable="true">Software</th>
      <th data-field="Class of method" data-halign="center" data-align="right" data-sortable="true">Class of method</th>
      <th data-field="Purpose" data-halign="center" data-align="right" data-sortable="true">Purpose</th>
      <th data-field="Specifics" data-halign="center" data-align="right" data-sortable="true">Class of method</th>
      <th data-field="Issues and warnings" data-halign="center" data-align="right" data-sortable="true">Issues/Warnings</th>
      <th data-field="Reference" data-halign="center" data-align="right" data-sortable="true">Reference</th>
      <th data-field="Link" data-halign="right" data-align="left" data-sortable="true">Link</th>    </tr>
  </thead>
</table>



## Table 3: Summary of methods dedicated to reconstruct demographic history
<table
  data-click-to-select="true"
  data-height="460"
  data-pagination="true"
  data-search="true"
  data-toggle="table"
  data-url="{{ '/assets/json/Table_3.json' | relative_url }}"
>
  <thead>
    <tr>
      <th data-checkbox="true"></th>
      <th data-field="Software" data-halign="left" data-align="center" data-sortable="true">Software</th>
      <th data-field="Class of method" data-halign="center" data-align="right" data-sortable="true">Class of method</th>
      <th data-field="Purpose" data-halign="center" data-align="right" data-sortable="true">Purpose</th>
      <th data-field="Specifics" data-halign="center" data-align="right" data-sortable="true">Class of method</th>
      <th data-field="Issues and warnings" data-halign="center" data-align="right" data-sortable="true">Issues/Warnings</th>
      <th data-field="Reference" data-halign="center" data-align="right" data-sortable="true">Reference</th>
      <th data-field="Link" data-halign="right" data-align="left" data-sortable="true">Link</th>    </tr>
  </thead>
</table>



## Table 4: Summary of simulators and simulation-based methods for selection and demographic inference.
<table
  data-click-to-select="true"
  data-height="460"
  data-pagination="true"
  data-search="true"
  data-toggle="table"
  data-url="{{ '/assets/json/Table_4.json' | relative_url }}"
>
  <thead>
    <tr>
      <th data-checkbox="true"></th>
      <th data-field="Software" data-halign="left" data-align="center" data-sortable="true">Software</th>
      <th data-field="Class of method" data-halign="center" data-align="right" data-sortable="true">Class of method</th>
      <th data-field="Purpose" data-halign="center" data-align="right" data-sortable="true">Purpose</th>
      <th data-field="Specifics" data-halign="center" data-align="right" data-sortable="true">Class of method</th>
      <th data-field="Issues and warnings" data-halign="center" data-align="right" data-sortable="true">Issues/Warnings</th>
      <th data-field="Reference" data-halign="center" data-align="right" data-sortable="true">Reference</th>
      <th data-field="Link" data-halign="right" data-align="left" data-sortable="true">Link</th>
    </tr>
  </thead>
</table>
