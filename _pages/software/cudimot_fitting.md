---
title: "CoNI Lab - Fitting your cuDIMOT model"
layout: textlay
excerpt: "cuDIMOT"
sitemap: false
permalink: /software/cudimot_fitting
---

# How to fit a model using cuDIMOT:

Once a model is compiled, binaries files and a main script are generated in ``$FSLDEVDIR/bin``

For calling the main script that fits your model you can use:

    $FSLDEVDIR/bin/cudimot_(MODELNAME).sh   subject_directory   [options]

You can create your own script (using any language) and call the model binaries.

You can concatenate the output of a fitting process with the input of other fitting process using different models.

You can use multi GPUs to fit a dataset.

## Create my own script to fit a model

For fitting a model you need to call three binaries:

 - ``split_parts_$modelname`` - this binary split the dataset into smaller parts.
 - ``$modelname`` - this binary performs the fit.
 - ``merge_parts_$modelname`` - this binary merge the output from the different parts.
 - You can use as reference the main script created by CUDIMOT

## Fitting options of the toolbox

### Compulsory arguments:

 - ``--data``	Data file with measurements
 - ``--maskfile``	Mask file
 - ``--subjdir``	Subject directory
 - ``--partsdir``	Directory where different parts of the data/results will be stored
 - ``--outputdir``	Directory where to write the output file
 - ``--idPart	Number`` of the part of the dataset to process [0..N-1]
 - ``--nParts``	Total number of parts of the dataset [1..N]

### Optional arguments:

 - ``-h``, ``--help``	Display the options of the toolbox
 - ``--ld``, ``--logdir``	Log directory (default is logdir)
 - ``--forcedir``	Use the actual directory name given - i.e. don't add + to make a new directory
 - ``--nj``, ``--njumps``	Num of jumps to be made by MCMC (default is 1250)
 - ``--bi``, ``--burnin``	Total num of jumps at start of MCMC to be discarded (default is 1000)
 - ``--se``, ``--sampleevery``	Num of jumps between each sample (MCMC) (default is 25)
 - ``--upe``, ``--updateproposalevery``	Num of jumps for each update to the proposal density std (MCMC) (default is 40)
 - ``--no_updateproposal``	Do not update the proposal density std during the recording step of MCMC
 - ``--seed``	Seed for pseudo random number generator
 - ``--gridSearch``	Run gridSearch algorithm using the values specified in a file
 - ``--runMCMC``	Run MCMC algorithm and get distribution of estimates
 - ``--no_LevMar``	Do not run Levenberg-Marquardt algorithmRun MCMC algorithm and get distribution of estimates
 - ``--no_Marquardt``	Do not use Marquardt contribution in Levenberg algorithm
 - ``--iterLevMar``	Maximum number of iterations in Levenberg(-Marquardt) algorithm (default is 200)
 - ``--rician``	Use Rician noise modelling in MCMC
 - ``--keepTmp``	Do not remove the temporal directory created for storing the data/results parts
 - ``--getPredictedSignal``	Save the predicted signal by the model at the end
 - ``--CFP``	File with a list of ASCCI files for specifying the common (to all voxels) fixed parameters of the model
 - ``--FixP``	File with a list of NIfTI files for specifying the fixed parameters of the model
 - ``--fixed``	List of the Ids of the fixed parameters separated by commas. For example: --fixed=2,4
 - ``--init_params``	File with a list of NIfTI files for the initialization of the model parameters
 - ``--debug``	Specify a voxel for debugging. Some variables at certain steps of the algorithms will be printed (use few iterations)
 - ``--BIC_AIC``	Calculate Bayesian and Akaike Information Criteria at the end

## Concatenating models

The toolbox offers the possibility of initialising the model parameters with some given values. You can use values estimated in other models.

The user can provide a NIfTI volume for each parameter of the model. The volumes must have the same dimensions as the input dataset.

The path to the NIfTI volumes needs to be specified in a text file passed as argument using the option ``--init_params``.

The text file must contain a line for each model parameter, but a line can be empty if that parameter does not need to be initialised.

For instance, for initialising the first and third parameter of model-2 with the first and second parameters estimated in model-1:

    model2 --init_params=File.txt

and File.txt containing a line for each model-2 parameter:

<figure>
<img src="{{ site.url }}{{ site.baseurl }}/images/software/cudimot/initialization.png" width="50%">
</figure>

## Specifying Fixed Parameters

Common Fixed Parameters, such as bvals and bvecs, and Fixed Parameters, such as T1 or S0, are specified with a list of paths to the files containing the values of these parameters.

Common Fixed Parameters files must be ASCII files and Fixed Parameters must be NIfTI volumes with the same size in the first three dimensions as the input dataset.

The paths to the ASCII Common Fixed Parameters files must be specified in a text file passed as argument using the option ``--CFP``.

The paths to the NIfTI Fixed Parameters files must be specified in a text file passed as argument using the option ``--FixP``.

The text files must contain a line for each Common Fixed Parameter or each Fixed Parameter.

For instance, in a model with bvals and bvecs as Common Fixed Parameters and S0 as Fixed Parameter:

    model --CFP=CommonFixed_params.txt --FixP=Fixed_params.txt

CommonFixed_params.txt containing:

<figure>
<img src="{{ site.url }}{{ site.baseurl }}/images/software/cudimot/cfp.png" width="50%">
</figure>

And Fixed_params.txt containing:

<figure>
<img src="{{ site.url }}{{ site.baseurl }}/images/software/cudimot/fixp.png" width="50%">
</figure>


## Fixing Parameters on the fly

It is possible to indicate that some of the estimated parameters of the model do not change during the fitting.

To do that, you can use the option ``--fixed``.

## Specifying the grid for Grid Search

If Grid Search is used, the combination of values for defining the grid must be specified in a file using the option ``--gridSearch`` and using the format:

    search[Num_parameter]: [Value0, ..., ValueN]

For instance, if we want to define the grid with different values for the first three parameters of a model:

    model --gridSearch=Grid.txt

and Grid.txt containing:

<figure>
<img src="{{ site.url }}{{ site.baseurl }}/images/software/cudimot/gridsearch.png" width="50%">
</figure>

The toolbox will try all the combinations of these parameter values.
