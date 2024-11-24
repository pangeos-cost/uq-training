
<img src="images/1-logos-pan-eu-cost.png" alt="PANGEOS" width="100%"/> 


# Uncertaintiy quantification: Level 0 -> Level 4

This code is based on the PANGEOS COST Action first [Summer School](https://pangeos.eu/ss1/) held in Bucharest, Romania in 30 September -- 4 October 2024.

The notebooks show how to propagate uncertainty of spectral measurements from level 0 (raw digital numbers) to level 4 (high level model outputs) with the [`punpy`](https://punpy.readthedocs.io/en/latest/) Python package and [CoMet toolkit](https://www.comet-toolkit.org/about/)

For reference

| level    | description |
|----------|-------|
| 0  | raw (uncalibrated) digital numbers     |
| 1  | calibrated measurements in absolute units     |
| 2  | [for satellite data] - top of canopy, atomspherically corrected radiance or reflectance     |
| 3  | retrieved biophysical traits (leaf area index, LAI; fraction of absorbed photosynthetically active radiation, fAPAR)    |
| 4  | computed higher-level products (gross primary productivity, GPP; evapotranspiration, ET)    |

# Cases

The notebooks are grouped into three cases:

1. Case 1 - ground measurements with a dual-view spectrometer system Piccolo doppio
   0. Piccolo instrument description and data processing [notebooks/case_1-Ex0-Piccolo.ipynb](notebooks/case_1-Ex0-Piccolo.ipynb)
   1. Uncertainty propagation for radiance measurements [notebooks/case_1-Ex1.1_UPropagation_Noise_Cal.ipynb](notebooks/case_1-Ex1.1_UPropagation_Noise_Cal.ipynb)
   2. Uncertainty propagation to reflectance [notebooks/case_1-Ex1.2_UPropagation_Noise_Cal.ipynb](notebooks/case_1-Ex1.2_UPropagation_Noise_Cal.ipynb)
   3. Uncertainty propagation conciderting the non-linearity of sensor response [notebooks/case_1-Ex2_UPropagation_Cal_Noise_Nonlin.ipynb](notebooks/case_1-Ex2_UPropagation_Cal_Noise_Nonlin.ipynb)
   4. Uncertainty propagation conciderting the uncertainty of the cosine head of irradiance sensor [notebooks/case_1-Ex3_UPropagation_Cal_Noise_Nonlin_Cos.ipynb](notebooks/case_1-Ex3_UPropagation_Cal_Noise_Nonlin_Cos.ipynb)
3. Case 2 - retrieval of biophysical variables from remote sensing data
    1. NDVI -> fAPAR propagation
    2. Radiative transfer model (RTM) inversion is explained in a separate repository by `Jose Gomez-Dans` [09-PiccoloDoppioInversion.ipynb](https://github.com/pangeos-cost/pangeos_uq/blob/main/notebooks/09-PiccoloDoppioInversion.ipynb)
5. Case 3 - computation of GPP with models
    1. fAPAR -> GPP with a light use efficiency (LUE) model
    2. LAI -> GPP with the SCOPE (Soil Canopy Observation, Photochemistry and Energy fluxes) model

An extra case illustrating the **uncertainty of the atmospheric** correction is presented in a separate [PyEOSim](https://github.com/pangeos-cost/pangeos-training-24) repository by `Joe Fennell`


## Acknowledgements
This repository is based upon work from COST Action [PANGEOS CA22136](https://pangeos.eu/), supported by [COST (European Cooperation in Science and Technology)](https://www.cost.eu/).

<img src="images/1-logos-pan-eu-cost.png" alt="PANGEOS" width="100%"/> 

COST (European Cooperation in Science and Technology) is a funding agency for research and innovation networks. Our Actions help connect research initiatives across Europe and enable scientists to grow their ideas by sharing them with their peers. This boosts their research, career and innovation. http://www.cost.eu