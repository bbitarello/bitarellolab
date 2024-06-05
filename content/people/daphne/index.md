---
title: "Daphne Hansell"

subtitle: "Public health Major and Chinese Minor ('24)"

excerpt: "Public health Major and Chinese Minor ('24)"

date: "2024-06-05"
  
# layout options: single or single-sidebar
layout: single-sidebar
links:
- icon: github
  icon_pack: fab
  name: Github
  url: https://github.com/daphnehanse11

tags: 
- balancing selection
- population genetics
- teaching

categories: 
- research projects
- alumni

featured: true
draft: false
---


Pronouns: she/her/hers 

Fun Fact: I love to bake, listen to podcasts and feed stray cats. 

In the Lab: Joined summer 2023 to work on an R package to calculate balancing selection. My interests are all things R! Also worked on developing an R package for the B215: Biostatistics with R course. Stayed until graduating (Spring 2024).


-----------------------------------------------------------------

## balselr - Balancing Selection Tests in R

Broader project: [Balancing selection: mechanisms, timescales, and signatures. ](https://bitarellolab.netlify.app/project/balancingselection/)/

Long-term balancing selection (LTBS) is vital for population adaptability and resilience. LTBS includes mechanisms such as heterozygote advantage, negative frequency dependency selection, and fluctuating selection, all of which maintain polymorphisms segregating in populations.  We previously introduced the Non-central Deviation (NCD) statistic as a statistically powerful and fast method to identify LTBS. Widespread adoption of NCD and several other LTBS methods developed since has been limited due to specialized knowledge requirements and implementation inaccuracies. Our package described here bridges this gap by providing an accessible interface, enabling researchers to leverage single-locus and genomic data effortlessly, even with basic R proficiency. We name this package balselr —  balancing selection in R. balselr is a comprehensive R package designed to detect LTBS using the NCD statistics as initially described. balselr features include: a) preparation of input files from popular data formats, such as VCF files for SNP data (e.g. functions `read_vcf()` and `parse_vcf()`);  b) implementation of NCD1 and NCD2 calculations (`ncd1()` and `ncd2()` functions, respectively); help pages and tutorials to further aid researchers in understanding LTBS prevalence and implications in population and evolutionary genetics. This dedicated package will make it easier for individuals with basic proficiency in R to run the NCD method effectively, allowing wider adoption of NCD and advancing understanding of balancing selection’s evolutionary significance across organisms. We implemented comprehensive automated package tests to ensure, for example, that if a  function code is changed, the output stays the same, that functions produce the correct type of object, and to compare an expected calculation to the functions’ output. Ongoing and future work include: implementing more tests for the existing functions; including other LTBS methods beyond NCD that are currently not implemented in R (e.g. BetaScan and BalLeRMix); integrating the `balselr` and `slendr` (Population Genetic Simulations in R) packages and providing tutorial materials on how to properly assess statistical power for different organisms with forward simulations. In brief, the current package and the planned updates will make it easier for researchers with minimal programming experience to use NCD and other LTBS methods on their data. The development version is available at \url{https://github.com/bitarellolab/balselr.}


<i class="fa-solid fa-link"></i> [BMC Summer Research Program Webpage](https://www.brynmawr.edu/inside/academic-information/research/summer-science-research/summer-2024-program/biology-research-projects-2023#dhansell)