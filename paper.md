---
title: 'Training course on Uncertainty quantification and propagation in remote sensing'
tags:
  - remote sensing
  - uncertainty 
  - Python
authors:
  - name: Egor Prikaziuk
    orcid: 0000-0002-7331-7004
    affiliation: 1
  - name: Laura Mihai
    orcid: 0000-0003-3869-1890
    affiliation: 2
  - name: Agnieszka Bialek
    orcid: 0000-0003-4502-2687
    affiliation: 3
  - name: Gary Llewellyn
    affiliation: 4
  - name: Andreas Hueni
    orcid: 0000-0002-4283-2484
    affiliation: 5
  - name: Mike Werfeli
    orcid: 0000-0001-5768-8887
    affiliation: 5
  - name: Jos\'e G\'omez-Dans
	orcid: 0000-0003-4787-8307
    affiliation: 6
  - name: Jochem Verrelst
    orcid: 0000-0002-6313-2081
    affiliation: 7
  - name: Jose Luis Garcia-Soria
    orcid: 0000-0002-7693-0891
    affiliation: 7
  - name: Joseph Fennell
    orcid: 0000-0001-6874-6667
    affiliation: 8
  - name: Dessislava Ganeva
    orcid: 0000-0001-9265-9539
    affiliation: 9
  - name: Shawn Carlisle Kefauver
    orcid: 0000-0002-1687-1965
    affiliation: 10
affiliations:
 - name: Faculty of Geo-Information Science and Earth Observation (ITC), University of Twente, Enschede, the Netherlands
   index: 1
 - name: CETAL-PhIL, National Institute for Laser, Plasma and Radiation Physics, Măgurele, Romania
   index: 2
 - name: National Physical Laboratory, Teddington, the UK
   index: 3
 - name: 2Excel Aviation, Northamptonshire, the UK
   index: 4
 - name: University of Zurich, Zurich, Switzerland
   index: 5
 - name: King's College London, Leverhulme Centre for Wildfires, National Centre for Earth Observation, UK
   index: 6
 - name: Image Processing Lab, University of Valencia, Valencia, Spain
   index: 7
 - name: The open university, Milton Keynes, the UK
   index: 8
 - name: Space Research and Technology Institute, Bulgarian Academy of Sciences, Sofia, Bulgaria
   index: 9
 - name: University of Barcelona, Barcelona, Spain
   index: 10
date: 18 October 2025
---

# Summary

Uncertainty propagation in remote sensing is crucial for drawing solid data-based conclusions. Yet, this topic is often disregarded in MSc and PhD curricula, leading to inappropriate or incomplete uncertainty estimates in scientific publications and data products. 
The Pan-European Network of Green Deal Agriculture and Forestry Earth Observation Science (PANGEOS) funded by the European Cooperation in Science and Technology (COST) organisation brings together researchers to share their expertise and to bring up a new generation of scientists. In October 2024, PANGEOS conducted an intensive 5-day summer school in which more than 20 participants learned how to propagate the uncertainty of spectral measurements to uncertainty in higher-level products. The training material in the form of Python Jupyter notebooks is publicly available on GitHub https://github.com/pangeos-cost/uq-training.
This learning module teaches the steps of uncertainty propagation from ground measurements through vegetation indices and retrieved plant traits toward higher-level model estimates, like gross primary productivity and evapotranspiration. All three pathways of retrieval uncertainty estimation, regression-based (vegetation indices), radiative transfer model-based, and hybrid (a combination of both regression and model-based methods), are demonstrated. In addition, challenges of uncertainty propagation through satellite imagery are discussed in a separate block.

# Statement of need

The field of remote sensing is known for having large uncertainties, fundamentally because of the disparity in what the sensor measures (e.g. radiance, irradiance, reflectance) and the magnitudes of interest such as biophysical parameters like, e.g., leaf area index (LAI), surface fluxes, or leaf pigment concentrations. In order to smoothly transition from the measurement space to the parameters of interest, models (either empirical or mechanistic) are used. Understanding all these nuances requires robust methods to quantify and propagate uncertainty. While methods of uncertainty propagation have been developed for years, they are always considered too complex to be taught in MSc or even PhD courses. As a result, remote-sensing-derived values reported in papers or distributed as scientific products often lack uncertainty estimates, which is crucial to understand the reliability of the data and to use it to make robust scientific statements. This learning module addresses this gap, teaching how to propagate uncertainty at any level of the remote sensing product generation chain from raw digital numbers to higher-level products like plant productivity or evaporation.


# Learning module

## Learning objectives

The learning objectives are the following:
1. To identify and discuss possible sources of uncertainty in field spectrometry and ways to minimise them.
2. To describe how a field spectrometer (e.g., the Piccolo Doppio system) is used to retrieve ground-level reflectance.
3. To draw an uncertainty tree diagram for a field spectrometer (e.g. Piccolo Doppio) to illustrate the sources of uncertainty and how they propagate through the process of deriving ground-based reflectance.
4. To explain how to use punpy (Propagation of UNcertainties in Python) package (or similar approaches) for uncertainty propagation at various levels (digital numbers, vegetation indices, higher-level products).
5. To explain the difference between radiative transfer models PROSAIL and SCOPE.

Furthermore, every Jupyter Python notebook has its own unit learning objectives specified in the markdown text. At the end of the module, there is a quiz for students to self-assess the fulfillment of the learning objectives.


## Module content

The course covers four topics:
1. Introduction to field, airborne and space-borne remote sensing. Uncertainty-aware field campaign planning.
2. Uncertainty propagation from raw readings to calibrated radiance and reflectance in field spectrometry.
	
	2.1 field spectrometry Piccolo Doppio
	
	2.2 * satellite sensor simulator PyEOSim 
	
3. Uncertainty propagation from top-of-canopy (bottom-of-atmosphere) reflectance to retrieved products
	
	3.1 through regression (vegetation indices): punpy available from CoMet toolkit
	
	3.2 * through a radiative transfer model: Bayesian approach
	
	3.3 * with a hybrid approach: ARTMO toolbox
	
4. Uncertainty propagation through complex models with punpy: SCOPE model 

The topics highlighted with an asterisk are followed ousdie of the provided Python environemnt (in Matlab or other linked Python codes).


## Instructional design

The course is designed for self-study. The topics contain lecture slides in PDF format to build a theoretical foundation and Python Jupyter notebook exercises to practice. For beginners, we recommend following the topics one by one. Each topic is expected to require around 2.5 hours each, leading to a 10-hour learning module (it is recommended to follow one topic per day). The topics marked with an asterisk, PyEOSim satellite sensor simulator, hybrid retrieval methods with ARTMO toolbox and radiative transfer model inversion in the Bayesian approach, are independent training packages.


## Experience of use in teaching and learning situations

The course was given face-to-face in October 2024. The theory and exercises lasted for four full days, plus an extra day for summary and student project presentation. The project included propagating uncertainty through the whole chain from spectrometer digital numbers to plant productivity with the SCOPE model. For the majority of trainees, it was the first encounter with the uncertainty diagrams. In the feedback form, training participants admitted that they were overwhelmed and required more time to reflect on the acquired knowledge. Therefore, we structured the contents and placed the material online so that everyone could follow at their own pace. Unfortunately, the online setup has its limitations, as the final student project and live support are not foreseen.


# Project story

The material was developed for PANGEOS COST action first Summer School held in Bucharest, Romania 30 September - 4 October 2024. 25 early career researchers and innovators were selected from 70 applicants from all over Europe.


# Acknowledgements

This work is supported by the EU COST (European Cooperation in Science and Technology) Action CA22136 “Pan-European Network of Green Deal Agriculture and Forestry Earth Observation Science” (PANGEOS).
