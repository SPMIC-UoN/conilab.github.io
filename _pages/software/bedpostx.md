---
title: "CoNI Lab - Bedpostx"
layout: textlay
excerpt: "Bedpostx"
sitemap: false
permalink: /software/bedpostx
---

# BedpostX

Tool for estimating multiple fibre orientations from diffussion MRI on NVIDIA GPUs

Part of [FSL](https://fsl.fmrib.ox.ac.uk/fsl/fslwiki) (FMRIB Software Library)

For information about the functionality of the tool, see the [BEDPOSTX User Guide](https://fsl.fmrib.ox.ac.uk/fsl/fslwiki/FDT/UserGuide#BEDPOSTX)

This page provides binary downloads of the GPU version of Bedpostx. 

## Installation

 - Download the correct bedpostx_gpu file for your CUDA version
 - Unzip ``bedpostx_gpu`` file
 - Copy all the files from ``bin`` directory into your ``$FSLDIR/bin`` directory
 - Copy all the files from ``lib`` directory into your ``$FSLDIR/lib`` directory
 - To execute it use: ``$FSLDIR/bin/bedpostx_gpu``

### FSL 6.x FILES

 - [bedpostx_gpu_cuda_7.5](https://github.com/SPMIC-UoN/fdt/releases/download/2103.0/bedpostx_gpu_cuda7_5.zip)
 - [bedpostx_gpu_cuda_8.0](https://github.com/SPMIC-UoN/fdt/releases/download/2103.0/bedpostx_gpu_cuda8_0.zip)
 - [bedpostx_gpu_cuda_9.0]https://github.com/SPMIC-UoN/fdt/releases/download/2103.0/bedpostx_gpu_cuda9_0.zip)
 - [bedpostx_gpu_cuda_9.1](https://github.com/SPMIC-UoN/fdt/releases/download/2103.0/bedpostx_gpu_cuda9_1.zip)
 - [bedpostx_gpu_cuda_9.2](https://github.com/SPMIC-UoN/fdt/releases/download/2103.0/bedpostx_gpu_cuda9_2.zip)
 - [bedpostx_gpu_cuda_10.0](https://github.com/SPMIC-UoN/fdt/releases/download/2103.0/bedpostx_gpu_cuda10_0.zip)
 - [bedpostx_gpu_cuda_10.1](https://github.com/SPMIC-UoN/fdt/releases/download/2103.0/bedpostx_gpu_cuda10_1.zip)
 - [bedpostx_gpu_cuda_10.2](https://github.com/SPMIC-UoN/fdt/releases/download/2103.0/bedpostx_gpu_cuda10_2.zip)
 - [bedpostx_gpu_cuda_11.0 (supports Ampere)](https://github.com/SPMIC-UoN/fdt/releases/download/2103.0/bedpostx_gpu_cuda11_0.zip)
 - [bedpostx_gpu_cuda_11.2 (supports Ampere)](https://github.com/SPMIC-UoN/fdt/releases/download/2103.0/bedpostx_gpu_cuda11_2.zip)

CUDA 11.3 or later version binaries will be supported within FSL installer starting from FSL 6.0.6

## Speedup

GPU BedpostX offers accelerations of *more than 200 times using a single GPU compared to 
a single CPU core: 1 GPU ≈ 200 CPU cores.*

<figure>
<img src="{{ site.url }}{{ site.baseurl }}/images/software/bedpostx_times.png" width="70%">
</figure>

*Execution times in logarithmic scale of a single CPU core and a single GPU (NVIDIA K80) fitting ball & sticks model in a whole dataset. The application fits the model in a low resolution dataset with 106,910 voxels and in a high resolution dataset with 684,203 voxels. Different number of diffusion measurements (36/72/108/145/181/218/254/291) and number of fibres (1/2/3 with 6/9/12 parameters) are showed.*

|Measurements	      | 36	 | 72	  | 108	  | 145	  | 181	  | 218	  | 254	  | 291
|-------------------|------|------|-------|-------|-------|-------|-------|-------
|Low-res 1 fibre	  | 96×	 | 145×	| 167×	| 175×	| 183×	| 195×	| 202×	| 196×
|Low-res 2 fibres	  | 98×	 | 149×	| 174×	| 180×	| 193×	| 206×	| 217×	| 207×
|Low-res 3 fibres	  | 92×	 | 144×	| 172×	| 195×	| 210×	| 225×	| 235×	| 220×
|High-res 1 fibre	  | 99×	 | 148×	| 171×	| 180×	| 214×	| 225×	| 233×	| 227×
|High-res 2 fibres	| 109× | 168×	| 196×	| 203×	| 215×	| 232×	| 238×	| 230×
|High-res 3 fibres	| 96×	 | 163×	| 194×	| 201×	| 209×	| 223×	| 236×	| 221×

## Citation

If you use Bedpostx GPU in publications, please cite [this paper](http://journals.plos.org/plosone/article?id=10.1371/journal.pone.0061892):

Hernández M, Guerrero GD, Cecilia JM, García JM, Inuggi A, Jbabdi S, Behrens TE, Sotiropoulos SN. 
*Accelerating fibre orientation estimation from diffusion weighted magnetic resonance imaging using GPUs.*
**PLoS One. 2013 Apr 29;8(4):e61892**

## Credits

 - Moises Hernandez Fernandez (FMRIB, University of Oxford, UK)
 - Stamatios N Sotiropoulos (FMRIB, University of Oxford, UK)
 - Gines D. Guerrero (University of Murcia, Spain)
 - José M. Cecilia (University of Murcia, Spain)
 - José M. García (University of Murcia, Spain)
 - Timothy E. J. Behrens (FMRIB, University of Oxford, UK)
 - Saad Jbabdi (FMRIB, University of Oxford, UK)
 - Alberto Inuggi (Basque Center on Cognition, Brain and Language, Spain)

## Copyright

Part of [FSL](https://fsl.fmrib.ox.ac.uk/fsl/fslwiki) (FMRIB Software Library)

[License Infomation](https://fsl.fmrib.ox.ac.uk/fsl/fslwiki/Licence)
