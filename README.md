## Introduction
This repository contains the code used to manipulate ERA5-land climate data<sup>1</sup> and produce results for the Vore et. al (2020) paper currently under review in the journal Hydrological Processes.

## Files
All code is presented in Jupyter Notebook files written in Python. Files are organized by their relevancy in the mansucript, with the flow chart below showing the order in which files should be run to replicate our work. 

### Individual Files
**ERA5LAND_dataset_to_Raster.ipyn** --> This code takes hourly ERA5-land datasets and turns them into rasters. The code can input the following variables: total precipitaion, 2m temperature, runoff, Evapotransipration, snow cover, snow depth, and potential evapotransipration. After rasters have been create, they are cut to a watershed's shapefile boundary, and then the climate variable is totaled/averaged over the basins area.

**Hammond_PET_Calc.ipyn** --> This code uses daily temperature averages to calculate the potential evapotranspiration (PET) of a watershed. A  maximum and minimum PET was calculed using K=1.2 and K=1.4<sup>2</sup>


## References
<sup>1</sup> Copernicus Climate Change Service (C3S) (2019). ERA5-Land hourly data from 1981 to present. Copernicus Climate Change Service. https://doi.org/10.24381/cds.e2161bac
<sup>2</sup> Zhou, G., Wei, X., Chen, X., Zhou, P., Liu, X., Xiao, Y., … Su, Y. (2015). Global pattern for the effect of climate and land cover on water yield. Nature Communications, 6, 5918. https://doi.org/10.1038/ncomms6918


