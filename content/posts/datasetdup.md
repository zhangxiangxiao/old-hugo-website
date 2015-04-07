---
title: "Dataset Duplication Issues for Text Understanding from Scratch"
date: "2015-04-07"
description: "Details on the dataset duplication issues discovered for the technical report"
categories:
    - "research"
---

On April 6th 2015, we discovered some issues related to the datasets used in our technical report ["Text Understanding from Scratch"](http://arxiv.org/abs/1502.01710). These issues include multiple instances of the same sample, and overlaps between training and testing data. These issues were first discovered by Alec Radford, head of research at [indico](https://indico.io), who carefully checked a few of our released datasets and found out this issues. I want offer my thanks to him.

Here is what I am going to do to solve this issue:

1. Remove Amazon review and Sogou news datasets from release. The DBPedia dataset is completely clean.
2. Put a notification in our technical report's first page, untill we can resolve these issues and obtain new experiment results. This is already submitted to arXiv, but it may take a few days to appear online.
3. Solve the issues in the datasets, and redo all related experiments.

I apologize for any inconvenience and inaccurate information resulted from this. I am aware that this technical report drew a lot of attention from fellow researchers all around the world, and I will do my best to resolve the issues as soon as possible.

### What are the issues?

As said before, the issues are multiple instances of the same sample, and overlaps between training and testing data. I am still investigating the reasons behind these issues, but so far it looks like there were duplications from the datasets' original owners and distributors. Below is a break down of the issues for the datasets in the original technical report.

* DBPedia
    * Duplication in Train: 0 of 560000, 0 %
    * Duplication in Test: 0 of 70000, 0 %
    * Overlap: 0 of 70000, 0%

* Yahooo Answers
    * Duplication in Train: 434 of 1400000, 0%
    * Duplication in Test: 0 of 50000, 0%
    * Overlap: 32 of 50000, 0%

* Amazon Review Full Score
    * Duplication in Train: 1434980 of 5000000, 29%
    * Duplication in Test: 175671 of 1250000, 14%
    * Overlap: 513193 of 1250000, 41%

* Amazon Review Polarity
    * Duplication in Train: 1854042 of 6000000, 31%
    * Duplication in Test: 162916 of 900000, 18%
    * Overlap: 352296 of 900000, 39%

* AGNews Corpus
    * Duplication in Train: 13423 of 160000, 8%
    * Duplication in Test: 16 of 4400, 0%
    * Overlap: 655 of 4400, 15%

* Sogou News Corpus
    * Duplication in Train: 194783 of 750000, 26%
    * Duplication in Test: 6876 of 50000, 14%
    * Overlap: 15789 of 50000, 32%

### Is the Crepe code affected?

The release of [Crepe](https://github.com/zhangxiangxiao/Crepe) is idependent of the datasets. It is currently not affected by this issue. Also, because the DBPedia dataset is clean, the example usage for Crepe is still totally valid. The DBPedia dataset is kept online.

That said, if you found bugs or issues with Crepe code, please let me know.
