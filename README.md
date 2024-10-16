# Computational CryoET Methods 
[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

<div align="center">
    <img src="https://github.com/phonchi/Computational-CryoET/assets/11373055/ba4ce0de-edf7-4d69-8ff9-b59cd0635b06" width="300">
</div>

This repository is a curated list of computational cryo-ET methods!

You will find the paper and associated software for the popular algorithms used in the cryo-ET field.

The format for the item is [software link] - [Paper link] (Available in which package) and the headings may contain a link to a review paper.



- [**Computational CryoET Methods**](#computational-cryoET-methods)
- [**Resources**](#resources)
- [**Workflow**](#workflow)
    - [Motion correction](#motion-correction)
    - [Tilt-series alignment](#tilt-series-alignment)
    - [CTF estimation and correction](#ctf-estimation-and-correction)
    - [Tomogram reconstruction](#tomogram-reconstruction)
    - [Particle picking](#particle-picking)
    - [Sub-tomogram alignment and averaging](#sub-tomogram-alignment-and-averaging)
    - [Classification](#classification)
    - [Postprocessing](#postprocessing)
- [**Conventions**](#conventions)


---


# Resources
## Preface
* [Protein Folding Problem](https://www.youtube.com/watch?v=KpedmJdrTpY&t=2s&ab_channel=DeepMind) - Great video describes the importance of understanding protein structure.
* [What is cryoET](https://cryoem101.org/chapter-1-et/) - Great article that describes the cryoET.

## Introduction
* [Cryo-ET 101](https://cryoem101.org/) - Deomnstrate the principles of cryo-ET using a media-rich approach with videos, animations, interactive simulation.
* [Computational methods for in situ structural studies with cryogenic electron tomography](https://www.frontiersin.org/articles/10.3389/fcimb.2023.1135013/full) - A review focus on computational methods.
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
* [Relion](https://www.biorxiv.org/content/10.1101/2024.04.26.591129v1.abstract) - A comprehensive package. [[Documentation](https://relion.readthedocs.io/en/latest/STA_tutorial/index.html#)]
* [nextPYP](https://www.nature.com/articles/s41592-023-02045-0) - [[Documentation](https://nextpyp.app/files/pyp/latest/docs/index.html)]
* [emClarity](https://github.com/StochasticAnalytics/emClarity) - [[Documentation](https://github.com/ffyr2w/emClarity-tutorial)]
* [IMDO](https://bio3d.colorado.edu/imod/)
* [EMAN2](https://blake.bcm.edu/emanwiki/EMAN2/e2tomo)
* [Warp](http://www.warpem.com/warp/)
* [Dynamo](https://wiki.dynamo.biozentrum.unibas.ch/w/index.php/Main_Page)
* [AITom](https://github.com/xulabs/aitom)
* [PyTom](https://github.com/FridoF/PyTom)
* [TomoBEAR](https://github.com/KudryashevLab/TomoBEAR)
* [STOPGAP](https://journals.iucr.org/d/issues/2024/05/00/vo5015/) - See [[Documentation](https://github.com/wan-lab-vanderbilt/STOPGAP)]

# Workflow
## Import Data
1. From [EMPIAR](https://www.ebi.ac.uk/pdbe/emdb/empiar/) or [EMDB](https://www.ebi.ac.uk/pdbe/emdb/index.html/).

2. From tutorial data set.
* https://scipion-em.github.io/docs/release-3.0.0/docs/user/user-documentation.html#tomography-tutorials

3. Generate simulation data
    * [`cryoSRPNT`](https://github.com/bpowell122/cryoSRPNT/tree/master)
    * [`PolNet`](https://github.com/anmartinezs/polnet) - [**Simulating the cellular context in synthetic datasets for cryo-electron tomography**](https://github.com/anmartinezs/polnet)
    * [`faket`](https://gitlab.com/deepet/faket) - [**Simulating the cellular context in synthetic datasets for cryo-electron tomography**](https://arxiv.org/abs/2304.02011)
    * https://github.com/MPI-Dortmund/tem-simulator-scripts
    * [`MEPSi`](https://github.com/pyCoAn/distro) - [**MEPSi: A tool for simulating tomograms of membrane-embedded proteins**](https://www.sciencedirect.com/science/article/pii/S1047847722000910#da005)
    * https://github.com/xulabs/aitom/blob/master/doc/tutorials/004_simulate_whole_tomogram.py
    * https://github.com/xulabs/aitom/blob/master/doc/tutorials/003_simulate_subtomogram.py
    * https://github.com/anmartinezs/pyseg_system/blob/master/code/pyorg/scripts/synthetic/gen_microsomes.py
    * https://www.shrec.net/cryo-et/
    * [`parakeet`](https://github.com/rosalindfranklininstitute/parakeet) - [**Parakeet: A digital twin software pipeline to assess the impact of experimental parameters on tomographic reconstructions for cryo-electron tomography**](https://royalsocietypublishing.org/doi/10.1098/rsob.210160)

## Image Formation model
1. [`TEM Simulator`](http://tem-simulator.sourceforge.net/) - [**Simulation of transmission electron microscope images of biological specimens**](https://onlinelibrary.wiley.com/doi/10.1111/j.1365-2818.2011.03497.x)

2. [`InSilicoTEM`](https://github.com/M4I-nanoscopy/InSilicoTEM/tree/v2.0.0) - [**Image formation modeling in cryo-electron microscopy**](https://www.sciencedirect.com/science/article/abs/pii/S1047847713001226)

3. [`CisTEM_Simulate`](https://github.com/timothygrant80/cisTEM/blob/master/src/programs/simulate/simulate.cpp) - [**Cryo-TEM simulations of amorphous radiation-sensitive samples using multislice wave propagation**](https://www.biorxiv.org/content/10.1101/2021.02.19.431636v2)

## Motion correction
1. [`MotionCorr2`](https://emcore.ucsf.edu/ucsf-motioncor2) - [**MotionCor2: anisotropic correction of beam-induced motion for improved cryo-electron microscopy**](https://www.nature.com/articles/nmeth.4193?proof=t) (Use in `Relion`)
1. [`Unblur`](https://grigoriefflab.umassmed.edu/unblur_summovie) - [**Measuring the optimal exposure for single particle cryo-EM using a 2.6 Å reconstruction of rotavirus VP6**](https://elifesciences.org/articles/06980)
1. [`Alignparts`](https://sites.google.com/site/rubinsteingroup/direct-detector-align_lmbfgs) - [**Alignment of cryo-EM Movies of Individual Particles by Optimization of Image Translations**](https://pubmed.ncbi.nlm.nih.gov/26296328/) 
1. `FlexAlign` - [**FlexAlign: An Accurate and Fast Algorithm for Movie Alignment in Cryo-Electron Microscopy**](https://www.mdpi.com/2079-9292/9/6/1040/htm) - (Use in `Scipion`)

## Tilt-series alignment
### [Fiducial based](https://link.springer.com/chapter/10.1007/978-0-387-69008-7_6)
1. [`IMOD`](https://bio3d.colorado.edu/imod/) - [**Automated tilt series alignment and tomographic reconstruction in IMOD**](https://www.sciencedirect.com/science/article/pii/S1047847716301526) (Use in `IMOD`)
2. [`Dynamo`](https://www.dynamo-em.org/w/index.php?title=Downloads) - [**Automated ﬁducial-based alignment of cryo-electron tomography tilt series in Dynamo**](https://www.sciencedirect.com/science/article/pii/S0969212624002417) (Use in `Dynamo`)

### Fiducialless
1. [`AreTomo`](https://drive.google.com/drive/folders/1Z7pKVEdgMoNaUmd_cOFhlt-QCcfcwF3_) - [**AreTomo: An integrated software package for automated marker-free, motion-corrected cryo-electron tomographic alignment and reconstruction**](https://www.sciencedirect.com/science/article/pii/S2590152422000095)
1. [`TomoAlign`](https://sites.google.com/site/3demimageprocessing/tomoalign) - [**Cryo-tomography tilt-series alignment with consideration of the beam-induced sample motion**](https://www.sciencedirect.com/science/article/pii/S1047847718300285)
1. [`Xmipp`](https://github.com/I2PC/xmipp) - [**A deep learning approach to the automatic detection of alignment errors in cryo-electron tomographic reconstructions**](https://www.sciencedirect.com/science/article/pii/S1047847723001193) (Use in `Xmipp`)

### Detect fiducial marker
1. [`MarkerDetector`](https://github.com/HaleyBG/MarkerDetector) - [**MarkerDetector: A method for robust fiducial marker detection in electron micrographs using wavelet-based template**](https://www.sciencedirect.com/science/article/pii/S1047847723001077) (Use in `IMOD`)

## CTF estimation and correction
1. [`CTFFIND4`](https://grigoriefflab.umassmed.edu/ctffind4) - [**CTFFIND4: Fast and accurate defocus estimation from electron micrographs**](https://www.sciencedirect.com/science/article/pii/S1047847715300460) ( Use in [`CisTEM`](http://grigoriefflab.janelia.org/ctffind4))
1. [`gCTF`](https://www2.mrc-lmb.cam.ac.uk/research/locally-developed-software/zhang-software/#gctf) - [**Gctf: Real-time CTF determination and correction**](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4711343/)
1. [`ctfplotter`](https://bio3d.colorado.edu/imod/doc/ctfHelp/ctfguide.html#top)- [**CTF determination and correction for low dose tomographic tilt series**](https://www.sciencedirect.com/science/article/pii/S1047847709002433) (Use in IMOD)
1. [`novaCTF`](https://github.com/turonova/novaCTF) - [**Efficient 3D-CTF correction for cryo-electron tomography using NovaCTF improves subtomogram averaging resolution to 3.4 Å**](https://www.sciencedirect.com/science/article/pii/S1047847717301272?via%3Dihub)
1. [`Warp`](http://www.warpem.com/warp/?page_id=378) 
1. [`M`](http://www.warpem.com/warp/?page_id=827) - [**Multi-particle cryo-EM refinement with M visualizes ribosome-antibiotic complex at 3.5 Å inside cells**](https://www.nature.com/articles/s41592-020-01054-7). [[Video]](https://www.youtube.com/watch?v=kiS-ELvQ1gc&list=PLFEB3YHuxu11Jp_pOCIEtXxSqozFHve0O&index=18)
2. [`Ctfplotter`](https://bio3d.colorado.edu/ftp/standaloneCtfplotter/) - [**Accurate, automatic determination of astigmatism and phase with Ctfplotter in IMOD**](https://www.sciencedirect.com/science/article/pii/S104784772300120X) (Use in `IMOD`)

## Tomogram reconstruction
1. [**A Survey of the Use of Iterative Reconstruction Algorithms in Electron Microscopy**](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5623807/)
1. [`Tomo3D`](https://sites.google.com/site/3demimageprocessing/tomo3d) -[**Tomo3D 2.0 – Exploitation of Advanced Vector eXtensions (AVX) for 3D reconstruction**](https://www.sciencedirect.com/science/article/pii/S1047847714002603)

### [Denoising tomogram](https://www.sciencedirect.com/science/article/pii/S104784772100109X)
1. [`SC-Net`](https://github.com/icthrm/SC-Net) - [**Self-Supervised Cryo-Electron Tomography Volumetric Image Restoration from Single Noisy Volume with Sparsity Constraint**](https://openaccess.thecvf.com/content/ICCV2021/papers/Yang_Self-Supervised_Cryo-Electron_Tomography_Volumetric_Image_Restoration_From_Single_Noisy_Volume_ICCV_2021_paper.pdf)
1. [`CryoCARE`](https://github.com/juglab/cryoCARE_T2T) - [**Content-aware image restoration for electron microscopy**](https://www.sciencedirect.com/science/article/abs/pii/S0091679X19300706?via%3Dihub)
1. [`Topaz`](https://github.com/tbepler/topaz) - [**Topaz-Denoise: general deep denoising models for cryoEM**](https://www.nature.com/articles/s41467-020-18952-1)
1. [`TomoEED`](https://sites.google.com/site/3demimageprocessing/tomoeed) - [**TomoEED: fast edge-enhancing denoising of tomographic volumes**](https://pubmed.ncbi.nlm.nih.gov/29850773/)
1. `DUAL` - [**DUAL: deep unsupervised simultaneous simulation and denoising for cryo-electron tomography**](https://www.biorxiv.org/content/10.1101/2024.03.02.583135v1)  (Use in `AITom`)
2. [`REST`](https://github.com/Zhang-hn1125/REST) - [**A method for restoring signals and revealing individual macromolecule states in cryo-ET, REST**](https://www.nature.com/articles/s41467-023-38539-w)
3. [`CCPEM Denoiser`](https://gitlab.com/ccpem/ccpem-denoiser)

## [Particle picking](https://www.sciencedirect.com/science/article/pii/S0022283623001274)
1. [`DeePiCt `](https://github.com/ZauggGroup/DeePiCt) - [**Convolutional networks for supervised mining of molecular patterns within cellular context**](https://www.nature.com/articles/s41592-022-01746-2)
1. [`DeepFinder`](https://github.com/deep-finder/deep-finder) - [**Deep learning improves macromolecule identification in 3D cellular cryo-electron tomograms**](https://www.nature.com/articles/s41592-021-01275-4)
1. [`Cryolo`](https://cryolo.readthedocs.io/en/stable/) - [**SPHIRE-crYOLO is a fast and accurate fully automated particle picker for cryo-EM**](https://www.nature.com/articles/s42003-019-0437-z). [[Video](https://www.youtube.com/watch?v=JTgldM4wAAk&list=UUbo1TnKiXGtkE_R5b526JmQ&index=6&t=1s&app=desktop)]
1. [`PySeg`](https://github.com/anmartinezs/pyseg_system) - [**Template-free detection and classification of membrane-bound complexes in cryo-electron tomograms**](https://www.nature.com/articles/s41592-019-0675-5)
1. [`TomoTwin`](https://github.com/MPI-Dortmund/tomotwin-cryoet) - [**TomoTwin: generalized 3D localization of macromolecules in cryo-electron tomograms with structural data mining**](https://www.nature.com/articles/s41592-023-01878-z)
1. [`pytom-match-pick`](https://github.com/SBC-Utrecht/pytom-match-pick) - [**Extensive Angular Sampling Enables the Sensitive Localization of Macromolecules in Electron Tomograms**](https://www.mdpi.com/1422-0067/24/17/13375) (Use in `PyTom`)
1. [`TARDIS`](https://github.com/SMLC-NYSBC/TARDIS) - [**Automated Segmentation of 3D Cytoskeletal Filaments from Electron Micrographs with TARDIS**](https://academic.oup.com/mam/article/29/Supplement_1/970/7228849?login=true)
2. [`TomoTwin`](https://github.com/MPI-Dortmund/tomotwin-cryoet) - [**TomoTwin: generalized 3D localization of macromolecules in cryo-electron tomograms with structural data mining**](https://www.nature.com/articles/s41592-023-01878-z)
3. [`TomoNet`](https://github.com/logicvay2010/TomoNet) - [**TomoNet: A streamlined cryogenic electron tomography software pipeline with automatic particle picking on flexible lattices**](https://www.cambridge.org/core/journals/biological-imaging/article/tomonet-a-streamlined-cryogenic-electron-tomography-software-pipeline-with-automatic-particle-picking-on-flexible-lattices/2634515FCC5CE369021280CB988D3324)
4. [`cet_pick_size`](https://gitlab.cs.duke.edu/bartesaghilab/cet_pick_size) - [**Accurate size-based protein localization from cryo-ET tomograms**](https://www.sciencedirect.com/science/article/pii/S2590152424000096) (Use in `nextPYP`)
5. [`PyTME`](https://github.com/ElsevierSoftwareX/SOFTX-D-23-00732) - [**PyTME (Python Template Matching Engine): A fast, flexible, and multi-purpose template matching library for cryogenic electron microscopy data**](https://www.sciencedirect.com/science/article/pii/S2352711024000074)

## Sub-tomogram alignment and averaging
1. [`emClarity`](https://github.com/StochasticAnalytics/emClarity) - [**emClarity: software for high-resolution cryo-electron tomography and subtomogram averaging**](https://www.nature.com/articles/s41592-018-0167-z)
1. [`Dynamo`](https://wiki.dynamo.biozentrum.unibas.ch/w/index.php/Main_Page) - [**Dynamo: A flexible, user-friendly development tool for subtomogram averaging of cryo-EM data in high-performance computing environments**](https://www.sciencedirect.com/science/article/pii/S1047847711003650)
1. [`IsoNet`](https://github.com/IsoNet-cryoET/IsoNet) - [**Isotropic reconstruction for electron tomography with deep learning**](https://www.nature.com/articles/s41467-022-33957-8)

## [Classification](https://www.sciencedirect.com/science/article/pii/S0169260722003996)
1. [`AITom`](https://github.com/xulabs/aitom/blob/master/doc/publications.md) - [**High-throughput cryo-ET structural pattern mining by unsupervised deep iterative subtomogram clustering**](https://www.pnas.org/doi/10.1073/pnas.2213149120)
2. [`TomoDRGN`](https://github.com/bpowell122/tomodrgn) - [**Learning structural heterogeneity from cryo-electron sub-tomograms with tomoDRGN**](https://www.biorxiv.org/content/10.1101/2023.05.31.542975v1)
3. [`CryoDRGN-ET`](https://github.com/ml-struct-bio/cryodrgn) - [**Deep reconstructing generative networks for visualizing dynamic biomolecules inside cells**](https://www.biorxiv.org/content/10.1101/2023.08.18.553799v1)

## Post-processing
### Local resolution
1. Monotomo - [**Measurement of local resolution in electron tomography**](https://www.sciencedirect.com/science/article/pii/S2590152419300145)

## Visualization
1. [`Chimera`](https://www.cgl.ucsf.edu/chimera/) - [**UCSF Chimera--a Visualization System for Exploratory Research and Analysis**](https://pubmed.ncbi.nlm.nih.gov/15264254/)
2. [`ChimeraX`](http://www.rbvi.ucsf.edu/chimerax/) - [**UCSF ChimeraX: Meeting modern challenges in visualization and analysis**](https://onlinelibrary.wiley.com/doi/full/10.1002/pro.3235)
3. [`ArtiaX`](https://github.com/FrangakisLab/ArtiaX)
4. [`blik`](https://github.com/brisvag/blik) - [**Blik is an extensible 3D visualisation tool for the annotation and analysis of cryo-electron tomography data**](https://journals.plos.org/plosbiology/article?id=10.1371/journal.pbio.3002447)
5. [`Colabseg`](https://github.com/KosinskiLab/colabseg) - [**ColabSeg: An interactive tool for editing, processing, and visualizing membrane segmentations from cryo-ET data**](https://www.sciencedirect.com/science/article/pii/S1047847724000078?dgcid=rss_sd_all)

# Conventions
## 3DEM Convention
* [3DEM Conventions](https://github.com/azazellochg/3DEM-conventions)
