# Generalized Motorcycle Graph
[![Build Status](https://travis-ci.org/NSchertler/GeneralizedMotorcycleGraph.svg?branch=master)](https://travis-ci.org/NSchertler/GeneralizedMotorcycleGraph)
[![Build status](https://ci.appveyor.com/api/projects/status/xxeeu3j7ukoh37ro?svg=true)](https://ci.appveyor.com/project/NSchertler/generalizedmotorcyclegraph)

This repository contains the source code for the research paper:
> **Generalized Motorcycle Graphs for Imperfect Quad-Dominant Meshes** <br/>
> Nico Schertler, Daniele Panozzo, Stefan Gumhold, Marco Tarini <br/>
> ACM TOG 37, 4, August 2018 <br/>

## Prerequisites
If you want support for invisible seam parametrization, you need to have [Gurobi](http://www.gurobi.com) installed. The CMake system will try to find the according libraries.

On Linux, the following packages are necessary (available via `apt-get`):
* xorg-dev
* libglu1-mesa-dev
* libboost-dev (only the header files are needed)

## Compilation
To compile the project, simply check out the git repository, initialize all submodules, use CMake to generate project files for your favorite build environment, and run the build.
On Unix-based systems, this may look as follows:

    git clone https://github.com/NSchertler/GeneralizedMotorcycleGraph.git
    cd GeneralizedMotorcycleGraph
    git submodule update --init --recursive
    mkdir build
    cd build
    cmake .. -DNANOGUI_USE_GLAD=ON
    make RegularMeshTexturing
	
Some parts of the code make use of OpenMP.
If your build environment does not support OpenMP (e.g. Clang on MacOS), the program will still compile but performance may be inferior due to missing parallelization.

## Binaries
The following binaries are compiled from the latest commit with default options (no Gurobi support):
* [Windows Binaries](https://github.com/NSchertler/GeneralizedMotorcycleGraph/blob/deploy-windows/gmcg-windows.zip) (Visual Studio 2017)
* [Linux Binaries](https://github.com/NSchertler/GeneralizedMotorcycleGraph/blob/deploy-linux/gmcg-linux.zip) (GCC 6)
* [macOS Binaries](https://github.com/NSchertler/GeneralizedMotorcycleGraph/blob/deploy-osx/gmcg-macos.zip) (Clang, without OpenMP support)


## Data sets
A selection of data sets that we presented in our paper can be found here under `data.zip` in the repository root.

## Documentation
Source code documentation can be found in the source files. For usage instructions, see the [wiki](https://github.com/NSchertler/GeneralizedMotorcycleGraph/wiki).