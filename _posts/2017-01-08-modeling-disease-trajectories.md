---
layout: post
title: Modeling Disease Trajectories 
tags: research 
---

My next project will (with high probability) involve modeling "disease trajectories" in some form. Though a concrete problem definition is still a few months away, I ran into some interesting recent work in this space that I will be reading soon. This post simply lists and quotes content from these papers that I found interesting. I will append to this post as I come across more.

## Disease Trajectory Maps
*Peter Schulam, Raman Arora. [NIPS '16][1].*

Peter approaches this space from the application point of view, and has a bunch of other papers in this domain since 2015:

   * Integrative Analysis using Coupled Latent Variable Models
for Individualizing Prognoses. [JMLR '16.][2] 
   * A Framework for Individualizing Predictions of Disease
Trajectories by Exploiting Multi-Resolution Structure. [NIPS '15.][3] 
   * Clustering Longitudinal Clinical Marker Trajectories from Electronic Health
Data: Applications to Phenotyping and Endotype Discovery. [AAAI '15.][4] 

His coauthor [Suchi Saria](http://www.suchisaria.com/) is also active in this space.
He links to an exciting commentary on [predictive analytics in healthcare](https://rockhealth.com/reports/predictive-analytics/).

The crux of [NIPS '16][1] is the following:

> [...] we propose the Disease Trajectory Map (DTM), a novel probabilistic model that learns low-dimensional representations of sparse and irregularly sampled longitudinal data.

"Sparse and irregularly sampled longitudinal data" is essentially point process data.

I usually find representation-learning papers short on the evaluation front, simply because the evaluation ill-defined. A useful proxy is to use the learned representation in a machine learning task with ground truth, such as classification. The evaluation presented in this paper is does not do this and is unfamiliar to me, but I think the gist is that DTM's corraborate what is already known medically, as shown via some hypothesis and association tests.

It still appears to be a primarily exploratory technique, potentially useful as input to classifiers further down the learning pipeline. The usual skepticism of the lack statistical guarantees and robustness apply.

## Patient Flow Prediction via Discriminative Learning of Mutually-Correcting Processes
*Hongteng Xu, Weichang Wu, Shamim Nemati, and Hongyuan Zha. [TKDE '16][5]*

Hongteng approaches this space from the theoretical point of view. He has a bunch of earlier work on point processes with his advisor (and prolific point process expert) [Hongyuan Zha](http://www.cc.gatech.edu/~zha/).

This paper specifically is not about how diseases evolve, but on how patients move between different care units (CUs) in a medical facility.

> In this paper, we focus on an important problem of predicting the so-called "patient flow" from longitudinal electronic health records (EHRs). [...] jointly predicting
patients’ destination CUs and duration days.

## Longitudinal Mixed Membership Trajectory Models for Disability Survey Data
*Daniel Manrique-Vallier. [Annals of Applied Statistics, '14][6].*

This is pretty far removed from disease trajectory modeling, but has a nice survey that I want to peruse later. The paper essentially combines "Latent Trajectory Models", which jointly model trajectories and clusters, and mixed memborship models, which permit soft-assignments of data points to clusters. It is easy to see its applicability to disease trajectories. 

[1]: http://pschulam.com/papers/schulam+arora_nips_2016.pdf
[2]: http://pschulam.com/papers/schulam+saria_jmlr_2016.pdf
[3]: http://papers.nips.cc/paper/5873-a-framework-for-individualizing-predictions-of-disease-trajectories-by-exploiting-multi-resolution-structure.pdf
[4]: http://pschulam.com/papers/schulam+wigley+saria_aaai_2015.pdf
[5]: https://arxiv.org/pdf/1602.05112.pdf
[6]: https://arxiv.org/pdf/1309.2324.pdf
