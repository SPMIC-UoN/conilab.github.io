---
title: "CoNI Lab - RubiX"
layout: textlay
excerpt: "RubiX"
sitemap: false
permalink: /software/rubix/
---

<!--figure>
<img src="{{ site.url }}{{ site.baseurl }}/images/software/cudimot.jpg" width="60%">
</figure-->

# RubiX: Resolutions Unified for Bayesian Inference of Crossings

The trade-off between signal-to-noise ratio (SNR) and spatial specificity governs the choice of spatial 
resolution in magnetic resonance imaging (MRI); diffusion-weighted (DW) MRI is no exception. Images of lower 
resolution have higher signal to noise ratio, but also more partial volume artifacts. 

The RubiX (Resolutions Unified for Bayesian Inference of Crossings) generative model represents a data-fusion framework, where data from all resolutions are combined through a spatial and a local model. Priors on the model parameters impose some spatial regularization constraints that assist model identifiability when the high resolution data are of very low SNR. The generative model is inverted using Markov-Chain Monte-Carlo (MCMC) and the posterior distribution of the parameters is estimated. 

The only required libraries are FSL (FMRIB Software Library) and CUDA toolkit.
**You will need an NVIDIA GPU.***

## Installation

### Downloading binaries

 - [RubiX for CUDA 9.2](https://github.com/SPMIC-UoN/fdt/releases/download/2103.0/rubix_cuda9.2.tar.gz)

## Citation

If you use RubiX in publications, please cite of the following:

Sotiropoulos SN, Jbabdi S, Andersson JL, Woolrich MW, Ugurbil K, Behrens TE. 
*"RubiX: combining spatial resolutions for Bayesian inference of crossing fibers in diffusion MRI."*
**IEEE Trans Med Imaging. 2013; 32(6):969-82. doi: 10.1109/TMI.2012.2231873.**

Sotiropoulos SN, Hernández-Fernández M, Vu AT, Andersson JL, Moeller S, Yacoub E, Lenglet C, Ugurbil K, Behrens TEJ, Jbabdi S
*"Fusion in diffusion MRI for improved fibre orientation estimation: An application to the 3T and 7T data of the Human Connectome Project."*
**Neuroimage. 2016; 134:396-409. doi: 10.1016/j.neuroimage.2016.04.014.**
