
<img src="images/1-logos-pan-eu-cost.png" alt="PANGEOS" width="100%"/> 

# Uncertainty quantification (UQ) and propagation in remote sensing

This code is based on the PANGEOS COST Action first <a href="https://pangeos.eu/ss1/" target="_blank">Summer School</a> held in Bucharest, Romania in 30 September -- 4 October 2024.

The notebooks show how to propagate uncertainty of spectral measurements from level 0 (raw digital numbers) to level 4 (high level model outputs) with the 
<a href="https://punpy.readthedocs.io/en/latest/" target="_blank">`punpy`</a> Python package and 
<a href="https://www.comet-toolkit.org/about/" target="_blank">CoMet toolkit</a>

# TOC

- [Contents](#contents)
- [Installation](#installation)
- [Quiz](#quiz)
- [Feedback](#feedback)
- [Acknowledgements](#acknowledgements)


# Contents

[back to TOC](#toc)


|levels* | author | theory (pdf) | practice (notebook) |
|-------|----------|--------|-------|
| - | Egor Prikaziuk | <a href="https://drive.google.com/file/d/1cr8kyW4BjVWxNudcpQRq1q6VsPr8_Ul3/view?usp=sharing" target="_blank">Summary of the course</a>  | - |
| - | Gary Llewellyn    | <a href="https://drive.google.com/file/d/1IP_Aq2hQyFVKUuU9BIXB6mG8umVtM8kj/view?usp=sharing" target="_blank">Principles and Methods for Field Spectrometry</a> | - |
| - |  Gary Llewellyn    | <a href="https://drive.google.com/file/d/17wHjESf4nhyc43OkEJ_83gvcBvYcloDm/view?usp=sharing" target="_blank">Field Validation (scenarios for supporting passive satellite systems)</a> | - |
| 0-1 |  Laura Mihai   | <a href="https://drive.google.com/file/d/1XKpYide9HWjGeJtSom23ale96y-ryJKw/view?usp=sharing" target="_blank">CASE 1: Ground based reflectance retrieval using a dual-field-of-view spectrometer system </a> | [notebooks/case_1-Ex0-Piccolo.ipynb](notebooks/case_1-Ex0-Piccolo.ipynb) |
| 0-1 |  Laura Mihai| <a href="https://docs.google.com/spreadsheets/d/1xZlU-cT2PwqFsijUYuLjePmwRP0ud5O8/edit?usp=sharing&ouid=118085746887841822427&rtpof=true&sd=true" target="_blank"> Uncertainty analysis checklist </a> | [notebooks/case_1-Ex1.1_UPropagation_Noise_Cal.ipynb](notebooks/case_1-Ex1.1_UPropagation_Noise_Cal.ipynb) <br> <br> [notebooks/case_1-Ex1.2_UPropagation_Noise_Cal.ipynb](notebooks/case_1-Ex1.2_UPropagation_Noise_Cal.ipynb)<br> <br> [notebooks/case_1-Ex2_UPropagation_Cal_Noise_Nonlin.ipynb](notebooks/case_1-Ex2_UPropagation_Cal_Noise_Nonlin.ipynb) <br> <br> [notebooks/case_1-Ex3_UPropagation_Cal_Noise_Nonlin_Cos.ipynb](notebooks/case_1-Ex3_UPropagation_Cal_Noise_Nonlin_Cos.ipynb) |
| 1-2-3 |  Andy Hueni | <a href="https://drive.google.com/file/d/17dVlzXyc6Hsnp-Waqoe8me4Z7BlP3TAn/view?usp=sharing" target="_blank"> Uncertainty of Reflectance Factor and NDVI </a>  | [notebooks/case_2-Ex1-VI.ipynb](notebooks/case_2-Ex1-VI.ipynb) <br> <br> [notebooks/case_2-Ex2-retrieval.ipynb](notebooks/case_2-Ex2-retrieval.ipynb) |
| 2-3 |  Jose Gomez-Dans   | <a href="https://drive.google.com/file/d/1K2Y8H6MLXy2uD08ZCAp4_aBaDEqCzBoP/view?usp=sharing" target="_blank"> A brief look at biophysical parameter retrieval using radiative transfer models </a> |(external Python)  <a href="https://github.com/pangeos-cost/pangeos_uq" target="_blank"> GitHub repository pangeos_uq </a> |
| 2-3-4 |  Egor Prikaziuk   | <a href="https://drive.google.com/file/d/1Gl84QG2wUHjBiKDdCcJq-JfQG79WNFWw/view?usp=sharing" target="_blank">SCOPE model: what can you use it for</a> | - | 
| 3-4 |  Andy Hueni & Mike Werfeli  | <a href="https://drive.google.com/file/d/1lpc47y9x5CLsxO-TWJx6h2g-6CFDhHfG/view?usp=sharing" target="_blank"> Uncertainty of SCOPE </a> |  [notebooks/case_3-Ex1.1-Run_SCOPE_from_Python.ipynb](notebooks/case_3-Ex1.1-Run_SCOPE_from_Python.ipynb) <br><br> [notebooks/case_3-Ex1.2-COMET_Call_of_SCOPE.ipynb](notebooks/case_3-Ex1.2-COMET_Call_of_SCOPE.ipynb) |
| 2-3 |  Jochem Verrelst | <a href="https://drive.google.com/file/d/1PldD4eUquZ-3r2I3ZXj_aSe8UI78jqDc/view?usp=sharing" target="_blank"> Tutorial: ARTMO essentials </a> | (external MATLAB) <a href="https://artmotoolbox.com/" target="_blank"> ARTMO toolbox </a> |
| 2-3 |  Jochem Verrelst | <a href="https://drive.google.com/file/d/1D-xDQAxKI3--4WBwQda-GA1POw9nkF5z/view?usp=sharing" target="_blank"> Tutorial: Semi-automatic mapping of vegetation properties using MLRA toolbox </a> | (external MATLAB) <a href="https://artmotoolbox.com/" target="_blank"> ARTMO toolbox </a> |
| 2-3 |  Jose Luis Garcia & Jochem Verrelst | <a href="https://drive.google.com/file/d/1_puznklbZBjVESdh0GcoxOvPtsRaZcjd/view?usp=sharing" target="_blank"> Epistemic uncertainty </a> | (external MATLAB) <a href="https://artmotoolbox.com/" target="_blank"> ARTMO toolbox </a> |
| 1-2 |  Joe Fennell | - | (external Python) <a href="https://github.com/pangeos-cost/pangeos-training-24" target="_blank"> GitHub repository pangeos-training-24 </a> | 


\* Levels of remote sensing data products

| level    | description |
|----------|-------|
| 0  | raw (uncalibrated) digital numbers     |
| 1  | calibrated measurements in absolute units (radiances) <br> for satellite / ariborne - top of atmosphere [at sensor] radiance   |
| 2  | for ground spectrometer - same as level 1 <br> for satellite / ariborne - top of canopy [surface] atomspherically corrected radiance or reflectance     |
| 3  | retrieved biophysical traits (leaf area index, LAI)  <br> multitemporal composites (of e.g. spectral indices)  |
| 4  | computed higher-level products (gross primary productivity, GPP; land surface temperature, LST)    |

# Installation 

[back to TOC](#toc)

1. Install Python (preferably <a href="https://docs.anaconda.com/miniconda/install/" target="_blank">miniconda</a>)
2. Download this repository (upper right corner green button `<>Code` -> `Download ZIP`
	- unzip somewhere
3. Open `Anaconda Promt` 
	- search for "Anaconda Promt..." on your computer
4. Navigate to the folder of the repository in the `Anaconda Promt` 
	- type in the `Anaconda Promt` `cd C:\Users\PrikaziukE\Downloads\uq-training-main\uq-training-main`
	- of course not ..PrikaziukE.. but a path on your own computer
5. Create a new conda environment from the .yml file
	- type in the `Anaconda Promt` `conda env create --file environment.yml`
	- you may be asked to type `Y` for yes to agree to the installation
6. Activate the environment
	- type in the `Anaconda Promt` `conda activate uq`
7. Launch jupyter lab
	- type in the `Anaconda Promt` `jupyter lab`
8. In the JupyterLab window navige to [notebooks](notebooks) folder and run examples

Note, this does not include `matlabengine` installation because this will depend on your MATLAB version. There are instructions in [notebooks/case_3-Ex1.1-Run_SCOPE_from_Python.ipynb](notebooks/case_3-Ex1.1-Run_SCOPE_from_Python.ipynb)

Installation <a href="https://pangeos.eu/wp-content/uploads/2024/09/pre-workshop-tasks.pdf" target="_blank"> instructions</a> with screenshots.


# Quiz
[back to TOC](#toc)

Assess your understanding of the topics covered during the training course with the following <a href="https://form.jotform.com/243444675125357" target="_blank">`Quiz`</a>


# Feedback

[back to TOC](#toc)

Feel free to give your suggestions and share your experiences in the <a href="https://docs.google.com/forms/d/e/1FAIpQLSe1C61rHnuVDpM1msnse8rKa_fsqdBcFXbgYdBcDj_48awtWg/viewform?usp=sharing" target="_blank"> form</a>.


# Acknowledgements

[back to TOC](#toc)

This repository is based upon work from COST Action 
<a href="https://pangeos.eu/" target="_blank">PANGEOS CA22136</a> supported by 
<a href="https://www.cost.eu/actions/CA22136/" target="_blank"> the COST (European Cooperation in Science and Technology</a>.

<img src="images/1-logos-pan-eu-cost.png" alt="PANGEOS" width="100%"/> 

COST (European Cooperation in Science and Technology) is a funding agency for research and innovation networks. 
Our Actions help connect research initiatives across Europe and enable scientists to grow their ideas by sharing them with their peers. 
This boosts their research, career and innovation. <a href="http://www.cost.eu" target="_blank">http://www.cost.eu </a>

