# Computational CryoET Methods 
[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

This repository is a curated list for computational cryo-ET methods!

You will find the paper and associated software for the popular algorithms used in the cryo-ET field.

The format for the item is [software link] - [Paper link] (Available in which package) and the headings may contain a ink to a review paper.



- [**Computational CryoET Methods**](#computational-cryoET-methods)
- [**Resources**](#resources)
- [**Workflow**](#workflow)
    - [Motion correction](#motion-correction)
    - [CTF estimation](#ctf-estimation)
    - [Particle picking](#particle-picking)
    - [2D classification](#2D-classification)
    - [Ab-initial Model](#ab-initial-model)
    - [3D refinement](#3d-refinement)
    - [3D variability analysis](#3D-variability-analysis)
    - [Postprocessing](#postprocessing)
- [**Conventions**](#conventions)
- [**Tips**](#tips)
    - [Format Conversion](#format-conversion)
    - [Performing Focus Classification](#performing-focus-classification)
    - [Display images](#display-images)
    - [Using Chimera](#using-chimera)
- [**Contributing**](#contributing)

---


# Resources
## Preface
* [Protein Folding Problem](https://www.youtube.com/watch?v=KpedmJdrTpY&t=2s&ab_channel=DeepMind) - Great video that describes the importance of understanding protein structure.
* [What is cryoET](https://cryoem101.org/chapter-1-et/) - Great article that describes the cryoET.

## Introduction
* [The promise and the challenges of cryo-electron tomography](https://febs.onlinelibrary.wiley.com/doi/full/10.1002/1873-3468.13948) - A great review to start with.
* [Toward high-resolution in situ structural biology with cryo-electron tomography and subtomogram averaging](https://www.sciencedirect.com/science/article/pii/S0959440X18301738?via%3Dihub)
* [Current data processing strategies for cryo-electron tomography and subtomogram averaging](https://portlandpress.com/biochemj/article/478/10/1827/228677/Current-data-processing-strategies-for-cryo)
* [Quantitative Cryo-Electron Tomography](https://www.frontiersin.org/articles/10.3389/fmolb.2022.934465/full)

## Resources
* [3DEM Methods](http://3demmethods.i2pc.es/index.php/Main_Page) - A great wiki that collects papers or books for computational methods.
* [A collective resource](https://teamtomo.org/index.html) - A great repository that covers tomography.
* [Math behind CryoEM](https://github.com/geoffwoollard/learn_cryoem_math) - A great repository that collects the materials which elaborate the math behind single-particle analysis and CryoET.


## Events and News
* [3DEM Events](http://www.emdatabank.org/3dem_events.html)
* [NRAMM Events](http://nramm.nysbc.org/workshops-and-courses/?lcp_page0=1#lcp_instance_0)

## [Software](http://3dem.ucsd.edu/software.shtm)
* [Scipion](http://scipion.i2pc.es/) - An integrated platform that allows users to use a variety of methods in the same framework. [[Documentation](https://scipion-em.github.io/docs/)]
* [Relion](https://www3.mrc-lmb.cam.ac.uk/relion/index.php?title=Main_Page) - A comprehensive package. [[Documentation](https://relion.readthedocs.io/en/release-4.0/STA_tutorial/index.html#)]
* [emClarity](https://github.com/StochasticAnalytics/emClarity) - [[Documentation](https://github.com/ffyr2w/emClarity-tutorial)]
* [IMDO](https://bio3d.colorado.edu/imod/)
* [EMAN2](https://blake.bcm.edu/emanwiki/EMAN2/e2tomo)
* [Warp](http://www.warpem.com/warp/)
* [Dynamo](https://wiki.dynamo.biozentrum.unibas.ch/w/index.php/Main_Page)
* [AITom](https://github.com/xulabs/aitom)
* [PyTom](https://github.com/FridoF/PyTom)




# Workflow
## Import Data
1. From [EMPIAR](https://www.ebi.ac.uk/pdbe/emdb/empiar/) or [EMDB](https://www.ebi.ac.uk/pdbe/emdb/index.html/).

2. From tutorial data set.
* https://scipion-em.github.io/docs/release-3.0.0/docs/user/user-documentation.html#tomography-tutorials

3. Generate simulation data
    * https://github.com/xulabs/aitom/blob/master/doc/tutorials/004_simulate_whole_tomogram.py
    * https://github.com/xulabs/aitom/blob/master/doc/tutorials/003_simulate_subtomogram.py

## Image Formation model
1. [`TEM Simulator`](http://tem-simulator.sourceforge.net/) - [**Simulation of transmission electron microscope images of biological specimens**](https://onlinelibrary.wiley.com/doi/10.1111/j.1365-2818.2011.03497.x)

2. [`InSilicoTEM`](https://github.com/M4I-nanoscopy/InSilicoTEM/tree/v2.0.0) - [**Image formation modeling in cryo-electron microscopy**](https://www.sciencedirect.com/science/article/abs/pii/S1047847713001226)

3. [`CisTEM_Simulate`](https://github.com/timothygrant80/cisTEM/blob/master/src/programs/simulate/simulate.cpp) - [**Cryo-TEM simulations of amorphous radiation-sensitive samples using multislice wave propagation**](https://www.biorxiv.org/content/10.1101/2021.02.19.431636v2)

## Motion correction

## Tilt-series alignment

## CTF estimation

## CTF correction

## Tomogram reconstruction

### Denoising tomogram

## Particle picking

## Sub-tomogram alignment and averaging

## Classification

## Post-processing

## Visualization
1. [`Chimera`](https://www.cgl.ucsf.edu/chimera/) - [**UCSF Chimera--a Visualization System for Exploratory Research and Analysis**](https://pubmed.ncbi.nlm.nih.gov/15264254/)
2. [`ChimeraX`](http://www.rbvi.ucsf.edu/chimerax/) - [**UCSF ChimeraX: Meeting modern challenges in visualization and analysis**](https://onlinelibrary.wiley.com/doi/full/10.1002/pro.3235)

# Conventions
## 3DEM Convention
* [3DEM Conventions](https://github.com/azazellochg/3DEM-conventions)

## Display images
### Micrographs
In Matlab use `grayImage = uint8(255 * mat2gray(originalImage)); imshow(grayImage);`

## Using Chimera
### Create synthetic map from PDB
1. Open chimera and import that protein: File -> Fetch By ID… -> Select PDB and type the PDB ID of the protein -> Fetch. Now you will see the 3D structure of the protein.
2. Create synthetic map from PDB model: Modify the density of the protein: Tools -> General Controls -> Command Line -> Type: molmap #0 5 (molmap = is command that generates a density map from the specified atom; # is atom specification, i.e. number assigned to the model by default; 5 = resolution).
3. Store reference map as MRC: Save to a file: Tools -> Volume Data -> Volume Viewer -> File -> Save map as… -> Give it the protein_PDB_ID.mrc.

### [Dispaly local resolution](https://discuss.cryosparc.com/t/view-coloured-3d-map-in-chimera-using-output-from-local-resolution/1003)
### [Flip handedness of model and map](https://github.com/asarnow/pyem/wiki/Z-Flip-for-Models-and-Maps)
### Slice view
`volume #0 planes z,220 step 1 level -1 style surface`
### [Visualizing dynamic movies](https://guide.cryosparc.com/processing-data/tutorials-and-case-studies/tutorial-3d-variability-analysis-part-one#visualization)
#### [Using Script](https://github.com/zhonge/cryodrgn/discussions/79) 

