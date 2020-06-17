## Introduction
This repository contains the code used to manipulate ERA5-land climate data<sup>1</sup> and produce results for the Vore et. al (2020) paper currently under review in the journal Hydrological Processes.

## Files
All code is presented in Jupyter Notebook files written in Python. Files are organized by their relevancy in the mansucript, with the flow chart below showing the order in which files should be run to replicate our work. 

## Individual Files
**ERA5LAND_dataset_to_Raster.ipynb** --> This code takes hourly ERA5-land datasets and turns them into rasters. The code can input the following variables: total precipitaion, 2m temperature, runoff, Evapotransipration, snow cover, snow depth, and potential evapotransipration. After rasters have been create, they are cut to a watershed's shapefile boundary, and then the climate variable is totaled/averaged over the basins area.

**Hamond_PET_Calc.ipynb** --> This code uses daily temperature averages to calculate the potential evapotranspiration (PET) of a watershed. A  maximum and minimum PET was calculed using K=1.2 and K=1.4<sup>2</sup>

**Aridity.ipynb** --> This code uses yearly potential evapotranspirationa and precipitation totals to determine the aridity of a watershed for each given year. The aridity results will be used in calculating the constants in the Safranyik et al. (1975) model<sup>3</sup>.

**Growing_Season.ipynb** --> This code calculates the average last day where minimum air tempertaures dip below -1 in the spring and the avergae day in fall where min temperatures fall below -1. The  spand between freezing temperatures are used to define the growing season. One growing season parameter is calculated for each watershed. The results will be used when calculating constraints in the Safranyik et al. (1975) model<sup>3</sup>.


## References
<sup>1</sup> Copernicus Climate Change Service (C3S) (2019). ERA5-Land hourly data from 1981 to present. Copernicus Climate Change Service. https://doi.org/10.24381/cds.e2161bac

<sup>2</sup> Zhou, G., Wei, X., Chen, X., Zhou, P., Liu, X., Xiao, Y., … Su, Y. (2015). Global pattern for the effect of climate and land cover on water yield. Nature Communications, 6, 5918. https://doi.org/10.1038/ncomms6918

<sup>3</sup> Safranyik, L., Shrimpton, D. M., & Whitney, H. S. (1975). An interpretation of the interaction between lodgepole pine, the mountain pine beetle, and its associated blue stain fungi in western Canada. Management of Lodgepole Pine Ecosystems Symposium Proceedings, 406–428. http://scholar.google.com/scholar?hl=en&btnG=Search&q=intitle:No+Title#0


