# Digital Twin Ocean (DTO) Pilot - Skagerrak

## Project Description
This repository includes the code generated during the pilot project “Havsplanering – Fall Lysekils Kommun” which explores the development of methodologies and data products for a Digital Twin Ocean (DTO) in the Baltic Sea drainage basin. The concept of a DTO refers to a dynamic, data-driven digital representation of the marine environment that can support marine spatial planning, environmental monitoring, and decision-making. This pilot focuses on the application of open-source satellite data - with a specific focus on the Copernicus Earth observation program - to generate actionable insights for local and regional stakeholders. The project was carried out in collaboration with the Swedish Space Agency and municipalities in northern Bohuslän. Funding comes from the Framework Partnership Agreement on Copernicus User Uptake (FPCUP).

The primary objective of the pilot is to demonstrate how open-access remote sensing data can be transformed into living, sensor-derived data products that are relevant for maritime planning. Specifically, the project has developed and tested three data products:

### Euphotic Depth and Zone Delineation 
  - The Euphotic depth refers to the upper layer of the ocean where light can penetrate, allowing photosynthesis to occur. The Eupthotic zone refers to areas where at least 1% of light incident at the water surface reaches the seafloor. These are important environmental factors as they reflect the seabed area available for underwater vegetation, which is in turn an important factor in the health of many marine ecosystems.
  - An investigation into the light properties of the underwater environment. Includes time series calculations of the depth of blue-green light penetration (490nm), areas where light is incident on the seafloor (and what percentage of light reaches the seafloor), and methods for aggregating and dynamically visualizing the results.
  - Bathymetry data is included for the region of interest, and is required for the investigation of the Euphotic zone.
    
### Macroalgae Habitat Distribution
  - Macroalgae communities are important ecosystem components in shallow coastal marine areas where they often form dense belts on hard substrates and provide a complex habitat for a large number of species. 
    Increased nutrition load and a following decrease in Secchi depth in coastal areas is a threat that will limit the distribution of macroalgae communities to a shallower depth, decreasing the total area 
    covered by these communities. The spatial distribution and cover of macroalgae communities is therefore subject to change over time and depend on environmental factors that can be monitored using RS data.
  - A machine learning model used to predict macroalgae habitat zones based on environmental conditions of the past 9 years (2016-2024) is presented as well as a separate notebook for result visualization and investigation.
  - Training data of benthic macroalgae occurences from SMHIs SHARK database is included along with the code tutorial.

### Water Quality Indicators 
  - Three different water quality indicators are investigated in the coastal regions of the Skagerrak and Kattegat seas. These indicators include: secchi depth (water clarity), chlorophyll-a concentration, and 
    oxygen availability at the seafloor. All indicators are generated using remote sensing products from the Copernicus Marine Service.
  - For relevant indicators, data is classified according to the swedish environmental quality standards for coastal waters, showing the potential for remote sensing digital twins to replace or contribute to 
    extensive yearly water testing protocols.

Together, these data products comprise a Digital Twin Ocean prototype, which can be built upon and scaled to generate a full-scale DTO for marine planning purposes.

For a detailed technical description of the project and data products please see the technical report included in this repository: [text](https://github.com/WSP-Sweden/DTO-Skagerrak/blob/main/WSP_DTO_Lysekil_Technical_Report_20250528.pdf)

## Code Usage
All code is provided in annotated tutorial Jupyter Notebooks which require very little programming experience to investigate and run. All code can be used for further development in different projects. To run the code provided in this repository the user needs to complete the following steps:
1. Create (free) accounts in:
    - WEkEO (https://wekeo.copernicus.eu/)
    - Copernicus Marine Services (https://marine.copernicus.eu/)
2. Start a WEkEO Workspace from the following web page after logging into your WEkEO account: https://wekeo.copernicus.eu/my-wekeo
3. Choose to spawn either a "Machine Learning" or "Machine Learning (GPU)" server instance. Computing resources of the different server environments can be found here: https://help.wekeo.eu/en/articles/7945473-which-are-the-computing-resources-of-the-wekeo-jupyterhub?pk_vid=8f7b592cbc1701351750312755f9bc5b
4. Download Jupyter notebooks and their associated "external_data" from this repository and load into your WEkEO workspace. These steps can also be managed through Git integration.
5. Complete the below steps to create the custom python environment required to run the notebooks included in this repository.

To create the required python environment:
1. Create a custom conda environment using the YAML file provided in this repository (DTO_conda.yaml"). This environment can be used to run all notebooks provided in this repository. This new conda environment "DTO_conda" will persist in your WEkEO JupyterHub workspace, meaning that you will not need to spend time resinstalling extra libraries every time you restart a server instance:<br/>
    - Open a terminal in your WEkEO JupyterHub <br/>
    - Use the YAML file included in this repo to create a new environment: <br/>
        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;conda env create -f DTO_conda.yaml <br/>
    - Activate your new conda environment "DTO_conda": <br/>
        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;conda activate DTO_conda <br/>
    - Add the new ipykernel. In order to use the new environment in a notebook you need to conduct this step:<br/>
        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;python -m ipykernel install --user --name DTO_conda <br/>
    - Refresh the webpage for the changes to take effect.<br/>
    - With a notebook open, select the newly created kernel "DTO_conda" in the upper right hand corner of the screen.<br/>
    - You are now ready to run the notebook!<br/>
2. Replace the "username" and "password" variables at the beginning of the notebook with your own credentials for Copernicus Marine
3. Run the notebook, making sure to use your new "DTO_conda" kernel

Alternatively, you can use the preinstalled "wekeolab" conda environment and install a number of extra python packages. Note that if you choose this option you will need to reinstall these packages every time you restart your server instance:
1. Open a terminal in your WEkEO JupyterHub.
2. Activate the "wekeolab" conda environment: <br/>
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;conda activate wekeolab <br/>
3. Execute the following code: <br/>
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;conda install xcube xcube-cmems contextily hvplot seaborn bottleneck openeo xgboost optuna geoviews copernicusmarine -y <br/>
4. Open the notebook you would like to run and select the "wekeolab" environment as your kernel

As of 2025-07-01, code will not be maintained as the proof of concept funding does not cover updates. We hope to generate a user group that will fork the repository and maintain the code in other environments so that these tools can continue to be used!

