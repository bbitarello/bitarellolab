---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "GnomAD API Query Tool"
subtitle: "If you've been trying to find an API query tool for gnomAD, you found it!"
summary: ""
authors: [Bárbara Bitarello]
tags: [software, gnomAD, computational biology, JSON, API, allele frequencies, tutorial]
categories: [post, tutorial]
date: 2020-07-21T19:09:57-04:00
lastmod: 2020-07-21T19:09:57-04:00
featured: true
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: ""
  focal_point: ""
  preview_only: false

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["internal-project"]` references `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects: []
---
Tl; dr, I love to tell a good story. If you don't wanna read that, no worries. Just [skip ahead](#a-brief-tutorial) or get [straight to business](https://github.com/crankysparrow/computationalbio)!

Now, to the story. 

I have been working on a project where I was using population allelic frequencies for about 6,000 SNPs (single nucleotide polymorphisms) for CEU (North Americans from UTAH with European ancestry) individuals from the [1000 Genomes Project](https://www.internationalgenome.org/faq/what-do-your-population-codes-ceu-or-tsi-mean/). We have our own copy of this dataset in our computer, and it's relatively straightforward to get those frequencies from vcf files. All good.

Then, I decided I should check whether CEU individuals were a good proxy for allelic frequencies in Europeans (excluding Finnish, which due to their interesting demographic history are usually excluded for this kind of analysis). I wanted to do this by comparing the allelic frequencies for CEU from the 1000 Genomes (404 individuals) to the tens of thousands 'non-Finnish European' samples from the the Genome Aggregation Database ([gnomAD](https://gnomad.broadinstitute.org/)). Hence, I went to their website and thought to myself that downloading their entire dataset and calculating allelic frequencies did not strike me as elegant. Neigther did the idea of manually quering ~6,000 SNP IDs on the gnomAD browser (which is great if you only have a few SNPs to look at). No batch submission option was available.

There must be a well-established gnomAD API query tool available, right? Wrong! No such tool. Of course, I did find some solutions people made here and there, but none of them did exactly what I wanted.

Enters [Michelle Enos](https://michelleenos.com), who is an awesome web developper and is entirely foreign to the field of computational biology. I explained what I needed and they made the tool I needed in javascript (which I am not fluent in). Modest, @crankysparrow thought this wasn't much, 'a fun little project'. But looking at biostars [^1], I begged to differ: we [*NEED* this](https://www.biostars.org/p/375279/)!

Even cooler, after they did the hard work, I was able to tweek the script to include some options that computational biologists would appreciate. Feedback is appreciated. 

So here it is, from us, to you. A gnomAD API query tool that gathers gnomad-genomes or gnomad-exomes allelic frequencies for a list of SNP IDs for a population defined by the user. [Link here](https://github.com/crankysparrow/computationalbio). Enjoy!

##
[^1]: Biostars is the stackoverflow of computational biologists. 

## A brief tutorial:

Requirements:

*node must be installed 

*command line

*npm must be installed

*Note*: instructions available at the [repo](https://github.com/crankysparrow/computationalbio).


## Input file

This should be a .json file with the SNP IDs you would like to query. IF you have a regular text file with one ID per line, you can use our [conversion tool](https://github.com/crankysparrow/computationalbio/blob/master/scripts/readIDs.js):

```
node scripts/readIDs.js --input path/<your_text_file_with_SNP_ids>.txt
```

This will produce an output file with the same name, but ending in '.json'. Then you can run:

```
node scripts/gnomad_query.js --input input/<our_SNP_IDs>.json --pop 'NFE' --db 'GNOMAD'
```

Enjoy!


