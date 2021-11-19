---
title: "CoNI Lab - Probtrackx"
layout: textlay
excerpt: "Probtrackx"
sitemap: false
permalink: /software/probtrackx
---

# Probtrackx GPU

Tool for performing probabilistic tractography on NVIDIA GPUs

Part of [FSL](https://fsl.fmrib.ox.ac.uk/fsl/fslwiki) (FMRIB Software Library)

For information about the functionality of the tool, see the [PROBTRACKX User Guide](https://fsl.fmrib.ox.ac.uk/fsl/fslwiki/FDT/UserGuide#BEDPOSTX)

This page provides binary downloads of the GPU version of Probtrackx. 

## Speedup

GPU Probtrackx offers accelerations of *more than 200 times using a single GPU compared to 
a single CPU core: 1 GPU ≈ 230 CPU cores.*

<figure>
<img src="{{ site.url }}{{ site.baseurl }}/images/software/probtrackx/times_ptx.png" width="70%">
</figure>

*a) Execution times (in logarithmic scale) and speedup (standard deviation σ is also shown) in the reconstruction of 15 tracts comparing a GPU-based with a CPU-based probabilistic tractography framework. (b) Execution times (in logarithmic scale) and speedup (and its standard deviation σ) reconstructing 27 tracts. (c) Execution times (in logarithmic scale) and speedup (and std) generating a dense connectome, taking and without taking into account the time spent for merging results from differenc CPU cores (required only in the CPU-based solution).*

<figure>
<img src="{{ site.url }}{{ site.baseurl }}/images/software/probtrackx/tracts.png" width="70%">
</figure>

*Coronal, sagittal and axial views comparing CPU-based and GPU-based frameworks performing probabilistic tractography and reconstructing some major white matter tracts. Each colour represents a different brain white matter tract. These paths are binarised versions of the path distributions after being thresholded at 0.5%.*

<figure>
<img src="{{ site.url }}{{ site.baseurl }}/images/software/probtrackx/connectome.png" width="70%">
</figure>

*Path probability map from a vertex in the Motor Cortex. The map was extracted from dense connectome matrices reconstructed with CPU-based and GPU-based probabilistic tractography applications.*

## Citation

If you use Probtrackx GPU in publications, please cite [this paper](https://www.sciencedirect.com/science/article/pii/S1053811918321591):

Hernandez-Fernandez M., Reguly I., Jbabdi S, Giles M, Smith S., Sotiropoulos S.N. 
*Using GPUs to accelerate computational diffusion MRI: From microstructure estimation to tractography and connectomes.*
**NeuroImage 188 (2019): 598-615**

## Installation

 - Download the correct probtrackx2_gpu file for your CUDA version
 - Unzip ``probtrackx2_gpu`` file
 - Copy the binary file into your ``$FSLDIR/bin`` directory
 - To execute it use: ``$FSLDIR/bin/probtrackx2_gpu``

### FSL 6.x FILES

 - [probtrackx_gpu_cuda_7.5](http://users.fmrib.ox.ac.uk/~moisesf/Probtrackx_GPU/FSL_6/CUDA_7.5/probtrackx2_gpu.zip)
 - [probtrackx_gpu_cuda_8.0](http://users.fmrib.ox.ac.uk/~moisesf/Probtrackx_GPU/FSL_6/CUDA_8.0/probtrackx2_gpu.zip)
 - [probtrackx_gpu_cuda_9.1](http://users.fmrib.ox.ac.uk/~moisesf/Probtrackx_GPU/FSL_6/CUDA_9.1/probtrackx2_gpu.zip)
 - [probtrackx_gpu_cuda_9.2](http://users.fmrib.ox.ac.uk/~moisesf/Probtrackx_GPU/FSL_6/CUDA_9.2/probtrackx2_gpu.zip)
 - [probtrackx_gpu_cuda_10.0](http://users.fmrib.ox.ac.uk/~moisesf/Probtrackx_GPU/FSL_6/CUDA_10.0/probtrackx2_gpu.zip)
 - [probtrackx_gpu_cuda_10.1](http://users.fmrib.ox.ac.uk/~moisesf/Probtrackx_GPU/FSL_6/CUDA_10.1/probtrackx2_gpu.zip)
 - [probtrackx_gpu_cuda_10.2](http://users.fmrib.ox.ac.uk/~moisesf/Probtrackx_GPU/FSL_6/CUDA_10.2/probtrackx2_gpu.zip)

Ampere architecture, and CUDA 11.x binaries will be supported within FSL installer starting from FSL 6.0.6

## Credits

 - Moises Hernandez Fernandez (FMRIB, University of Oxford, UK)
 - Stamatios N Sotiropoulos (FMRIB, University of Oxford, UK)
 - Mike Giles (Oxford e-Research Centre, University of Oxford, UK)
 - István Zoltán Reguly (Pázmány Péter Catholic University, Hungary)
 - Saad Jbabdi (FMRIB, University of Oxford, UK)
 - Stephen Smith (FMRIB, University of Oxford, UK)

## Copyright

Part of [FSL](https://fsl.fmrib.ox.ac.uk/fsl/fslwiki) (FMRIB Software Library)

[License Infomation](https://fsl.fmrib.ox.ac.uk/fsl/fslwiki/Licence)
