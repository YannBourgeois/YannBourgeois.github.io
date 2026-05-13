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

I am also working on developing pipelines using machine/deep learning. You can check these two resources, which aim at helping researchers build their own pipelines.

##  Table 1: Summary of methods dedicated to infer population structure.

Below you can find a table listing several methods that aim at inferring both discrete and continuous patterns in genetic data. One of the main issues that one can encounter is overinterpreting patterns of structure as reflecting isolation. Methods that incorporate the landscape (landscape genomics) may be better suited to get a sense of whether there is a barrier to gene flow or not. Some methods can also incorporate time if samples have been obtained from different generations (like tfa).


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

Detecting candidate genes for selection can be more complex than it seems, not because the methods are difficult to implement, but because of the temptation of storytelling. I can only invite the reader to read (again) the famous article about the spandrels of San Marco. It is good practice to use simulations to get a sense of what can be detected or not (see also table 4). You can find a few basic examples of what can be done [here]({{ site.url }}/assets/html/Workshop_Day_3.html).

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

Demographic inference can be roughly divided between methods that require extensive supervision by the user (e.g. fastsimcoal2), and those that come with an already shipped model (e.g. MSMC2). The latter are useful to get a sense of what signal lies in the data, but the user should not exclusively rely on them. Methods that require the user to define a model are better from that perspective, as they force them to think of possible alternative ways of generating similar data. Again, it is a good idea to keep in mind that several demographic histories may produce very similar signatures in the genetic data. Whenever possible, for any given method, check whether simulations under the best-fitting model can recover observations for statistics that were not used for inference. For example, when using a method based on the SFS, you might want to check whether LD-based statistics are well recovered.

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

The field is now moving towards a better integration of demography and selection, although this remains computationnally challenging. The complex interaction between selection and demography shapes patterns of genomic diversity, and it is not necessarily clear to what extent these parameters are identifiable. Below are some methods that provide ways to simulate datasets, train algorithms, and obtain a fuller picture of possible ways a gene or a genome evolves.

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

## Table 5: A possible list of methods to begin with

There are a lot of methods, each of them built with a particular need in mind. For most analyses however, there are a few unavoidable pieces of software that can be used. You will find an attempt at listing them below. 

<table
  data-click-to-select="true"
  data-height="460"
  data-pagination="true"
  data-search="true"
  data-toggle="table"
  data-url="{{ '/assets/json/Table_5.json' | relative_url }}"
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

## Table 6: A primer to museomics/ancient DNA

Disclaimer: I am not a specialist of these methods, although I am starting to use them in my own research. However, museum and herbarium samples have proven invaluable to reconstruct the past history of species, and are sometimes extremely abundant. However, they may require using dedicated pipeline that handle the uncertainty due to low depth and post-mortem damage. The table below may help users who want to know a bit more about the requirements of such analyses.


<table
  data-click-to-select="true"
  data-height="460"
  data-pagination="true"
  data-search="true"
  data-toggle="table"
  data-url="{{ '/assets/json/Table_6.json' | relative_url }}"
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



