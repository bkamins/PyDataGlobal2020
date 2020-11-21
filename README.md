# PyData Global 2020 DataFrames.jl Tutorial

# An introduction to DataFrames.jl for pandas users

## Introduction

This tutorial is prepared for
[PyData Global 2020](https://global.pydata.org/talks/an-introduction-to-dataframesjl-for-pandas-users).

You are viewing the version of the tutorial updated to DataFrames.jl 0.22
release that was made after PyData Global 2020 (the tutorial is identical, only
dependency versions have been changed).

I present the fundamental design concepts behind
[DataFrames.jl](https://github.com/JuliaData/DataFrames.jl) to help potential
users get started with using it. I show how an exemplary
[pandas](https://pandas.pydata.org/) data processing pipeline can be transferred
to [DataFrames.jl](https://github.com/JuliaData/DataFrames.jl). Finally I
discuss how [DataFrames.jl](https://github.com/JuliaData/DataFrames.jl)
integrates with the whole data science ecosystem available in the Julia
language.

I based the tutorial on an excellent
[PyCon 2018: Using pandas for Better (and Worse) Data Science](https://nbviewer.jupyter.org/github/justmarkham/pycon-2018-tutorial/blob/master/tutorial.ipynb)
presentation that was prepared by [Kevin Markham](https://github.com/justmarkham).

In the tutorial I have selected exemplary [pandas](https://pandas.pydata.org/)
commands from that presentation and show how they can be expressed in
[DataFrames.jl](https://github.com/JuliaData/DataFrames.jl).

The data I use is exactly the same as the original tutorial and it is contained
in *police.csv* file contained in this GitHub repository.

*police.csv* is the Rhode Island dataset from the
[Stanford Open Policing Project](https://openpolicing.stanford.edu/),
made available under the
[Open Data Commons Attribution License](https://opendatacommons.org/licenses/by/summary/).

I use [Jupyter Notebook](https://jupyter.org/) to run the code as it should be
familiar to Python users. However, Julia offers you also reactive notebooks
(with automatic cell updating and featuring widgets). If you want to learn more
about it check out [Pluto.jl](https://github.com/fonsp/Pluto.jl).

## Preparing for running the tutorial

All the examples are prepared under Julia 1.5.3. If you use any other version of
Julia 1.x the examples should just work (if they do not please let me know via
an Issue; you might need to adjust the Jupyter Notebook kernel).

Before we begin please make sure that you have Julia and git installed and that
respectively `julia` and `git` commands work in your terminal. You can download
Julia at [here](https://julialang.org/downloads/).

## Ready, set, go!

Actually the tutorial starts before we even go to the Jupyter Notebook.
The first step we need to do is to make sure that your Julia environment is
set up with proper versions of required packages.

Fortunately Julia has in-built package manager that allows you to smoothly
ensure this, provided that you have *Project.toml* and *Manifest.toml* files
that contain all the required information (you can notice that they are
present in the GitHub repository; you can learn more what these files contain
[here](https://docs.julialang.org/en/v1/stdlib/Pkg/)).

The simplest way to set up your project is to perform the following steps
(I assume you have `git` and `julia` commands available):

1. Open a terminal in a directory where you want to have the tutorial stored.
2. Run `git clone https://github.com/bkamins/PyDataGlobal2020.git`
   to download the repository with the turorial (if you to not have `git`
   installed then you can download a zip of this repository from GitHub and
   unpack it locally).
3. Run `cd PyDataGlobal2020` to switch a directory to the one where the tutorial
   has been downloaded.
4. Run `julia --project=. -e "using Pkg; Pkg.instantiate()"`
   to make sure you have all the required packages automatically downloaded and
   precompiled (this step is optional and should be run only once to make sure
   that all the packages are correctly set up before we start working with them;
   you can expect that downloading all the dependencies will take some time)
5. Run `julia --project=. -e "using IJulia; notebook(dir=pwd())"` to start the
   Jupyter Notebook in the directory where the tutorial is stored (note that
   in the terminal you do not see a prompt as the Julia process is running
   now).
6. Now you can work with the tutorial (here the actual fun happens).
7. After you are done please make sure to choose "Quit" option in the top right
   hand side in the Jupyter Notebook. This will automatically terminate the
   Julia process in the terminal and prompt will reappear.
