---
title: "CoNI Lab - Debugging cuDIMOT"
layout: textlay
excerpt: "cuDIMOT"
sitemap: false
permalink: /software/cudimot_debugging
---

# Debugging the functions of a model:

Sometimes, the obtained results are not the expected ones. Bugs in the specified model functions may cause wrong results. cuDIMOT offers some mechanisms for debugging your model functions.

You have three options for debugging.
In ascending order of difficulty:

 - Test Predicted Signal and Partial Derivatives functions
 - Debug toolbox option
 - CUDA printf

## Test Predicted Signal and Partial Derivatives functions

After compiling your model, a binary file called ``testFunctions_$modelname`` is generated in ``$FSLDEVDIR/bin``.

This binary evaluates the model predicted signal and the partial derivatives provided by the user. It needs all the parameters, including the common fixed parameters and the fixed parameters.

<figure>
<img src="{{ site.url }}{{ site.baseurl }}/images/software/cudimot/testfunctions.png" width="70%">
</figure>

<figure>
<img src="{{ site.url }}{{ site.baseurl }}/images/software/cudimot/testfunctions2.png" width="70%">
</figure>

It also returns the numerical partial derivatives (taking small steps for each parameter) for comparison.

## Debug toolbox option

If you need deeper debugging, the first recommendation is to reduce the analysed dataset to few voxels, or just 1 voxel. You can modify the mask of the dataset to include only one voxel.

The default script divides the dataset into 4 parts, but for processing 1 voxel, you want to particionate the data into a single part. You can use ``-NJOBS`` option:

    ./model -NJOBS 1

To make the debugging process faster, we should avoid the preprocessing and postprocessing steps performed by ``split_parts_$modelname`` and ``merge_parts_$modelname``. These processes create intermediate files that are used and deleted at the end. In order to keep these intermediate files we can run our script once using the option ``--keepTmp``.

Now we can execute only the commands for fitting a model. The executed commands are saved in the output file ``${Your_output_Directory}/commands.txt``

If you run one of these commands adding at the end the option ``--debug=Num_voxel``, the toolbox will print out the value of the most important variables at certain steps of the algorithms. For instance:

    {command} --debug=0

You should use few iterations of the algorithms and a small grid when debugging.

## CUDA printf

In addition to the two previous debugging mechanisms, you can print out the value of any variable inside your model functions.

You can use the CUDA function ``printf``. You must be aware that any line in your model functions code is going to be executed by multiple threads. To make the debugging process simpler, you should select just one thread to print out the value of the variables. In order to to this, you can use an if condition to make only the first CUDA thread to print out: ``if (threadIdx.x==0 && blockIdx.x==0)``.

For instance, if you want the first thread to print the variable x inside you model functions:

    if (threadIdx.x==0 && blockIdx.x==0) printf("Value of my variable x is: %f\n",x);
