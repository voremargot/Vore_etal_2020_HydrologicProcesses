
## Introduction
This repository contains the code used to manipulate ERA5-land climate data<sup>1</sup> and produce results for the Vore et. al (2020) paper currently under review in the journal Hydrological Processes.

## Files
All code is presented in Jupyter Notebook files written in Python. Files are organized by their relevancy in the mansucript, with the flow chart below showing the order in which files should be run to replicate our work. 

## Individual Files
**ERA5LAND_dataset_to_Raster.ipynb** --> This code takes hourly ERA5-land datasets and turns them into rasters. The code can input the following variables: total precipitaion, 2m temperature, runoff, Evapotransipration, snow cover, snow depth, and potential evapotransipration. After rasters have been create, they are cut to a watershed's shapefile boundary, and then the climate variable is totaled/averaged over the basins area.

**Hamond_PET_Calc.ipynb** --> This code uses daily temperature averages to calculate the potential evapotranspiration (PET) of a watershed. A  maximum and minimum PET was calculed using K=1.2 and K=1.4<sup>2</sup>

**Aridity.ipynb** --> This code uses yearly potential evapotranspirationa and precipitation totals to determine the aridity of a watershed for each given year. The aridity results will be used in calculating the constants in the Safranyik et al. (1975) model<sup>3</sup>.

**Growing_Season.ipynb** --> This code calculates the average last day where minimum air tempertaures dip below -1 in the spring and the avergae day in fall where min temperatures fall below -1. The  spand between freezing temperatures are used to define the growing season. One growing season parameter is calculated for each watershed. The results will be used when calculating constraints in the Safranyik et al. (1975) model<sup>3</sup>.

**Calculating_Constraints.ipynb** --> This code calculate the contraints C1-C4 in the Safranyik et al. (1975) model<sup>3</sup> (Table  2 in Vore et al (2020)). This code takes the precipitation and temperature data for each year and creates a binary rasters (1 if the contstraint is met, 0 if it is not met) for C1, C3, and C4. For constraint C2, the code counts the number of cold days each year for each grid cell and creates a count Raster, identifying how many days the minimum temperature fell below -40C. A raster for each year and constraint is created. 

**MPB_Climate_Analysis.ipynb**--> This code uses all the outputs calculated in Aridity.ipynb, Growing_Season.ipynb,and Calculating_Constraints.ipynb to plot the relationship between MPB CSC's and MPB outbreaks themselves. The code can be run for different time-intervals (in the manuscript it mentions 5, 10, and 15 year analysis, but can be used over any time spans.

**ForestFire_Summary.ipynb** --> Creates a summary of forest fire events in each watershed since 1981.

**Climate Index and Forest Fires.ipynb** --> This code creates a climate index from noramlized precipitation anomalies and normalized temperature anomalies. Climate index trends are then calculated and plots showing the relationship between forest fire size and the climate index are produced for multiple seasons and years. 

**Forest Fires and Runoff.pynb** --> This code summerizes runoff/precipitation (R/P) and normalized precipitation anomalies (NPA) for 3 years pre- and post- forest fire events. Normalized R/P anomalies are calculated and the extreme R/P events (those that exceed the 95th perrcentile of data) are determined. These extreme R/P events are then compared to NPA to determine if they fall within the data distribution. 

**Runoff and MPB.ipynb** --> This code calcuates the normalized R/P anomalies for each year on record  and looks at linear trends of the runoff data during MPB outbreak and before MPB outbreaks. Subsets of the data are determined based on minimal changes in logging and forest fire ECA, with trends determined for each subset. 

**Fhu Equation.ipynb** --> 

## Data



## References
<sup>1</sup> Copernicus Climate Change Service (C3S) (2019). ERA5-Land hourly data from 1981 to present. Copernicus Climate Change Service. https://doi.org/10.24381/cds.e2161bac

<sup>2</sup> Zhou, G., Wei, X., Chen, X., Zhou, P., Liu, X., Xiao, Y., … Su, Y. (2015). Global pattern for the effect of climate and land cover on water yield. Nature Communications, 6, 5918. https://doi.org/10.1038/ncomms6918

<sup>3</sup> Safranyik, L., Shrimpton, D. M., & Whitney, H. S. (1975). An interpretation of the interaction between lodgepole pine, the mountain pine beetle, and its associated blue stain fungi in western Canada. Management of Lodgepole Pine Ecosystems Symposium Proceedings, 406–428. http://scholar.google.com/scholar?hl=en&btnG=Search&q=intitle:No+Title#0


