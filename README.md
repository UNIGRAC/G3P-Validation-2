# Evaluation of the G3P project against in-situ groundwater observations (2024) 
Codes (.ipynb), data (.shp) and workflow (.pdf) to process G3P (.nc) and in-situ groundwater data (.xlsx) [Validation 2024]   
Main Author: [Sacha MORLIERE](https://github.com/SachaMORLIERE)
## Introduction  
This evaluation aims to compare, within a given region and period, the time series of GroundWater Storage Anomalies (GWSA) from G3P with the time series of GroundWater Level Anomalies (GWLA) and GroundWater Storage Anomalies (GWSA) from wells.  
## Methodology  
Four codes are used in a specific order. At the beginning of each code, a "README" is annotated to describe the steps and indicate the necessary inputs and outputs. Note that the outputs of some codes serve as inputs for others.   
- Methodology report: [IGRAC Internship Report.pdf](https://github.com/UNIGRAC/G3P-Validation-2/blob/bc0d56ede5a386bfe8f9c2f8f047730db3c31116/IGRAC%20Internship%20Report.pdf)

The Paris Basin is used here as an example:  
### 1. ParisBasin_GWLA_GWSA.ipynb  
•	Purpose: Generate GWLA and/or GWSA time series (if specific yield values are available) from groundwater depth data.  
•	Method: A grid-based method is used to reduce the overrepresentation of well clusters and visualize variations at a local scale. Linear interpolation is applied to fill some gaps in the time series.  
•	Inputs : [ParisBasin_GWL.xlsx](https://github.com/UNIGRAC/G3P-Validation-2/blob/bc0d56ede5a386bfe8f9c2f8f047730db3c31116/Paris_Basin%20-%20DEMO/1%20In%20Situ/ParisBasin_GWL.xlsx) ; [wells_Sy.xlsx](https://github.com/UNIGRAC/G3P-Validation-2/blob/bc0d56ede5a386bfe8f9c2f8f047730db3c31116/Paris_Basin%20-%20DEMO/1%20In%20Situ/wells_Sy.xlsx)  
•	Outputs: [ParisBasin_GWLA_GWSA.xlsx](https://github.com/UNIGRAC/G3P-Validation-2/blob/bc0d56ede5a386bfe8f9c2f8f047730db3c31116/Paris_Basin%20-%20DEMO/1%20In%20Situ/ParisBasin_GWLA_GWSA.xlsx)  
### 2. ParisBasin_G3P_GWSA.ipynb  
•	Purpose: Extract GWSA time series from G3P (netCDF files) and the geometry of the studied region (shapefile). The latest version of G3P, v1.12, is used.  
•	Inputs: [.nc annual datasets from G3P](https://github.com/UNIGRAC/G3P-Validation-2/tree/bc0d56ede5a386bfe8f9c2f8f047730db3c31116/Paris_Basin%20-%20DEMO/2_G3P_dates) ; [Grids_G3P.shp](https://github.com/UNIGRAC/G3P-Validation-2/blob/f03c6b4424135eddf017a791ba9c28c08da3a2d0/Paris_Basin%20-%20DEMO/2_G3P_dates/Grids_G3P.shp)    
•	Outputs: [ParisBasin_G3P_GWSA.xlsx](https://github.com/UNIGRAC/G3P-Validation-2/blob/bc0d56ede5a386bfe8f9c2f8f047730db3c31116/Paris_Basin%20-%20DEMO/2_G3P_dates/ParisBasin_G3P_GWSA.xlsx)  
### 3. ParisBasin_validation.ipynb  
•	Purpose: Compare the GWSA time series from G3P with in-situ GWLA and GWSA time series. Note that for the comparison with in-situ GWLA, the data are normalized. Pearson correlation coefficient (pattern) and Mann-Kendall analysis (long-term trend) are used.  
•	Inputs: [ParisBasin_GWLA_GWSA.xlsx](https://github.com/UNIGRAC/G3P-Validation-2/blob/bc0d56ede5a386bfe8f9c2f8f047730db3c31116/Paris_Basin%20-%20DEMO/3%20Comparisons/ParisBasin_GWLA_GWSA.xlsx) ; [ParisBasin_G3P_GWSA.xlsx](https://github.com/UNIGRAC/G3P-Validation-2/blob/bc0d56ede5a386bfe8f9c2f8f047730db3c31116/Paris_Basin%20-%20DEMO/3%20Comparisons/ParisBasin_G3P_GWSA.xlsx)  
•	Outputs: Jupiter Notebook plots  
### 4. (OPTIONAL) ParisBasin_correlation_map.ipynb  
•	Purpose: Compare GWSA time series from G3P with in-situ GWLA at the cell scale to observe the spatial variability of correlations.  
•	Inputs: [ParisBasin_GWLA_GWSA.xlsx](https://github.com/UNIGRAC/G3P-Validation-2/blob/bc0d56ede5a386bfe8f9c2f8f047730db3c31116/Paris_Basin%20-%20DEMO/3%20Comparisons/ParisBasin_GWLA_GWSA.xlsx) ; [ParisBasin_G3P_GWSA.xlsx](https://github.com/UNIGRAC/G3P-Validation-2/blob/bc0d56ede5a386bfe8f9c2f8f047730db3c31116/Paris_Basin%20-%20DEMO/3%20Comparisons/ParisBasin_G3P_GWSA.xlsx)   
•	Outputs: Jupiter Notebook map   
