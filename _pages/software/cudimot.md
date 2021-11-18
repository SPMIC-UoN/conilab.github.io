---
title: "CoNI Lab - cuDIMOT"
layout: textlay
excerpt: "cuDIMOT"
sitemap: false
permalink: /software/cudimot
---

<figure>
<img src="{{ site.url }}{{ site.baseurl }}/images/software/cudimot.jpg" width="60%">
</figure>

# CUDA Diffusion Modelling Toolbox (cuDIMOT)

CUDIMOT is a toolbox, part of [FSL](https://fsl.fmrib.ox.ac.uk/fsl/fslwiki) 
(FMRIB Software Library), for designing and implementing MRI nonlinear models 
on Graphics Processing Units (GPUs).

The toolbox includes:

 - An easy C interface for specifying your model parameters and functions.
 - Three nonlinear optimisation routines:
   - MCMC
   - Levenberg-Marquardt
   - Grid Search
 - Can use different models concatenating outputs/inputs
 - Gaussian and Rician noise modelling
 - Parameters bounds and Priors: Gaussian, Gamma, ARD, sin()
 - Bayesian information criterion (BIC) and Akaike information criterion (AIC)
 - Several diffusion MRI models implemented: Ball&Sticks, NODDI-Watson, NODDI-Bingham, Ball&Rackets
 - Can use multiple GPUs to fit a dataset

The only required libraries are FSL (FMRIB Software Library) and CUDA toolkit.
**You will need an NVIDIA GPU.***

## Installation

If you want to use the toolbox for implementing your own models you can download it here:

[cudimot.zip]()

### Downloading individual cuDIMOT NODDI_Watson binaries and scripts

 - Create a directory for storing CUDIMOT binary files and set ``CUDIMOT`` variable 
   with that path - for instance: ``export CUDIMOT=/home/moises/CUDIMOT``
 - Download the correct ``NODDI_Watson`` file for your CUDA version
 - Unzip ``NODDI_Watson`` file
 - Copy all the uncompressed files from ``NODDI_Watson/bin/*`` directory to your ``$CUDIMOT/bin/*`` directory
 - To fit the model use:
   ``$CUDIMOT/bin/Pipeline_NODDI_Watson.sh [SubjectDirectory]``
 - The pipeline uses SGE for sending jobs to a GPU queue (name of queue can be redefined in ``FSLGECUDAQ`` environment variable).
 - If you want to run the tool without using SGE, the environment variable ``SGE_ROOT`` should be unset: ``unset SGE_ROOT``
 - If you have several GPUs, you can use the option ``-NJOBS X`` to create X different GPUs jobs, each one for processing 
   a subpart of the dataset (this option can process the dataset very fast)
 - Requirements: NVIDIA GPU compute capability >= 3.0

[cudimot NODDI_Watson for CUDA 9.1](http://users.fmrib.ox.ac.uk/~moisesf/cudimot/NODDI_Watson/CUDA_9.1/NODDI_Watson.zip)
[cudimot NODDI_Watson for CUDA 10.0](http://users.fmrib.ox.ac.uk/~moisesf/cudimot/NODDI_Watson/CUDA_10.0/NODDI_Watson.zip)
[cudimot NODDI_Watson for CUDA 10.1](http://users.fmrib.ox.ac.uk/~moisesf/cudimot/NODDI_Watson/CUDA_10.1/NODDI_Watson.zip)
[cudimot NODDI_Watson for CUDA 10.2](http://users.fmrib.ox.ac.uk/~moisesf/cudimot/NODDI_Watson/CUDA_10.2/NODDI_Watson.zip)

 - You can also download cuDIMOT ``NODDI_Bingham`` binaries and scripts:
 - Please follow the same steps as for ``NODDI_Watson``, but using ``NODDI_Bingham`` files
 - To fit the model use:
   ``$CUDIMOT/bin/Pipeline_NODDI_Bingham.sh [SubjectDirectory]``

[cudimot NODDI_Bingham for CUDA 9.1](http://users.fmrib.ox.ac.uk/~moisesf/cudimot/NODDI_Bingham/CUDA_9.1/NODDI_Bingham.zip)
[cudimot NODDI_Bingham for CUDA 10.0](http://users.fmrib.ox.ac.uk/~moisesf/cudimot/NODDI_Bingham/CUDA_10.0/NODDI_Bingham.zip)
[cudimot NODDI_Bingham for CUDA 10.1](http://users.fmrib.ox.ac.uk/~moisesf/cudimot/NODDI_Bingham/CUDA_10.1/NODDI_Bingham.zip)
[cudimot NODDI_Bingham for CUDA 10.2](http://users.fmrib.ox.ac.uk/~moisesf/cudimot/NODDI_Bingham/CUDA_10.2/NODDI_Bingham.zip)

## Implementing your own model

[Read here how to use the tool for implementing your own model.]({{ site.url }}{{ site.baseurl }}/software/cudimot_own_model)

## Citation

If you use cuDIMOT in publications, please cite [this paper](https://www.sciencedirect.com/science/article/pii/S1053811918321591):

Hernandez-Fernandez M., Reguly I., Jbabdi S, Giles M, Smith S., Sotiropoulos S.N. 
*"Using GPUs to accelerate computational diffusion MRI: From microstructure estimation to tractography and connectomes."*
**NeuroImage 188 (2019): 598-615.**
