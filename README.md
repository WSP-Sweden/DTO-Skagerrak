# Digital Twin Ocean (DTO) Pilot - Skagerrak

## Project Description
This repository includes the code generated during the pilot project “Havsplanering – Fall Lysekils Kommun” which explores the development of methodologies and data products for a Digital Twin Ocean (DTO) in the Baltic Sea drainage basin. The concept of a DTO refers to a dynamic, data-driven digital representation of the marine environment that can support marine spatial planning, environmental monitoring, and decision-making. This pilot focuses on the application of open-source satellite data - with a specific focus on the Copernicus Earth observation program - to generate actionable insights for local and regional stakeholders. The project was carried out in collaboration with the Swedish Space Agency and municipalities in northern Bohuslän. Funding comes from the Framework Partnership Agreement on Copernicus User Uptake (FPCUP).

The primary objective of the pilot is to demonstrate how open-access remote sensing data can be transformed into living, sensor-derived data products that are relevant for maritime planning. Specifically, the project has developed and tested three data products:

### Euphotic Zone Delineation 
  - The Euphotic zone refers to the upper layer of the ocean where light can penetrate, allowing photosynthesis to occur. It is an important environmental zone as it reflects the seabed area available for 
    underwater vegetation, which is in turn an important factor in the health of many marine ecosystems
  - An investigation into the light properties of the underwater environment. Includes time series calculations of the depth of blue light penetration, areas where light is incident on the seafloor (and what     
    percentage of light reaches the seafloor), and methods for aggregating and dynamically visualizing the results.
    
### Macroalgae Habitat Distribution
  - Macroalgae communities are important ecosystem components in shallow coastal marine areas where they often form dense belts on hard substrates and provide a complex habitat for a large number of species. 
    Increased nutrition load and a following decrease in Secchi depth in coastal areas is a threat that will limit the distribution of macroalgae communities to a shallower depth, decreasing the total area 
    covered by these communities. The spatial distribution and cover of macroalgae communities is therefore subject to change over time and depend on environmental factors that can be monitored using RS data.
  - A machine learning model used to predict macroalgae habitat zones is presented along with training data.

### Water Quality Indicators 
  - Three different water quality indicators are investigated in the coastal regions of the Skagerrak and Kattegat seas. These indicators include: secchi depth (water clarity), chlorophyll-a concentration, and 
    oxygen availability at the seafloor. All indicators are generated using remote sensing products from the Copernicus Marine Service.
  - For relevant indicators, data is classified according the swedish environmental quality standards for coastal waters, showing the potential for remote sensing digital twins to replace or contribute to 
    extensive yearly water testing protocols.

Together, these data products comprise a Digital Twin Ocean prototype, which can be built upon and scaled to generate a full-scale DTO for marine planning purposes.

## Code Usage
All code is provided in annotated tutorial Jupyter Notebooks which require very little programming experience. All code can be used for further development in different projects. To run the code provided in this repository the user needs to create (free) accounts in 
1. WEkEO (https://wekeo.copernicus.eu/)
2. Copernicus Marine Services (https://marine.copernicus.eu/)

All code can be run in the WEkEO Jupyter environment with the following steps:
1. Once logged into WEkEO, spawn a remote server at the following location: https://jupyterhub.prod.wekeo2.eu/hub/spawn
2. Install the following packages via terminal in the "wekeolab" environment (more specific instructions are given at the beginning och each notebook):
   - xcube-cmems
   - bottleneck
3. Replace the "username" and "password" variables at the beginning of the notebook with your own credentials for Copernicus Marine
4. Run the notebook using the "wekeolab" kernel

Alternatively, the DTO_Skagerrak_environment.txt can be used to build a custom environment either locally or on the WEkEO server workspace.

As of 2025-07-01, code will not be maintained as the proof of concept funding does not cover updates. We hope to generate a user group that will fork the repository and maintain the code in other environments so that these tools can continue to be used!

