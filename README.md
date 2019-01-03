# QMRITools

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.2530801.svg)](https://doi.org/10.5281/zenodo.2530801)
[![contributions welcome](https://img.shields.io/badge/contributions-welcome-brightgreen.svg?style=flat)](https://github.com/dwyl/esta/issues)
[![HitCount](http://hits.dwyl.io/mfroeling/DTITools.svg)](http://hits.dwyl.io/mfroeling/DTITools)

* [Information](#information)
* [Install toolbox](#install-toolbox)
* [Using the toolbox](#using-the-toolbox)
* [Functionality](#functionality)

## Information

QMRITools is developed for [Mathematica](https://www.wolfram.com/mathematica/).
It contains the following toolboxes:

- CardiacTools
- CoilTools
- DenoiseTools
- DixonTools
- ElastixTools
- GeneralTools
- GradientTools
- ImportTools
- IVIMTools
- JcouplingTools
- MaskingTools
- NiftiTools
- PhysiologyTools
- PlottingTools
- ProcessingTools
- RelaxometryTools
- SimulationTools
- VisteTools

A list off all functions and their help can be found int ``All-Functions.nb``. Documentation of all functions and their options is fully integrated in the Mathematica documentation.
The toolbox always works within the latest version of Mathematica and does not support any backward compatibility.

All code and documentation is maintained and uploaded to github using [Workbench](https://www.wolfram.com/workbench/).

## Install toolbox

Install the toolbox in the Mathematica UserBaseDirectory > Applications.

	FileNameJoin[{$UserBaseDirectory, "Applications"}]

Some functions of QMRITools call on external executables and software.
These executables need to be placed in "QMRITools\Applications".
For the latest version of these tools and their user licences please visit their website.

* [dcm2niix](https://github.com/rordenlab/dcm2niix/)
	* dcm2niix.exe
* [Elastix](http://elastix.isi.uu.nl/)
	* elastix.exe
	* transformix.exe

All functionality is tested under windows 10 with the latest Mathematica version. 
Elastix compatibility has been tested for MacOSX but is not guaranteed.  

A full build and release can be found [here](https://github.com/mfroeling/QMRITools/blob/master/QMRITools.zip). 

## Using the toolbox

The toolbox can be loaded by using <<QMRITools`

A list of all QMRITools packages is generated by 
	
	QMRIToolsPackages[]

A list of all DTITools functions or functions per toolbox is generated by 

	QMRIToolsFunctions[]
	QMRIToolsFunctions["toolboxname"]
	
To print the documentation of all functions use

	QMRIToolsFuncPrint[]
	QMRIToolsFuncPrint["toolboxname"]

## Functionality

The toolbox contains over 250 Functions and options of processing and analyzing data.
A summary of the core functionality can be found here. 

* Diffusion Analysis
	* Signal drift correction 
	* LLS, WLLS and iWLLS methods
	* REKINDLE outlier detection
	* IVIM fitting (fixed parameters, back-projection and Bayesian fitting)
	* Parameter fitting using histogram analysis
	* Joining and sorting of multiple series of the same volume
	* Joining multiple stacks with slice overlap into one stack
* Diffusion Gradients optimization
	* Single and multi shell
	* Rotating and correcting Bmatrix
	* Actual b-value estimation by gradient sequence integration
	* Gradient visualization
* Noise suppression
	* LMMSE noise suppression
	* PCA noise suppression based on ramom matrix theory
	* Anisotropic tensor smoothing using diffusion filter.
* Importing and Exporting
	* Dicom data (classing and enhanced file format)
	* Nifti data (.nii and .img .hdr, supports .gz files)
	* Compatible with ExplorDTI and Viste for fiber tractography
* Data visualization
	* 2D 3D and 4D viewer
	* Multiple images: Transparent overlay, difference and, checkboard overlays
	* Legend bars and image labels
	* Saving to pdf, jpg, animated gif and movie
* Masking
	* Automate and threshold masking
	* Extracting parameters form masks
	* Smoothing masks
	* Smoothing muscle segmentation
* Motion and distortion correction (Registration using elastix)
	* Rigid, affine, b-spline and cyclic registration 
	* nD to nD registration
	* Automated series processing 
	* Slice to slice motion correction of 3D and 4D data
* Dixon Reconstruction
	* B0 phase unwrapping
	* DIXON iDEAL reconstruction with T2start
* Relaxometry fitting
	* T2 fitting
	* T1rho fitting
	* Tri Exponential T2 fitting
	* EPG based T2 fitting with slice profile
* Simulation Framework
	* Diffuison tensor simulation and analysis
	* Bloch and EPG simulations
	* Cardiac DTI models (fiber architecture)
* Cardiac Diffusion analysis 
	* Breathing motion correction
	* Corrupted slice rejection
	* Local myocardial coordinate system calculation
	* helix angle and fiber architecture matrix
	* AHA 17 parameter description
	* Transmural parameter description	

## Demonstrations

The toolbox contains a file ``demo.nb`` and demo data folder testdata. This wil give a global overview of the functionality of the toolbox. 
	
## License
https://opensource.org/licenses/BSD-3-Clause

Some code in the NiiTools packages was based on https://github.com/tomdelahaije/nifti-converter
