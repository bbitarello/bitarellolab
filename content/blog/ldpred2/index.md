---
author: Bárbara Bitarello
categories:
- blog
tags:
- software
- ldpred2
- ldpred
- C+T
- PRS
- polygenic risk score
date: "2020-07-02"
draft: false
excerpt: Summarizing the new LDpred2 method
layout: single
title: "LDpred2: Better, Faster, Stronger"
---

Today we discussed the new version of LDpred: LDpred2 (preprint [here](https://www.biorxiv.org/content/10.1101/2020.04.28.066720v1.full.pdf)).

The preprint is short and technical and does not go through the trouble of explaining the models implemented in LDpred1 and LDpred2, since that has been described in great detail in the [original publication](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4596916/). Rather, this seems to be a ‘Bioinformatics’ style preprint that goes straight to the novelties:

LDpred2 runs in R instead of in Python like its predecessor;

LDpred2 has four implementations (LDpred2-inf, LDpred2, LDpred2-sparse, LDpred2-auto), compared to two from its predecessor (LDpred-inf, LDpred);

LDpred2-auto estimates both p (proportion of causal variants) and h2 (SNP heritability) from the test data, without requiring a validadation set for hyperparameter optimization (this option is great, provided that appropriate QC is performed in the summary statistics);

LDpred2-sparse allows some some of the causal variants to actually have effect sizes of zero;

LDpred2 parallelizes both the grid of hyperparameters as well as the chromosomes (run in parallel) via C++, which makes it faster;

By changing how the LD radius is defined in the weight estimation (Gibbs sampler) step, it performs much better in regions of long-range LD such as the MHC region. Instead of defining a SNP window of aM\3000 in each direction (M is the number of causal variants, roughly 1Mb), it defines the window in terms of genetic distances and the default value is 3 cM;

Personally, I have spent quite some time figuring out the error messages that LDpred provides, as well as studying the models that it implements. Also, I am a big R fan, so it would be a shame to see all my efforts with LDpred go to waste: I am definitely switching to LDpred2, which runs 100% in R. The first author has kindly provided [a tutorial](https://privefl.github.io/bigsnpr/articles/LDpred2.html), which I see as a big bonus.

TL;dr: If you are already using LDpred1 (i.e, you have spent time figuring out how it runs, as well as the underlying models), it is definitely worth switching to LDpred2. If you are just beginning your exploration of Polygenic Risk Scores, a less overwhelming approach would be to start with C+T (clumping and thresholding), which is very simple, fast, effective, and requires nothing too fancy. If you are already using another fancy approach such as lassosum, LDpred2 does not seem to do better than that, so I would stick with what is working for you.

I will write something about my experience running LDpred2 in the coming weeks.
