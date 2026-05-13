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

I am also working on developing pipelines using **machine/deep learning** (see also Table 4). You can check these two resources, which aim at helping researchers build their own pipelines:

[dnadna](https://mlgenetics.gitlab.io/dnadna/)
[popgen-npe](https://popgen-npe.readthedocs.io/en/latest/)

Note that the latter has been designed with the ability to produce posterior distributions and confidence intervals.

##  Table 1: Summary of methods for population structure inference.

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



## Table 2: Summary of methods for genome scans of selection.

Detecting candidate genes for selection can be more complex than it seems, not because the methods are difficult to implement, but because of the temptation of storytelling. I can only invite the reader to read (again) the famous article about the spandrels of San Marco. It is good practice to use simulations to get a sense of what can be detected or not (see also table 4). You can find a few basic examples of what can be done [here]({{ site.url }}/assets/html/Workshop_Day_3.html).
You will also find in this table methods that estimate the recombination landscape, since it can be useful to quantify linked selection.

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



## Table 3: Summary of methods for demographic history reconstruction

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

## References


Adrion, J., Cole, C., Dukler, N., Galloway, J., Gladstein, A., Gower, G., Kyriazis, C., Ragsdale, A., Tsambos, G., Baumdicker, F., & others (2020). A community-maintained standard library of population genetic models. eLife, 9, e54967.

Adrion, J., Galloway, J., & Kern, A. (2020). Predicting the landscape of recombination using deep learning. Mol. Biol. Evol., 37(6), 1790–1808.

Akbari, A., Vitti, J., Iranmehr, A., Bakhtiari, M., Sabeti, P., Mirarab, S., & Bafna, V. (2018). Identifying the favored mutation in a positive selective sweep. Nat. Methods, 15, 279–282.

Alaçaml\i, E., Naidoo, T., Yaka, R., Coskun, S., Sağlican, E., & others (2024). READv2: Advanced and user-friendly detection of biological relatedness in archaeogenomics. bioRxiv.

Al-Asadi, H., Petkova, D., Stephens, M., & Novembre, J. (2019). Estimating recent migration and population-size surfaces. PLoS Genet., 15(1), e1007908.

Alachiotis, N., Stamatakis, A., & Pavlidis, P. (2012). OmegaPlus: a scalable tool for rapid detection of selective sweeps in whole-genome datasets. Bioinformatics, 28(17), 2274–2275.

Alachiotis, N., & Pavlidis, P. (2018). RAiSD detects positive selection based on multiple signatures of a selective sweep and SNP vectors. Commun. Biol., 1, 79.

Alachiotis, N., & others (2024). RAiSD-AI: a deep-learning extension of RAiSD for sweep detection. Bioinformatics.

Alexander, D., Novembre, J., & Lange, K. (2009). Fast model-based estimation of ancestry in unrelated individuals. Genome Res., 19, 1655–1664.

Atkinson, E., Maihofer, A., Kanai, M., Martin, A., Karczewski, K., Santoro, M., Ulirsch, J., Kamatani, Y., Okada, Y., Finucane, H., & others (2021). Tractor uses local ancestry to enable the inclusion of admixed individuals in GWAS and to boost power. Nat. Genet., 53, 195–204.

Aulchenko, Y., Ripke, S., Isaacs, A., & Duĳn, C. (2007). GenABEL: an R library for genome-wide association analysis. Bioinformatics, 23, 1294–1296.

Baran, Y., Pasaniuc, B., Sankararaman, S., Torgerson, D., Gignoux, C., Eng, C., Rodriguez-Cintron, W., Chapela, R., Ford, J., Avila, P., & others (2012). Fast and accurate inference of local ancestry in Latino populations. Bioinformatics, 28(10), 1359–1367.

Barroso, G., Puzovic, N., & Dutheil, J. (2019). Inference of recombination maps from a single pair of genomes and its application to ancient samples. PLoS Genet., 15(11), e1008449.

Baumdicker, F., Bisschop, G., Goldstein, D., Gower, G., Ragsdale, A., Tsambos, G., Zhu, S., Eldon, B., Ellerman, E., Galloway, J., & others (2022). Efficient ancestry and mutation simulation with msprime 1.0. Genetics, 220(3), iyab229.

Beaumont, M., & Balding, D. (2004). Identifying adaptive genetic divergence among populations from genome scans. Mol. Ecol., 13, 969–980.

Beeravolu, C., Hickerson, M., Frantz, L., & Lohse, K. (2018). ABLE: blockwise site frequency spectra for inferring complex population histories and recombination. Genome Biol., 19, 145.

Behr, A., Liu, K., Liu-Fang, G., Nakka, P., & Ramachandran, S. (2016). pong: fast analysis and visualization of latent clusters in population genetic data. Bioinformatics, 32(18), 2817–2823.

Bitarello, B., Filippo, C., Te\ixeira, J., Schmidt, J., Kleinert, P., Meyer, D., & Andrés, A. (2018). Signatures of long-term balancing selection in human genomes. Genome Biol. Evol., 10(3), 939–955.

Boitard, S., Rodr\'iguez, W., Jay, F., Mona, S., & Austerlitz, F. (2016). Inferring population size history from large samples of genome-wide molecular data –- an approximate Bayesian computation approach. PLoS Genet., 12(3), e1005877.

Bonhomme, M., Chevalet, C., Servin, B., Boitard, S., Abdallah, J., Blott, S., & SanCristobal, M. (2010). Detecting selection in population trees: the Lewontin and Krakauer test extended. Genetics, 186(1), 241–262.

Bouckaert, R., Heled, J., Kuhnert, D., Vaughan, T., Wu, C.H., Xie, D., Suchard, M., Rambaut, A., & Drummond, A. (2014). BEAST 2: a software platform for Bayesian evolutionary analysis. PLoS Comput. Biol., 10(4), e1003537.

Boyrie, Y., Hivert, V., & others (2020). Scanning for epistatic interactions based on linkage disequilibrium. Mol. Ecol. Resour..

Bradburd, G., Ralph, P., & Coop, G. (2013). Disentangling the effects of geographic and ecological isolation on genetic differentiation. Evolution, 67(11), 3258–3273.

Bradburd, G., Coop, G., & Ralph, P. (2018). Inferring continuous and discrete population genetic structure across space. Genetics, 210(1), 33–52.

Bradbury, P., Zhang, Z., Kroon, D., Casstevens, T., Ramdoss, Y., & Buckler, E. (2007). TASSEL: software for association mapping of complex traits in diverse samples. Bioinformatics, 23(19), 2633–2635.

Brisbin, A., Bryc, K., Byrnes, J., Zakharia, F., Omberg, L., Degenhardt, J., Reynolds, A., Ostrer, H., Mezey, J., & Bustamante, C. (2012). PCAdmix: principal components-based assignment of ancestry along each chromosome in individuals with admixed ancestry from two or more populations. Hum. Biol., 84(4), 343–364.

Browning, B., & Browning, S. (2013). Detecting identity by descent and estimating genotype error rates in sequence data. Am. J. Hum. Genet., 93(5), 840–851.

Browning, S., & Browning, B. (2015). Accurate non-parametric estimation of recent effective population size from segments of identity by descent. Am. J. Hum. Genet., 97(3), 404–418.

Browning, S., Browning, B., Zhou, Y., Tucci, S., & Akey, J. (2018). Analysis of human sequence data reveals two pulses of archaic Denisovan admixture. Cell, 173(1), 53–61.

Browning, B., Tian, X., Zhou, Y., & Browning, S. (2021). Fast two-stage phasing of large-scale sequence data. Am. J. Hum. Genet., 108(10), 1880–1890.

Browning, S., Waples, R., & Browning, B. (2023). Fast, accurate local ancestry inference with FLARE. Am. J. Hum. Genet., 110(2), 326–335.

Bryant, D., Bouckaert, R., Felsenstein, J., Rosenberg, N., & RoyChoudhury, A. (2012). Inferring species trees directly from biallelic genetic markers: bypassing gene trees in a full coalescent analysis. Mol. Biol. Evol., 29(8), 1917–1932.

Burban, E., Tenaillon, M., & Glemin, S. (2024). RIDGE, a tool tailored to detect gene flow barriers across species pairs. Mol. Ecol. Resour..

Cadzow, M., Boocock, J., Nguyen, H., Wilcox, P., Merriman, T., & Black, M. (2014). A bioinformatics workflow for detecting signatures of selection in genomic data. Front. Genet., 5, 293.

Capblancq, T., & Forester, B. (2021). Redundancy analysis: a Swiss Army knife for landscape genomics. Methods Ecol. Evol., 12, 2298–2309.

Caye, K., Deist, T., Martins, H., Michel, O., & Fran\ccois, O. (2016). TESS3: fast inference of spatial population structure and genome scans for selection. Mol. Ecol. Resour., 16(2), 540–548.

Caye, K., Jumentier, B., Lepeule, J., & Fran\ccois, O. (2019). LFMM 2: fast and accurate inference of gene-environment associations in genome-wide studies. Mol. Biol. Evol., 36(4), 852–860.

Chan, A., Jenkins, P., & Song, Y. (2012). Genome-wide fine-scale recombination rate variation in Drosophila melanogaster. PLoS Genet., 8(12), e1003090.

Chang, C., Chow, C., Tellier, L., Vattikuti, S., Purcell, S., & Lee, J. (2015). Second-generation PLINK: rising to the challenge of larger and richer datasets. GigaScience, 4, 7.

Chembi, A., & others (2024). unPC: a tool for spatial visualization of population structure. TODO.

Chen, L., Wolf, A., Fu, W., Li, L., & Akey, J. (2020). Identifying and interpreting apparent Neanderthal ancestry in African individuals. Cell, 180(4), 677–687.

Cheng, X., & DeGiorgio, M. (2020). Flexible mixture model approaches that accommodate footprint size variability for robust detection of balancing selection. Mol. Biol. Evol., 37(11), 3267–3291.

Cheng, X., & DeGiorgio, M. (2024). BalLeRMix+: extensions of the BalLeRMix framework for balancing selection. Bioinformatics.

Cheng, J., Mailund, T., & Nielsen, R. (2017). Fast admixture analysis and population tree estimation for SNP and NGS data. Bioinformatics, 33, 2148–2155.

Chifman, J., & Kubatko, L. (2014). Quartet inference from SNP data under the coalescent model. Bioinformatics, 30(23), 3317–3324.

Chintalapati, M., Patterson, N., & Moorjani, P. (2022). The spatiotemporal patterns of major human admixture events during the European Holocene. eLife, 11, e77625.

Chu, L., & others (2021). Maximally correlated principal component analysis for population genetics. TODO.

Clemente, F., Cardona, A., Inchley, C., Peter, B., Jacobs, G., Pagani, L., Lawson, D., Antao, T., Vicente, M., Mitt, M., & others (2014). A selective sweep on a deleterious mutation in CPT1A in Arctic populations. Am. J. Hum. Genet., 95(5), 584–589.

Conomos, M., Reiner, A., Weir, B., & Thornton, T. (2016). Model-free estimation of recent genetic relatedness. Am. J. Hum. Genet., 98(1), 127–148.

Cornuet, J.M., Santos, F., Beaumont, M., Robert, C., Marin, J.M., Balding, D., Guillemaud, T., & Estoup, A. (2008). Inferring population history with DIY ABC: a user-friendly approach to approximate Bayesian computation. Bioinformatics, 24, 2713–2719.

Cousins, T., Scally, A., & Durbin, R. (2025). A structured coalescent model reveals deep ancestral structure shared by all modern humans. Nat. Genet..

Csilléry, K., Fran\ccois, O., & Blum, M. (2012). abc: an R package for approximate Bayesian computation (ABC). Methods Ecol. Evol., 3(3), 475–479.

Currat, M., Arenas, M., Quilodran, C., Excoffier, L., & Ray, N. (2019). SPLATCHE3: simulation of serial genetic data under spatially explicit evolutionary scenarios including long-distance dispersal. Bioinformatics, 35, 4480–4483.

Danecek, P., Auton, A., Abecasis, G., Albers, C., Banks, E., DePristo, M., Handsaker, R., Lunter, G., Marth, G., Sherry, S., & others (2011). The variant call format and VCFtools. Bioinformatics, 27(15), 2156–2158.

Danecek, P., Bonfield, J., Liddle, J., Marshall, J., Ohan, V., Pollard, M., Whitwham, A., Keane, T., McCarthy, S., Davies, R., & Li, H. (2021). Twelve years of SAMtools and BCFtools. GigaScience, 10, giab008.

Davies, R., Flint, J., Myers, S., & Mott, R. (2016). Rapid genotype imputation from sequence without reference panels. Nat. Genet., 48, 965–969.

Davies, R., Kucka, M., Su, D., Shi, S., Flanagan, M., Cunniff, C., Chan, Y., & Myers, S. (2024). Rapid genotype imputation from sequence with reference panels. Nat. Genet., 56, 1066–1074.

Davy, T., & others (2024). Leveraging ancient DNA to uncover signals of natural selection in Europe lost due to admixture or drift. Nat. Commun., 15, 10075.

DeGiorgio, M., Lohmueller, K., & Nielsen, R. (2014). A model-based approach for identifying signatures of ancient balancing selection in genetic data. PLoS Genet., 10(8), e1004561.

DeGiorgio, M., Huber, C., Hubisz, M., Hellmann, I., & Nielsen, R. (2016). SweepFinder2: increased sensitivity, robustness and flexibility. Bioinformatics, 32, 1895–1897.

Deng, Y., Nielsen, R., & Song, Y. (2025). Robust and accurate Bayesian inference of genome-wide genealogies for large samples. Nat. Genet..

Dias-Alves, T., Mairal, J., & Blum, M. (2018). Loter: a software package to infer local ancestry for a wide range of species. Mol. Biol. Evol., 35, 2318–2326.

Do, C., Waples, R., Peel, D., Macbeth, G., Tillett, B., & Ovenden, J. (2014). NeEstimator v2: re-implementation of software for the estimation of contemporary effective population size (Ne) from genetic data. Mol. Ecol. Resour., 14(1), 209–214.

Drummond, A., & Rambaut, A. (2007). BEAST: Bayesian evolutionary analysis by sampling trees. BMC Evol. Biol., 7, 214.

Duforet-Frebourg, N., Luu, K., Laval, G., Bazin, E., & Blum, M. (2016). Detecting genomic signatures of natural selection with principal component analysis: application to the 1000 Genomes data. Mol. Biol. Evol., 33(4), 1082–1093.

Durvasula, A., & Sankararaman, S. (2019). A statistical model for reference-free inference of archaic local ancestry. PLoS Genet., 15(5), e1008175.

Edelman, N., Frandsen, P., Miyagi, M., Clavijo, B., Davey, J., Dikow, R., Garc\'ia-Accinelli, G., Van Belleghem, S., Patterson, N., Neafsey, D., & others (2019). Genomic architecture and introgression shape a butterfly radiation. Science, 366(6465), 594–599.

Ewing, G., & Hermisson, J. (2010). MSMS: a coalescent simulation program including recombination, demographic structure and selection at a single locus. Bioinformatics, 26(16), 2064–2065.

Excoffier, L., & Lischer, H. (2010). Arlequin suite ver 3.5: a new series of programs to perform population genetics analyses under Linux and Windows. Mol. Ecol. Resour., 10(3), 564–567.

Excoffier, L., Dupanloup, I., Huerta-Sánchez, E., Sousa, V., & Foll, M. (2013). Robust demographic inference from genomic and SNP data. PLoS Genet., 9(10), e1003905.

Eyre-Walker, A., & Keightley, P. (2009). Estimating the rate of adaptive molecular evolution in the presence of slightly deleterious mutations and population size change. Mol. Biol. Evol., 26(9), 2097–2108.

Fan, C., Cahoon, J., Dinh, B., Ortega-Del Vecchyo, D., Huber, C., Edge, M., Mancuso, N., & Chiang, C. (2023). A likelihood-based framework for demographic inference from genealogical trees. bioRxiv.

Fellows Yates, J., Lamnidis, T., Borry, M., Andrades Valtueña, A., Fagernäs, Z., Clayton, S., Garcia, M., Neukamm, J., & Peltzer, A. (2021). Reproducible, portable, and efficient ancient genome reconstruction with nf-core/eager. PeerJ, 9, e10947.

Fernandes, D., Cheronet, O., Gelabert, P., & Pinhasi, R. (2021). TKGWV2: an ancient DNA relatedness pipeline for ultra-low coverage whole genome shotgun data. Sci. Rep., 11, 21262.

Ferretti, L., Ramos-Onsins, S., & Peréz-Enciso, M. (2013). Population genomics from pool sequencing. Mol. Ecol., 22(22), 5561–5576.

Flouri, T., Jiao, X., Rannala, B., & Yang, Z. (2018). Species tree inference with BPP using genomic sequences and the multispecies coalescent. Mol. Biol. Evol., 35(10), 2585–2593.

Foll, M., & Gaggiotti, O. (2008). A genome-scan method to identify selected loci appropriate for both dominant and codominant markers: a Bayesian perspective. Genetics, 180(2), 977–993.

Forester, B., Lasky, J., Wagner, H., & Urban, D. (2018). Comparing methods for detecting multilocus adaptation with multivariate genotype-environment associations. Mol. Ecol., 27(9), 2215–2233.

Fournier, R., Tsangalidou, Z., Reich, D., & Palamara, P. (2023). Haplotype-based inference of recent effective population size in modern and ancient DNA samples. Nat. Commun., 14, 7945.

Francioli, Y., & others (2025). Genome-wide coupling coefficient analysis in a rattlesnake hybrid zone. Nat. Commun..

Fran\ccois, O., & Jay, F. (2020). Factor analysis of ancient population genomic samples. Nat. Commun., 11, 4661.

Fra\"isse, C., Popovic, I., Mazoyer, C., Cornet, B., Belkhir, K., Bierne, N., Vekemans, X., & Roux, C. (2021). DILS: demographic inferences with linked selection by using ABC. Mol. Ecol. Resour., 21(8), 2629–2644.

Frichot, E., Schoville, S., Bouchard, G., & Fran\ccois, O. (2013). Testing for associations between loci and environmental gradients using latent factor mixed models. Mol. Biol. Evol., 30(7), 1687–1699.

Frichot, E., Mathieu, F., Trouillon, T., Bouchard, G., & Fran\ccois, O. (2014). Fast and efficient estimation of individual ancestry coefficients. Genetics, 196, 973–983.

Frichot, E., & Fran\ccois, O. (2015). LEA: an R package for landscape and ecological association studies. Methods Ecol. Evol., 6(8), 925–929.

Galtier, N. (2016). Adaptive protein evolution in animals and the effective population size hypothesis. PLoS Genet., 12(1), e1005774.

Gao, F., Ming, C., Hu, W., & Li, H. (2016). New software for the fast estimation of population recombination rates (FastEPRR) in the genomic era. G3, 6, 1563–1571.

Garcia-Erill, G., & Albrechtsen, A. (2020). Evaluation of model fit of inferred admixture proportions. Mol. Ecol. Resour., 20(4), 936–949.

Garrigan, D. (2013). POPBAM: tools for evolutionary analysis of short read sequence alignments. Evol. Bioinformatics, 9, 343–353.

Garud, N., Messer, P., Buzbas, E., & Petrov, D. (2015). Recent selective sweeps in North American Drosophila melanogaster show signatures of soft sweeps. PLoS Genet., 11(2), e1005004.

Gautier, M., & Vitalis, R. (2012). rehh: an R package to detect footprints of selection in genome-wide SNP data from haplotype structure. Bioinformatics, 28(8), 1176–1177.

Gautier, M. (2015). Genome-wide scan for adaptive divergence and association with population-specific covariates. Genetics, 201(4), 1555–1579.

Gautier, M., Vitalis, R., Flori, L., & Estoup, A. (2022). f-Statistics estimation and admixture graph construction with Pool-Seq or allele count data using the R package poolfstat. Mol. Ecol. Resour., 22(4), 1394–1416.

Gompert, Z., DeRaad, D., & Buerkle, C. (2024). A next-generation hierarchical Bayesian analysis of hybrid zones using bgchm. Ecol. Evol..

Goudet, J. (2005). hierfstat, a package for R to compute and test hierarchical F-statistics. Mol. Ecol. Notes, 5(1), 184–186.

Gower, G., Picazo, P., Fumagalli, M., & Racimo, F. (2021). Detecting adaptive introgression in human evolution using convolutional neural networks. eLife, 10, e64669.

Gower, G., Ragsdale, A., Bisschop, G., Gutenkunst, R., Hartfield, M., Noskova, E., Schiffels, S., Struck, T., Kelleher, J., & Thornton, K. (2022). Demes: a standard format for demographic models. Genetics, 222(3), iyac131.

Gronau, I., Hubisz, M., Gulko, B., Danko, C., & Siepel, A. (2011). Bayesian inference of ancient human demography from individual genome sequences. Nat. Genet., 43, 1031–1034.

Guan, Y. (2014). Detecting structure of haplotypes and local ancestry. Genetics, 196(3), 625–642.

Guillot, G., Renaud, S., Ledevin, R., Michaux, J., & Claude, J. (2012). A unifying model for the analysis of phenotypic, genetic, and geographic data. Syst. Biol., 61(6), 897–911.

Guindon, S., Dufayard, J.F., Lefort, V., Anisimova, M., Hordijk, W., & Gascuel, O. (2010). New algorithms and methods to estimate maximum-likelihood phylogenies: assessing the performance of PhyML 3.0. Syst. Biol., 59(3), 307–321.

Gunnarsson, ., Zhu, J., Zhang, B., Tsangalidou, Z., Allmont, A., & Palamara, P. (2024). A scalable approach for genome-wide inference of ancestral recombination graphs. bioRxiv.

Günther, T., & Coop, G. (2013). Robust identification of local adaptation from allele frequencies. Genetics, 195(1), 205–220.

Gusev, A., Lowe, J., Stoffel, M., Daly, M., Altshuler, D., Breslow, J., Friedman, J., & Pe'er, I. (2009). Whole population, genome-wide mapping of hidden relatedness. Genome Res., 19, 318–326.

Gutenkunst, R., Hernandez, R., Williamson, S., & Bustamante, C. (2009). Inferring the joint demographic history of multiple populations from multidimensional SNP frequency data. PLoS Genet., 5(10), e1000695.

Haak, W., Lazaridis, I., Patterson, N., Rohland, N., Mallick, S., Llamas, B., Brandt, G., Nordenfelt, S., Harney, E., Stewardson, K., & others (2015). Massive migration from the steppe was a source for Indo-European languages in Europe. Nature, 522, 207–211.

Haller, B., Galloway, J., Kelleher, J., Messer, P., & Ralph, P. (2019). Tree-sequence recording in SLiM opens new horizons for forward-time simulation of whole genomes. Mol. Ecol. Resour., 19(2), 552–566.

Haller, B., & Messer, P. (2023). SLiM 4: multispecies eco-evolutionary modeling. Am. Nat., 201(5), E127–E139.

Han, D., & others (2025). mrpast: likelihood-based demographic inference from ancestral recombination graphs. bioRxiv.

Hanghoj, K., Moltke, I., Andersen, P., Manica, A., & Korneliussen, T. (2019). Fast and accurate relatedness estimation from high-throughput sequencing data in the presence of inbreeding. GigaScience, 8(5), giz034.

Harney, ., Patterson, N., Reich, D., & Wakeley, J. (2021). Assessing the performance of qpAdm: a statistical tool for studying population admixture. Genetics, 217(4), iyaa045.

Harris, K., & Nielsen, R. (2013). Inferring demographic history from a spectrum of shared haplotype lengths. PLoS Genet., 9(6), e1003521.

Hartfield, M., Wright, S., & Agrawal, A. (2016). Coalescent times and patterns of genetic diversity in species with facultative sex. Genetics, 202, 297–312.

Hejase, H., Mo, Z., Campagna, L., & Siepel, A. (2022). A deep-learning approach for inference of selective sweeps from the ancestral recombination graph. Mol. Biol. Evol., 39(1), msab332.

Heled, J., & Drummond, A. (2010). Bayesian inference of species trees from multilocus data. Mol. Biol. Evol., 27(3), 570–580.

Hellenthal, G., Busby, G., Band, G., Wilson, J., Capelli, C., Falush, D., & Myers, S. (2014). A genetic atlas of human admixture history. Science, 343(6172), 747–751.

Henderson, D., Zhu, S., Cole, C., & Lunter, G. (2021). Demographic inference from multiple whole genomes using a particle filter for continuous Markov jump processes. PLoS ONE, 16(3), e0247647.

Hey, J., & Nielsen, R. (2007). Integration within the Felsenstein equation for improved Markov chain Monte Carlo methods in population genetics. Proc. Natl. Acad. Sci. U.S.A., 104(8), 2785–2790.

Hibbins, M., & others (2025). Detecting introgression from ghost lineages with the four-taxon test. bioRxiv.

Hilmarsson, H., Kumar, A., Rastogi, R., Bustamante, C., Mas Montserrat, D., & Ioannidis, A. (2021). High resolution ancestry deconvolution for next generation genomic data. bioRxiv.

Hivert, V., Leblois, R., Petit, E., Gautier, M., & Vitalis, R. (2018). Measuring genetic differentiation from Pool-seq data. Genetics, 210(1), 315–330.

Hofmeister, R., Ribeiro, D., Rubinacci, S., & Delaneau, O. (2023). Accurate rare variant phasing of whole-genome and whole-exome sequencing data in the UK Biobank. Nat. Genet., 55, 1243–1249.

Hu, Y., & others (2023). ERICA: deep-learning detection of introgression for arbitrary species. TODO.

Huang, Y., & Ringbauer, H. (2022). hapCon: estimating contamination of ancient genomes by copying from reference haplotypes. Bioinformatics, 38(15), 3768–3777.

Huang, X., Ortega-Del Vecchyo, D., Lopez-Valenzuela, M., Mas-Sandoval, A., Hsi-Yang Fritz, M., Pool, J., & Gutenkunst, R. (2023). dadi-cli: automated and distributed population genetic model inference from allele frequency spectra. bioRxiv.

Huang, X., Hackl, T., & Kuhlwilm, M. (2025). Decoding the genomic landscapes of introgression. Trends Genet..

Hubisz, M., Williams, A., & Siepel, A. (2020). Mapping gene flow between ancient hominins through demography-aware inference of the ancestral recombination graph. PLoS Genet., 16(8), e1008895.

Hudson, R. (2002). Generating samples under a Wright-Fisher neutral model of genetic variation. Bioinformatics, 18(2), 337–338.

Huisman, J. (2017). Pedigree reconstruction from SNP data: parentage assignment, sibship clustering and beyond. Mol. Ecol. Resour., 17(5), 1009–1024.

Huson, D., & Bryant, D. (2006). Application of phylogenetic networks in evolutionary studies. Mol. Biol. Evol., 23(2), 254–267.

Isildak, U., Stella, A., & Fumagalli, M. (2021). Distinguishing between recent balancing selection and incomplete sweep using deep neural networks. Mol. Ecol. Resour., 21(8), 2706–2718.

Jackson, N., Morales, A., Carstens, B., & O'Meara, B. (2017). PHRAPL: phylogeographic inference using approximate likelihoods. Syst. Biol., 66, 1045–1053.

Jombart, T., Devillard, S., Dufour, A.B., & Pontier, D. (2008). Revealing cryptic spatial patterns in genetic variability by a new multivariate method. Heredity, 101, 92–103.

Jombart, T., Devillard, S., & Balloux, F. (2010). Discriminant analysis of principal components: a new method for the analysis of genetically structured populations. BMC Genet., 11, 94.

J\'onsson, H., Ginolhac, A., Schubert, M., Johnson, P., & Orlando, L. (2013). mapDamage2.0: fast approximate Bayesian estimates of ancient DNA damage parameters. Bioinformatics, 29(13), 1682–1684.

Jouganous, J., Long, W., Ragsdale, A., & Gravel, S. (2017). Inferring the joint demographic history of multiple populations: beyond the diffusion approximation. Genetics, 206(3), 1549–1567.

Kamm, J., Terhorst, J., Durbin, R., & Song, Y. (2020). Efficiently inferring the demographic history of many populations with allele count data. J. Am. Stat. Assoc., 115, 1472–1487.

Keightley, P., & Eyre-Walker, A. (2007). Joint inference of the distribution of fitness effects of deleterious mutations and population demography based on nucleotide polymorphism frequencies. Genetics, 177(4), 2251–2261.

Kelleher, J., Etheridge, A., & McVean, G. (2016). Efficient coalescent simulation and genealogical analysis for large sample sizes. PLoS Comput. Biol., 12(5), e1004842.

Kelleher, J., Wong, Y., Wohns, A., Fadil, C., Albers, P., & McVean, G. (2019). Inferring whole-genome histories in large population datasets. Nat. Genet., 51, 1330–1338.

Kemppainen, P., Knight, C., Sarma, D., Hlaing, T., Prakash, A., Maung Maung, Y., Somboon, P., Mahanta, J., & Walton, C. (2015). Linkage disequilibrium network analysis (LDna) gives a global view of chromosomal inversions, local adaptation and geographic structure. Mol. Ecol. Resour., 15(5), 1031–1045.

Kern, A., & Schrider, D. (2016). discoal: flexible coalescent simulations with selection. Bioinformatics, 32(24), 3839–3841.

Kern, A., & Schrider, D. (2018). diploS/HIC: an updated approach to classifying selective sweeps. G3, 8, 1959–1970.

Kofler, R., Orozco-terWengel, P., De Maio, N., Pandey, R., Nolte, V., Futschik, A., Kosiol, C., & Schlötterer, C. (2011). PoPoolation: a toolbox for population genetic analysis of next generation sequencing data from pooled individuals. PLoS ONE, 6(1), e15925.

Korneliussen, T., Albrechtsen, A., & Nielsen, R. (2014). ANGSD: analysis of next generation sequencing data. BMC Bioinformatics, 15, 356.

Korneliussen, T., & Moltke, I. (2015). NgsRelate: a software tool for estimating pairwise relatedness from next-generation sequencing data. Bioinformatics, 31(24), 4009–4011.

Laetsch, D., Heger, A., & Lohse, K. (2023). gIMble: genome-wide IM blockwise likelihood estimation. TODO.

Lauterbur, M., Cavassim, M., Gladstein, A., Gower, G., Pope, N., Tsambos, G., Adrion, J., Belsare, S., Biddanda, A., Caudill, V., & others (2023). Expanding the stdpopsim species catalog, and lessons learned for realistic genome simulations. eLife, 12, RP84874.

Lee, T.H., Guo, H., Wang, X., Kim, C., & Paterson, A. (2014). SNPhylo: a pipeline to construct a phylogenetic tree from huge SNP data. BMC Genomics, 15, 162.

Li, H., & Durbin, R. (2011). Inference of human population history from individual whole-genome sequences. Nature, 475, 493–496.

Librado, P., & Orlando, L. (2018). Detecting signatures of positive selection along defined branches of a population tree using LSD. Mol. Biol. Evol., 35(6), 1520–1535.

Link, V., Kousathanas, A., Veeramah, K., Sell, C., Scheu, A., & Wegmann, D. (2017). ATLAS: analysis tools for low-depth and ancient samples. bioRxiv.

Lipatov, M., Sanjeev, K., Patro, R., & Veeramah, K. (2015). Maximum likelihood estimation of biological relatedness from low coverage sequencing data. bioRxiv.

Liu, X., & Fu, Y.X. (2020). Stairway Plot 2: demographic history inference with folded SNP frequency spectra. Genome Biol., 21, 280.

Liu, L., & Yu, L. (2011). Estimating species trees from unrooted gene trees. Syst. Biol., 60, 661–667.

Liu, Y., Mao, X., Krause, J., & Fu, Q. (2021). Insights into human history from the first decade of ancient human genomics. Science, 373, 1479–1484.

Liu, S., & others (2025). $Φ$SFS: a transposable-element age-aware site-frequency-spectrum statistic. bioRxiv.

Loh, P.R., Lipson, M., Patterson, N., Moorjani, P., Pickrell, J., Reich, D., & Berger, B. (2013). Inferring admixture histories of human populations using linkage disequilibrium. Genetics, 193, 1233–1254.

Mahmoudi, A., Koskela, J., Kelleher, J., Chan, Y.b., & Balding, D. (2022). Bayesian inference of ancestral recombination graphs. PLoS Comput. Biol., 18(3), e1009960.

Maier, R., Flegontov, P., Flegontova, O., Isildak, U., Changmai, P., & Reich, D. (2023). On the limits of fitting complex models of population history to f-statistics. eLife, 12, e85492.

Malinsky, M., Matschiner, M., & Svardal, H. (2021). Dsuite –- fast D-statistics and related admixture evidence from VCF files. Mol. Ecol. Resour., 21(2), 584–595.

Manichaikul, A., Mychaleckyj, J., Rich, S., Daly, K., Sale, M., & Chen, W.M. (2010). Robust relationship inference in genome-wide association studies. Bioinformatics, 26(22), 2867–2873.

Maples, B., Gravel, S., Kenny, E., & Bustamante, C. (2013). RFMix: a discriminative modeling approach for rapid and robust local-ancestry inference. Am. J. Hum. Genet., 93(2), 278–288.

Marcus, J., Ha, W., Barber, R., & Novembre, J. (2021). Fast and flexible estimation of effective migration surfaces. eLife, 10, e61927.

Martin, S., & Van Belleghem, S. (2017). Exploring evolutionary relationships across the genome using topology weighting. Genetics, 206(1), 429–438.

Martin, M., Patterson, M., Garg, S., Fischer, S., Pisanti, N., Klau, G., Schönhuth, A., & Marschall, T. (2016). WhatsHap: fast and accurate read-based phasing. bioRxiv.

Massarat, A., Lamkin, M., Reeve, C., Williams, A., D'Antonio, M., & Gymrek, M. (2024). haptools: a toolkit for admixture and haplotype analysis. Bioinformatics, 40(1), btad104.

Mathieson, I., & Mathieson, S. (2018). FADS1 and the timing of human adaptation to agriculture. Mol. Biol. Evol., 35(12), 2957–2970.

Matz, M., & Black, K. (2025). Spatial mapping of polygenic adaptation with random forests. Mol. Ecol. Resour..

McVean, G., Awadalla, P., & Fearnhead, P. (2002). A coalescent-based method for detecting and estimating recombination from gene sequences. Genetics, 160(3), 1231–1241.

Meisner, J., & Albrechtsen, A. (2018). Inferring population structure and admixture proportions in low-depth NGS data. Genetics, 210(2), 719–731.

Minh, B., Schmidt, H., Chernomor, O., Schrempf, D., Woodhams, M., Haeseler, A., & Lanfear, R. (2020). IQ-TREE 2: new models and efficient methods for phylogenetic inference in the genomic era. Mol. Biol. Evol., 37(5), 1530–1534.

Mirarab, S., & Warnow, T. (2015). ASTRAL-II: coalescent-based species tree estimation with many hundreds of taxa and thousands of genes. Bioinformatics, 31(12), i44–i52.

Mirzaei, S., & Wu, Y. (2017). RENT+: an improved method for inferring local genealogical trees from haplotypes with recombination. Bioinformatics, 33(7), 1021–1030.

Monroy Kuhn, J., Jakobsson, M., & Günther, T. (2018). Estimating genetic kin relationships in prehistoric populations. PLoS ONE, 13(4), e0195491.

Murrell, B., Weaver, S., Smith, M., Wertheim, J., Murrell, S., Aylward, A., Eren, K., Pollner, T., Martin, D., Smith, D., Scheffler, K., & Kosakovsky Pond, S. (2015). Gene-wide identification of episodic selection. Mol. Biol. Evol., 32(5), 1365–1371.

Myers, S., Bottolo, L., Freeman, C., McVean, G., & Donnelly, P. (2005). A fine-scale map of recombination rates and hotspots across the human genome. Science, 310, 321–324.

Nait Saada, J., Kalantzis, G., Shyr, D., Cooper, F., Robinson, M., Gusev, A., & Palamara, P. (2020). Identity-by-descent detection across 487,409 British samples reveals fine-scale population structure and ultra-rare variant associations. Nat. Commun., 11, 6130.

Naseri, A., Liu, X., Tang, K., Zhang, S., & Zhi, D. (2019). RaPID: ultra-fast, powerful, and accurate detection of segments identical by descent (IBD) in biobank-scale cohorts. Genome Biol., 20, 143.

Noskova, E., Ulyantsev, V., Koepfli, K.P., O'Brien, S., & Dobrynin, P. (2020). GADMA: genetic algorithm for inferring demographic history of multiple populations from allele frequency spectrum data. GigaScience, 9, giaa005.

Noskova, E., Abramov, N., Iliutkin, S., Sidorin, A., Dobrynin, P., & Ulyantsev, V. (2023). GADMA2: more efficient and flexible demographic inference from genetic data. GigaScience, 12, giad059.

Olazcuaga, L., Loiseau, A., Parrinello, H., Paris, M., Fraimout, A., Guilhot, R., Desneux, N., Lombaert, E., Malausa, T., Ravigne, V., & others (2020). A whole-genome scan for association with invasion success in the fruit fly Drosophila suzukii using contrasts of allele frequencies corrected for population structure. Mol. Biol. Evol., 37(8), 2369–2385.

Palamara, P., Terhorst, J., Song, Y., & Price, A. (2018). High-throughput inference of pairwise coalescence times identifies signals of selection and enriched disease heritability. Nat. Genet., 50, 1311–1317.

Patterson, M., Marschall, T., Pisanti, N., Iersel, L., Stougie, L., Klau, G., & Schönhuth, A. (2015). WhatsHap: weighted haplotype assembly for future-generation sequencing reads. J. Comput. Biol., 22(6), 498–509.

Pavlidis, P., Laurent, S., & Stephan, W. (2010). msABC: a modification of Hudson's ms to facilitate multi-locus ABC analysis. Mol. Ecol. Resour., 10(4), 723–727.

Peter, B. (2020). admixfrog: a method to identify and date introgressed segments of DNA. bioRxiv.

Petkova, D., Novembre, J., & Stephens, M. (2016). Visualizing spatial population structure with estimated effective migration surfaces. Nat. Genet., 48, 94–100.

Petr, M., Vernot, B., & Kelso, J. (2019). admixr –- R package for reproducible analyses using ADMIXTOOLS. Bioinformatics, 35(17), 3194–3195.

Petr, M., Haller, B., Ralph, P., & Racimo, F. (2023). slendr: a framework for spatio-temporal population genomic simulations on geographic landscapes. Peer Community J., 3, e121.

Pfeifer, B., Wittelsbürger, U., Ramos-Onsins, S., & Lercher, M. (2014). PopGenome: an efficient Swiss Army knife for population genomic analyses in R. Mol. Biol. Evol., 31, 1929–1936.

Pfeifer, B., & others (2024). TRIDENT: a Bayesian method for quantifying introgression. Bioinformatics.

Pickrell, J., & Pritchard, J. (2012). Inference of population splits and mixtures from genome-wide allele frequency data. PLoS Genet., 8(11), e1002967.

Plagnol, V., & Wall, J. (2006). Possible ancestral structure in human populations. PLoS Genet., 2(7), e105.

Kosakovsky Pond, S., Frost, S., & Muse, S. (2005). HyPhy: hypothesis testing using phylogenies. Bioinformatics, 21(5), 676–679.

Popli, D., Peyrégne, S., & Peter, B. (2023). KIN: a method to infer relatedness from low-coverage ancient DNA. Genome Biol., 24, 10.

Price, A., Patterson, N., Plenge, R., Weinblatt, M., Shadick, N., & Reich, D. (2006). Principal components analysis corrects for stratification in genome-wide association studies. Nat. Genet., 38, 904–909.

Pritchard, J., Stephens, M., & Donnelly, P. (2000). Inference of population structure using multilocus genotype data. Genetics, 155(2), 945–959.

Purcell, S., Neale, B., Todd-Brown, K., Thomas, L., Ferreira, M., Bender, D., Maller, J., Sklar, P., Bakker, P., Daly, M., & Sham, P. (2007). PLINK: a tool set for whole-genome association and population-based linkage analyses. Am. J. Hum. Genet., 81(3), 559–575.

Racimo, F., Marnetto, D., & Huerta-Sánchez, E. (2017). Signatures of archaic adaptive introgression in present-day human populations. Mol. Biol. Evol., 34(2), 296–317.

Ragsdale, A., & Gravel, S. (2019). Models of archaic admixture and recent history from two-locus statistics. PLoS Genet., 15(6), e1008204.

Raj, A., Stephens, M., & Pritchard, J. (2014). fastSTRUCTURE: variational inference of population structure in large SNP data sets. Genetics, 197(2), 573–589.

Ralf, A., Montiel González, D., Zhong, K., & Kayser, M. (2018). Yleaf: software for human Y-chromosomal haplogroup inference from next-generation sequencing data. Mol. Biol. Evol., 35(5), 1291–1294.

Rasmussen, M., Hubisz, M., Gronau, I., & Siepel, A. (2014). Genome-wide inference of ancestral recombination graphs. PLoS Genet., 10(5), e1004342.

Ray, D., Wang, L., Sohail, M., & Schrider, D. (2024). Introgression detection by semantic segmentation of haplotype matrices using a U-Net. bioRxiv.

Renaud, G., Slon, V., Duggan, A., & Kelso, J. (2015). schmutzi: estimation of contamination and endogenous mitochondrial consensus calling for ancient DNA. Genome Biol., 16, 224.

Ringbauer, H., Novembre, J., & Steinrücken, M. (2021). Parental relatedness through time revealed by runs of homozygosity in ancient DNA. Nat. Commun., 12, 5425.

Rubinacci, S., Ribeiro, D., Hofmeister, R., & Delaneau, O. (2021). Efficient phasing and imputation of low-coverage sequencing data using large reference panels. Nat. Genet., 53, 120–126.

Rubinacci, S., Hofmeister, R., Mota, B., & Delaneau, O. (2023). Imputation of low-coverage sequencing data from 150,119 UK Biobank genomes. Nat. Genet., 55, 1088–1090.

Salter-Townshend, M., & Myers, S. (2019). Fine-scale inference of ancestry segments without prior knowledge of admixing groups. Genetics, 212, 869–889.

Sanchez, T., Bray, E., Jobic, P., Guez, J., Letrouit, A.C., Prive, F., & Jay, F. (2023). dnadna: deep learning for population genetics. Bioinformatics, 39, btac765.

Santiago, E., Novo, I., Pardi\~nas, A., Saura, M., Wang, J., & Caballero, A. (2020). Recent demographic history inferred by high-resolution analysis of linkage disequilibrium. Mol. Biol. Evol., 37(12), 3642–3653.

Santiago, E., & Caballero, A. (2024). Estimation of the contemporary effective population size from SNP data while accounting for mating structure. Mol. Ecol. Resour..

Santiago, E., Köpke, C., & Caballero, A. (2025). Improved inference of population structure-aware effective population size. Nat. Commun..

Schaefer, N., Kelleher, J., & others (2024). tsdate: variational dating of tree sequences. Genetics.

Schiffels, S., & Durbin, R. (2014). Inferring human population size and separation history from multiple genome sequences. Nat. Genet., 46, 919–925.

Schiffels, S., & Wang, K. (2020). MSMC and MSMC2: the multiple sequentially Markovian coalescent. Methods Mol. Biol., 2090, 147–166.

Schrider, D., & Kern, A. (2018). Supervised machine learning for population genetics: a new paradigm. Trends Genet., 34(4), 301–312.

Schubert, M., Ermini, L., Sarkissian, C., J\'onsson, H., Ginolhac, A., Schaefer, R., Martin, M., Fernández, R., Kircher, M., McCue, M., & others (2014). Characterization of ancient and modern genomes by SNP detection and phylogenomic and metagenomic analysis using PALEOMIX. Nat. Protoc., 9, 1056–1082.

Sellinger, T., Awad, D., Moest, M., & Tellier, A. (2020). Inference of past demography, dormancy and self-fertilization rates from whole genome sequence data. PLoS Genet., 16(4), e1008698.

Sellinger, T., Johannes, F., & Tellier, A. (2024). Improved inference of population histories by integrating genomic and epigenomic data. eLife, 12, RP89470.

Setter, D., Mousset, S., Cheng, X., Nielsen, R., DeGiorgio, M., & Hermisson, J. (2020). VolcanoFinder: genomic scans for adaptive introgression. PLoS Genet., 16(6), e1008867.

Sheehan, S., & Song, Y. (2016). Deep learning for population genetic inference. PLoS Comput. Biol., 12(3), e1004845.

Shemirani, R., Belbin, G., Avery, C., Kenny, E., Gignoux, C., & Ambite, J. (2021). Rapid detection of identity-by-descent tracts for mega-scale datasets. Nat. Commun., 12, 3546.

Siewert, K., & Voight, B. (2017). Detecting long-term balancing selection using allele frequency correlation. Mol. Biol. Evol., 34(11), 2996–3005.

Siewert, K., & Voight, B. (2020). BetaScan2: standardized statistics to detect balancing selection utilizing substitution data. Genome Biol. Evol., 12(2), 3873–3877.

Skoglund, P., Northoff, B., Shunkov, M., Derevianko, A., Pääbo, S., Krause, J., & Jakobsson, M. (2014). Separating endogenous ancient DNA from modern day contamination in a Siberian Neandertal. Proc. Natl. Acad. Sci. U.S.A., 111, 2229–2234.

Skov, L., Hui, R., Shchur, V., Hobolth, A., Scally, A., Schierup, M., & Durbin, R. (2018). Detecting archaic introgression using an unadmixed outgroup. PLoS Genet., 14(9), e1007641.

Sol\'is-Lemus, C., & Ané, C. (2016). Inferring phylogenetic networks with maximum pseudolikelihood under incomplete lineage sorting. PLoS Genet., 12(3), e1005896.

Speidel, L., Forest, M., Shi, S., & Myers, S. (2019). A method for genome-wide genealogy estimation for thousands of samples. Nat. Genet., 51, 1321–1329.

Speidel, L., Cassidy, L., Davies, R., Hellenthal, G., Skoglund, P., & Myers, S. (2021). Inferring population histories for ancient genomes using genome-wide genealogies. Mol. Biol. Evol., 38(9), 3497–3511.

Spence, J., & Song, Y. (2019). Inference and analysis of population-specific fine-scale recombination maps across 26 diverse human populations. Sci. Adv., 5(10), eaaw9206.

Staab, P., Zhu, S., Metzler, D., & Lunter, G. (2015). scrm: efficiently simulating long sequences using the approximated coalescent with recombination. Bioinformatics, 31, 1680–1682.

Stamatakis, A. (2014). RAxML version 8: a tool for phylogenetic analysis and post-analysis of large phylogenies. Bioinformatics, 30(9), 1312–1313.

Steinrücken, M., Bhaskar, A., & Song, Y. (2014). A novel spectral method for inferring general diploid selection from time series genetic data. Ann. Appl. Stat., 8(4), 2203–2222.

Stern, A., Wilton, P., & Nielsen, R. (2019). An approximate full-likelihood method for inferring selection and allele frequency trajectories from DNA sequence data. PLoS Genet., 15(9), e1008384.

Stern, A., Speidel, L., Zaitlen, N., & Nielsen, R. (2021). Disentangling selection on genetically correlated polygenic traits via whole-genome genealogies. Am. J. Hum. Genet., 108(2), 219–239.

Stucki, S., Orozco-terWengel, P., Forester, B., Duruz, S., Colli, L., Masembe, C., Negrini, R., Landguth, E., Jones, M., NEXTGEN Consortium, & others (2017). High performance computation of landscape genomic models including local indicators of spatial association. Mol. Ecol. Resour., 17(5), 1072–1089.

Sugden, L., Atkinson, E., Fischer, A., Rong, S., Henn, B., & Ramachandran, S. (2018). Localization of adaptive variants in human genomes using averaged one-dependence estimation. Nat. Commun., 9, 703.

Svedberg, J., Shchur, V., Reinman, S., Nielsen, R., & Corbett-Detig, R. (2021). Inferring adaptive introgression using hidden Markov models. Mol. Biol. Evol., 38(5), 2152–2165.

Szpiech, Z., & Hernandez, R. (2014). selscan: an efficient multithreaded program to perform EHH-based scans for positive selection. Mol. Biol. Evol., 31(10), 2824–2827.

Takezaki, N., Nei, M., & Tamura, K. (2010). POPTREE2: software for constructing population trees from allele frequency data. Mol. Biol. Evol., 27(4), 747–752.

Tataru, P., & Bataillon, T. (2020). polyDFE: inferring the distribution of fitness effects and properties of beneficial mutations from polymorphism data. Methods Mol. Biol., 2090, 125–146.

Terhorst, J., Kamm, J., & Song, Y. (2017). Robust and scalable inference of population history from hundreds of unphased whole genomes. Nat. Genet., 49, 303–309.

Than, C., Ruths, D., & Nakhleh, L. (2008). PhyloNet: a software package for analyzing and reconstructing reticulate evolutionary relationships. BMC Bioinformatics, 9, 322.

Thornton, K. (2014). A C++ template library for efficient forward-time population genetic simulation of large populations. Genetics, 198, 157–166.

Torada, L., Lorenzon, L., Beddis, A., Isildak, U., Pattini, L., Mathieson, S., & Fumagalli, M. (2019). ImaGene: a convolutional neural network to quantify natural selection from genomic data. BMC Bioinformatics, 20, 337.

Tournebize, R., Chu, G., & Moorjani, P. (2022). Reconstructing the history of founder events using genome-wide patterns of allele sharing across individuals. PLoS Genet., 18(6), e1010243.

Tran, L., & others (2024). donni: deep-learning-based demographic inference from the SFS. Bioinformatics.

Vaughn, A., & Nielsen, R. (2024). Fast and accurate estimation of selection coefficients and allele histories from ancient and modern DNA. Mol. Biol. Evol., 41(8), msae156.

Vernot, B., & Akey, J. (2014). Resurrecting surviving Neandertal lineages from modern human genomes. Science, 343, 1017–1021.

Vitalis, R., Gautier, M., Dawson, K., & Beaumont, M. (2014). Detecting and measuring selection from gene frequency data. Genetics, 196(3), 799–817.

Wang, J. (2019). A parsimony estimator of the number of populations from a STRUCTURE-like analysis. Mol. Ecol. Resour., 19(4), 970–981.

Wang, K., Mathieson, I., O'Connell, J., & Schiffels, S. (2020). Tracking human population structure through time from whole genome sequences. PLoS Genet., 16(3), e1008552.

Wang, J., & Zhang, Z. (2021). GAPIT version 3: boosting power and accuracy for genomic association and prediction. Genomics, Proteomics & Bioinformatics, 19, 629–640.

Wegmann, D., Leuenberger, C., Neuenschwander, S., & Excoffier, L. (2010). ABCtoolbox: a versatile toolkit for approximate Bayesian computations. BMC Bioinformatics, 11, 116.

Weissensteiner, H., Pacher, D., Kloss-Brandstätter, A., Forer, L., Specht, G., Bandelt, H.J., Kronenberg, F., Salas, A., & Schönherr, S. (2016). HaploGrep 2: mitochondrial haplogroup classification in the era of high-throughput sequencing. Nucleic Acids Res., 44(W1), W58–W63.

Wohns, A., Wong, Y., Jeffery, B., Akbari, A., Mallick, S., Pinhasi, R., Patterson, N., Reich, D., Kelleher, J., & McVean, G. (2022). A unified genealogy of modern and ancient genomes. Science, 375(6583), eabi8264.

Xue, A., Schrider, D., & Kern, A. (2021). Discovery of ongoing selective sweeps within Anopheles mosquito populations using deep learning. Mol. Biol. Evol., 38(3), 1168–1183.

Yang, Z. (2007). PAML 4: phylogenetic analysis by maximum likelihood. Mol. Biol. Evol., 24(8), 1586–1591.

Yuan, K., Ni, X., Liu, C., Pan, Y., Deng, L., Zhang, R., Gao, Y., Ge, X., Liu, J., Ma, X., & others (2021). Refining models of archaic admixture in Eurasia with ArchaicSeeker 2.0. Nat. Commun., 12, 6232.

Zhang, C., Dong, S.S., Xu, J.Y., He, W.M., & Yang, T.L. (2019). PopLDdecay: a fast and effective tool for linkage disequilibrium decay analysis based on variant call format files. Bioinformatics, 35(10), 1786–1788.

Zhang, B., Biddanda, A., Gunnarsson, ., Cooper, F., & Palamara, P. (2023). Biobank-scale inference of ancestral recombination graphs enables genealogical analysis of complex traits. Nat. Genet., 55, 768–776.

Zhang, X., Kim, B., Singh, A., Sankararaman, S., Durvasula, A., & Lohmueller, K. (2023). MaLAdapt reveals novel targets of adaptive introgression from Neanderthals and Denisovans in worldwide human populations. Mol. Biol. Evol., 40(1), msad001.

Zheng, X., Levine, D., Shen, J., Gogarten, S., Laurie, C., & Weir, B. (2012). A high-performance computing toolset for relatedness and principal component analysis of SNP data. Bioinformatics, 28(24), 3326–3328.

Zhou, X., & Stephens, M. (2012). Genome-wide efficient mixed-model analysis for association studies. Nat. Genet., 44, 821–824.

Zhou, Y., Browning, S., & Browning, B. (2020). A fast and simple method for detecting identity-by-descent segments in large-scale data. Am. J. Hum. Genet., 106(4), 426–437.
