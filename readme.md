
<img src="images/1-logos-pan-eu-cost.png" alt="PANGEOS" width="100%"/> 


# Uncertaintiy quantification: Level 0 -> Level 4

This code is based on the PANGEOS COST Action first <a href="https://pangeos.eu/ss1/" target="_blank">Summer School</a> held in Bucharest, Romania in 30 September -- 4 October 2024.

The notebooks show how to propagate uncertainty of spectral measurements from level 0 (raw digital numbers) to level 4 (high level model outputs) with the 
<a href="https://punpy.readthedocs.io/en/latest/" target="_blank">`punpy`</a> Python package and 
<a href="https://www.comet-toolkit.org/about/" target="_blank">CoMet toolkit</a>

For reference

| level    | description |
|----------|-------|
| 0  | raw (uncalibrated) digital numbers     |
| 1  | calibrated measurements in absolute units     |
| 2  | [for satellite data] - top of canopy, atomspherically corrected radiance or reflectance     |
| 3  | retrieved biophysical traits (leaf area index, LAI; fraction of absorbed photosynthetically active radiation, fAPAR)    |
| 4  | computed higher-level products (gross primary productivity, GPP; land surface temperature, LST)    |

# Installation 

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

# Cases

The notebooks are grouped into six cases, three of which 1-3 are illustrated in the Jupyter Notebooks of this repository (folder [notebooks](notebooks)) and some of them (2, 4) in other repositories:

0. Case 0 (theory only) - filedwork planning considerations in relation to uncertainty
1. Case 1 (notebooks) - ground measurements with a dual-view spectrometer system Piccolo doppio
   0. Piccolo instrument description and data processing [notebooks/case_1-Ex0-Piccolo.ipynb](notebooks/case_1-Ex0-Piccolo.ipynb)
   1. Uncertainty propagation for radiance measurements [notebooks/case_1-Ex1.1_UPropagation_Noise_Cal.ipynb](notebooks/case_1-Ex1.1_UPropagation_Noise_Cal.ipynb)
   2. Uncertainty propagation to reflectance [notebooks/case_1-Ex1.2_UPropagation_Noise_Cal.ipynb](notebooks/case_1-Ex1.2_UPropagation_Noise_Cal.ipynb)
   3. Uncertainty propagation conciderting the non-linearity of sensor response [notebooks/case_1-Ex2_UPropagation_Cal_Noise_Nonlin.ipynb](notebooks/case_1-Ex2_UPropagation_Cal_Noise_Nonlin.ipynb)
   4. Uncertainty propagation conciderting the uncertainty of the cosine head of irradiance sensor [notebooks/case_1-Ex3_UPropagation_Cal_Noise_Nonlin_Cos.ipynb](notebooks/case_1-Ex3_UPropagation_Cal_Noise_Nonlin_Cos.ipynb)
2. Case 2 (notebooks) - retrieval of biophysical variables from remote sensing data
	1. Uncertainty in Piccolo doppio reflectance -> uncertainty in vegetation (spectral) index [notebooks/case_2-Ex1-VI.ipynb](notebooks/case_2-Ex1-VI.ipynb)
    2. Uncertainty in Sentinel-2 reflectance -> uncertainty in fAPAR [notebooks/case_2-Ex2-retrieval.ipynb](notebooks/case_2-Ex2-retrieval.ipynb)
    3. Radiative transfer model (RTM) inversion is explained in a separate repository by `Jose Gomez-Dans` 
	<a href="https://github.com/pangeos-cost/pangeos_uq/blob/main/notebooks/09-PiccoloDoppioInversion.ipynb" target="_blank">09-PiccoloDoppioInversion.ipynb</a>
3. Case 3 (notebooks) - retrieved parameters to higher level model outputs
    1. Calling SCOPE (Soil Canopy Observation, Photochemistry and Energy fluxes) model from Python [notebooks/case_3-Ex1.1-Run_SCOPE_from_Python.ipynb](notebooks/case_3-Ex1.1-Run_SCOPE_from_Python.ipynb)
    2. Uncertainty in LAI -> uncertainty in GPP and LST with the SCOPE [notebooks/case_3-Ex1.2-COMET_Call_of_SCOPE.ipynb](notebooks/case_3-Ex1.2-COMET_Call_of_SCOPE.ipynb)
4. Case 4 (external MATLAB tool) - epistemic uncertainty propagation with the ARTMO toolbox
5. Case 5 (external Python repository) - uncertainty of the atmospheric correction is presented in a separate 
<a href="https://github.com/pangeos-cost/pangeos-training-24" target="_blank">PyEOSim</a> repository by `Joe Fennell`

# Theory (presentations)

| case      | author | topic |
|----------|--------|-------|
| 0  | Gary Llewellyn    | <a href="https://drive.google.com/file/d/1IP_Aq2hQyFVKUuU9BIXB6mG8umVtM8kj/view?usp=sharing" target="_blank">Principles and Methods for Field Spectrometry</a> |
| 0  |  Gary Llewellyn    | <a href="https://drive.google.com/file/d/17wHjESf4nhyc43OkEJ_83gvcBvYcloDm/view?usp=sharing" target="_blank">Field Validation (scenarios for supporting passive satellite systems)</a> |
| 1  |  Laura Mihai   | <a href="https://drive.google.com/file/d/1XKpYide9HWjGeJtSom23ale96y-ryJKw/view?usp=sharing" target="_blank">CASE 1: Ground based reflectance retrieval using a dual-field-of-view spectrometer system </a> |
| 1  |  Laura Mihai   | <a href="https://docs.google.com/spreadsheets/d/1xZlU-cT2PwqFsijUYuLjePmwRP0ud5O8/edit?usp=sharing&ouid=118085746887841822427&rtpof=true&sd=true" target="_blank"> Uncertainty analysis checklist </a> |
| 2  |  Jose Gomez-Dans   | <a href="https://drive.google.com/file/d/1K2Y8H6MLXy2uD08ZCAp4_aBaDEqCzBoP/view?usp=sharing" target="_blank"> A brief look at biophysical parameter retrieval using radiative transfer models </a> |
| 2  |  Jose Gomez-Dans   | <a href="https://github.com/pangeos-cost/pangeos_uq" target="_blank"> GitHub repository pangeos_uq </a> |
| 3  |  Egor Prikaziuk   | SCOPE model: what can you use it for |
| 3  |  Andy Hueni & Mike Werfeli  | <a href="https://drive.google.com/file/d/1lpc47y9x5CLsxO-TWJx6h2g-6CFDhHfG/view?usp=sharing" target="_blank"> Uncertainty of SCOPE </a> |
| 4  |  Jochem Verrelst | <a href="https://drive.google.com/file/d/1PldD4eUquZ-3r2I3ZXj_aSe8UI78jqDc/view?usp=sharing" target="_blank"> Tutorial: ARTMO essentials </a> |
| 4  |  Jochem Verrelst | <a href="https://drive.google.com/file/d/1D-xDQAxKI3--4WBwQda-GA1POw9nkF5z/view?usp=sharing" target="_blank"> Tutorial: Semi-automatic mapping of vegetation properties using MLRA toolbox </a> |
| 4  |  Jose Luis Garcia & Jochem Verrelst | <a href="https://drive.google.com/file/d/1_puznklbZBjVESdh0GcoxOvPtsRaZcjd/view?usp=sharing" target="_blank"> Epistemic uncertainty </a> |
| 5  |  Joe Fennell | <a href="https://github.com/pangeos-cost/pangeos-training-24" target="_blank"> GitHub repository pangeos-training-24 </a> |



## Acknowledgements
This repository is based upon work from COST Action 
<a href="https://pangeos.eu/" target="_blank">PANGEOS CA22136</a> supported by 
<a href="https://www.cost.eu/actions/CA22136/" target="_blank"> the COST (European Cooperation in Science and Technology</a>.

<img src="images/1-logos-pan-eu-cost.png" alt="PANGEOS" width="100%"/> 

COST (European Cooperation in Science and Technology) is a funding agency for research and innovation networks. 
Our Actions help connect research initiatives across Europe and enable scientists to grow their ideas by sharing them with their peers. 
This boosts their research, career and innovation. <a href="http://www.cost.eu" target="_blank">http://www.cost.eu </a>

