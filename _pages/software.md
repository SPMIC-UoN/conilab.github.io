---
title: "CoNI Lab - Software"
layout: textlay
excerpt: "Software"
sitemap: false
permalink: /software/
---

# Software

We have a track record of developing and publicly releasing software
for neuro-image processing and analysis.

[FSL](#fsl-toolboxes), [CUDIMOT](#cudimot), [NFacT](#nfact),
[aFODs](#afods), [MPPs](#multimodal-processing-pipelines), [HCP WM Atlases](#hcp-white-matter-atlases), [Large Collaborative Projects](#large-collaborative-projects)


### FSL Toolboxes
<figure>
<img src="{{ site.url }}{{ site.baseurl }}/images/software/FSL_logo.jpg" width="15%">
</figure>

We have led the development or contributed to a number of toolboxes that are publicly released through [FSL](https://fsl.fmrib.ox.ac.uk/fsl/fslwiki){:target="_blank"}, one of the
de-facto software standards for multi-modal neuroimage processing,
used by thousands of researchers in hundreds of institutions
worldwide. These include:
* [XTRACT](https://fsl.fmrib.ox.ac.uk/fsl/fslwiki/XTRACT){:target="_blank"},
  for automated tractography in the human and non-human primate brain
* [Bedpostx / Bedpostx_gpu]({{ site.url }}{{ site.baseurl }}/software/bedpostx),
  for Bayesian estimation of WM fibre orientations from diffusion MRI
  data using a number of forward models
* [Qboot](https://fsl.fmrib.ox.ac.uk/fsl/fslwiki/FDT/UserGuide#qboot_-_Estimation_of_fibre_orientations_using_q-ball_ODFs_and_residual_bootstrap){:target="_blank"} for stochastic estimation of diffusion and fibre ODFs from diffusion MRI data
* [Probtrackx / Probtrackx_gpu]({{ site.url }}{{ site.baseurl }}/software/probtrackx) for probabilistic tractography, connectivity fingerprinting and mapping
* [Eddy](https://fsl.fmrib.ox.ac.uk/fsl/fslwiki/eddy){:target="_blank"}
for distortion, outlier, motion correction
* [Eddyqc](https://fsl.fmrib.ox.ac.uk/fsl/fslwiki/eddyqc/UsersGuide){:target="_blank"}
  for quality control and assessment of diffusion MRI data.

*[Lab contributors]({{ site.url }}{{ site.baseurl }}/team): Matteo Bastiani, Shaun Warrington, Stam Sotiropoulos*

<hr>


### CUDIMOT
<figure>
<img src="{{ site.url }}{{ site.baseurl }}/images/software/cudimot.jpg" width="15%">
</figure>

The CUda DIffusion MOdeling Toolbox (CUDIMOT) is a C front-end that allows the definition and fitting of
non-linear voxelwise models to MRI data using CUDA and GPUs (see
relevant [paper](https://doi.org/10.1016/j.neuroimage.2018.12.015){:target="_blank"}). The user
needs only to specify a cost function and model fitting
options (deterministic nonlinear fitting-Levenberg Marquardt, Bayesian
fitting-MCMC, priors, noise model) in C header file and the
software translates these choices to CUDA code, which is then compiled
to a binary that performs model fitting and can run on GPUs. The toolbox
has been made with tissue microstructure models for diffusion MRI data
in mind, but it can be used for any voxel-wise model of MRI data. 

[CUDIMOT and precompiled binaries for NODDI-Watson and 
NODDI-Bingham models]({{ site.url }}{{ site.baseurl }}/software/cudimot){:target="_blank"}
are available.

*[Lab contributors]({{ site.url }}{{ site.baseurl }}/team#alumni): Moises Hernandez-Fernandez, Stam Sotiropoulos*
<hr>

### NFacT
<figure>
<img src="{{ site.url }}{{ site.baseurl }}/images/software/nmf.jpg" width="20%">
</figure>

NFacT (Non-negative matrix FACtorisation of Tractography data) is a framework for performing data-driven decomposition of
whole-brain tractography. This allows concurrent delineation of white matter (WM) bundles
and grey matter (GM) networks (see relevant
[paper](https://www.biorxiv.org/content/10.1101/2020.03.09.965079v1){:target="_blank"}). We
also allow non-negative dual regression for projecting group-wise
WM/GM components to individual subjects.

[NFacT routines](https://github.com/ethompson93/Data-driven-tractography){:target="_blank"}
are available in python.

*[Lab contributors]({{ site.url }}{{ site.baseurl }}/team): Elinor Thompson, Matteo Bastiani, Stam Sotiropoulos*

<hr>


### aFODs
<figure>
<img src="{{ site.url }}{{ site.baseurl }}/images/software/afods.jpg" width="20%">
</figure>

Asymmetric Fibre Orientation Distribution functions (aFODs) can
represent within-voxel asymmetric fibre patterns (such as fanning
in/out, bending, Y-branching, see relevant
[paper](https://doi.org/10.1016/j.neuroimage.2017.06.050){:target="_blank"}). We
provide code that allows the estimation of asymmetric FODs from diffusion
MRI data using spherical harmonics and regularised spherical deconvolution.

[AFODs routines](https://git.fmrib.ox.ac.uk/matteob/aFOD){:target="_blank"} are available
as a python package. 

*[Lab contributors]({{ site.url }}{{ site.baseurl }}/team): Matteo Bastiani, Stam Sotiropoulos*

<hr>


### Multimodal Processing Pipelines
<figure>
<img src="{{ site.url }}{{ site.baseurl }}/images/software/pipelines.jpg" width="15%">
</figure>

[Multi-modal processing pipelines (MPPs)](https://doi.org/10.5281/zenodo.3624973)
(written in bash) are for a number of neuroimaging
modalities, including structural MRI, diffusion MRI and functional
MRI. The pipelines perform a number of steps needed on the raw data,
including distortion and motion correction, cross-modality
alignment, denoising, template-space registrations, tissue segmentation, cortical
surface extractions.

*[Lab contributors]({{ site.url }}{{ site.baseurl }}/team): Alireza Kisomi, Stam Sotiropoulos*

<hr>

### HCP White Matter Atlases
<figure>
<img src="{{ site.url }}{{ site.baseurl }}/images/software/hcp_wm.jpg" width="15%">
</figure>

These comprise of Diffusion Tensor Imaging (DTI) and white matter (WM)
tractography atlases derived using 1065 subjects from the young adult Human
Connectome Project (HCP). For the DTI templates, the minimally preprocessed diffusion MRI data were used to fit diffusion tensors in each of the
subjects. The tensors were non-linearly transformed to MNI space and averaged. The average tensor was then eigen-decomposed to give
orientation and microstructure maps. These DTI templates are also available in [FSL](https://fsl.fmrib.ox.ac.uk/fsl/fslwiki/Atlases){:target="_blank"}.

WM tract atlases were generated using probabilistic tractography and XTRACT in
each of the 1065 subjects (see relevant [paper](https://www.biorxiv.org/content/10.1101/804641v2){:target="_blank"}). The resultant
spatial distributions were binarised and averaged, giving a population-probability map for each tract. The *human* WM atlases are also accompanied by WM atlases of the *macaque* brain (obtained using 6 animals).

All [WM atlases](https://github.com/swarrington1/WM_atlases){:target="_blank"} are provided.

*[Lab contributors]({{ site.url }}{{ site.baseurl }}/team): Shaun Warrington, Stam Sotiropoulos*

<hr>

### RubiX
<!--figure>
<img src="{{ site.url }}{{ site.baseurl }}/images/software/cudimot.jpg" width="15%">
</figure-->

Resolutions Unified for Bayesian Inference of Crossings

[Further information and binaries]({{ site.url }}{{ site.baseurl }}/software/rubix){:target="_blank"}

*[Lab contributors]({{ site.url }}{{ site.baseurl }}/team#alumni): Moises Hernandez-Fernandez, Stam Sotiropoulos*
<hr>

### Large Collaborative Projects
<figure>
<img src="{{ site.url }}{{ site.baseurl }}/images/software/hcp_logo.jpg" width="20%">
</figure>
* We have been major partners in the NIH-funded
[Human Connectome Project](https://www.humanconnectome.org/){:target="_blank"}
(HCP), contributing to both the [HCP processing pipelines](https://github.com/Washington-University/HCPpipelines){:target="_blank"} and the public data
releases (*1,200 young adult subjects* with cutting-edge data quality and
multiple neuroimaging modalities).

<figure>
<img src="{{ site.url }}{{ site.baseurl }}/images/software/dhcp_logo.jpg" width="20%">
</figure>
* We have been major partners in the ERC-funded [developing
Human Connectome Project](http://www.developingconnectome.org){:target="_blank"}
(dHCP), leading the
[dHCP diffusion MRI processing pipelines](https://git.fmrib.ox.ac.uk/matteob/dHCP_neo_dMRI_pipeline_release){:target="_blank"} development
and contributing to the public data releases (*500 neonates*, 37-44
weeks post-conception age, with structural, functional and diffusion
MRI acquired).

<figure>
<img src="{{ site.url }}{{ site.baseurl }}/images/software/ukbiobank_logo.jpg" width="20%">
</figure>
* Our tools have been used in the diffusion MRI processing for
  generation of *imaging-derived phenotypes (IDPs)* from the data of
  the population-level
  [UK Biobank Imaging](https://imaging.ukbiobank.ac.uk){:target="_blank"}
  study, which scans *100,000 individuals* with 6 neuroimaging
  modalities (T1w, T2w-FLAIR, SWI, dMRI, resting-state fMRI, task fMRI).

<figure>
<img src="{{ site.url }}{{ site.baseurl }}/images/software/qunex.jpg" width="10%">
</figure>
* We are collaborating with the [Anticevic](https://medicine.yale.edu/lab/anticevic){:target="_blank"} and [Repovs](http://mblab.si/){:target="_blank"}  labs in the
  development of the [QuNex](https://qunex.yale.edu){:target="_blank"}
  integrative environment for neuroimage processing and analysis.


<p> &nbsp; </p>
