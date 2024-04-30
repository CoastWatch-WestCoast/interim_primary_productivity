# Interim Primary Productivity Project
This repository provides a set of notebook with code for scientist to assess how switching from the legacy MODIS-based primary productivity product to the to the interim VIIRS-based primary productivity product will impact their applications. 
## Background
Since 2005, SW fisheries and the CoastWatch West Coast Node have produced a satellite-based product for global oceanic primary productivity. Primary productivity on the ocean is the rate at which phytoplankton convert CO2 into organic C using photosynthesis. The product uses data from the MODIS-Aqua sensor to drive primary productivity algorithm Behrenfeld and Falkowski  (1997) algorithm.

The MODIS-Aqua sensor will soon be decommissioned and research is underway to replace the legacy MODIS-based primary productivity with new generation product based on an updated algorithm that is driven by modern satellite sensor data. However, the replacement product will not be ready before the MODIS sensor reaches the end of its life. 

The Interim Primary Productivity Project was funded to create an interim primary productivity product to bridge the gap between the end of legacy product and the beginning of new generation product. The goal for the project is to develop a product that tracks the legacy product in magnitude and patterns, thereby minimizing the impact that transition to the interim product will have on downstream applications. Major improvements to the accuracy and global applicability primary product estimates will presumably be introduced in the new generation product. The interim product is now available. It uses the Behrenfeld and Falkowski algorithm, but the data driving the model is sourced from the VIIRS-SNPP sensor.  

## Repository Organization

The repository is structured into directories, categorized by statistical method. Within each method are directories Python and R programming languages.

## Tutorial Module Descriptions

### [Unbiased Relative Difference Analysis](ERDDAP-basics)   
Calculate the mean unbiased relative difference (&psi;<sup>netPP</sup>) of the interim VIIRS netPP (netPP<sub>VIIRS</sub>) and legacy MODIS netPP (netPP<sub>MODIS</sub>) products within a user-specified region. &psi;<sub>netPP</sub> is calculated as the difference between netPP<sub>VIIRS</sub> and netPP<sub>MODIS</sub> divided by the mean of netPP<sub>VIIRS</sub> and netPP<sub>MODIS.  

$\Large\psi^{netPP} = \frac{netPP_{VIIRS} - netPP_{MODIS}}{(netPP_{VIIRS} + netPP_{MODIS}) \div 2}\$ 

The result will be a 120-month (10-year, from 2013-2022) mean monthly timeseries of &psi;<sub>netPP</sub> within your area of interest. Normalizing by the mean of the two values avoids arbitrarily selecting one product as reference. 

### [Difference Normalized to MODIS Analysis](difference_normalized_modis)   
Calculate the mean absolute relative difference (&Delta;<sub>rel</sub>) of the interim VIIRS netPP product (netPP<sub>VIIRS</sub>) and legacy MODIS netPP product (netPP<sub>MODIS</sub>) within a user-specified region. &Delta;<sub>rel</sub> is calculated as the difference between netPP<sub>VIIRS</sub> and netPP<sub>MODIS</sub> divided by netPP<sub>MODIS. 

$\Large\Delta^{rel} = \frac{netPP_{VIIRS} - netPP_{MODIS}}{netPP_{MODIS}}\$  

The result will be a 120-month (10-year, from 2013-2022) mean monthly timeseries of &Delta;<sub>rel</sub> within your area of interest. Normalizing by netPP<sub>MODIS</sub> allows to user to evaluate the degree to which a downstream application may be impacted by a switch to the interim product.

### [Linear regression of netPP<sub>VIIRS</sub> vs. netPP<sub>MODIS</sub>](Tutorial1-basics)  
Calculate the mean values of the interim VIIRS netPP product (netPP<sub>VIIRS</sub>) and legacy MODIS netPP product (netPP<sub>MODIS</sub>) within a user-specified region for each month from 2013-2022. Use the resulting 120-month (10-year) mean monthly timeseries to run a linear regression for netPP<sub>VIIRS</sub> vs. netPP<sub>MODIS</sub>.  

## References  
Behrenfeld and Falkowski. (1997) Photosynthetic rates derived from satellite-based chlorophyll concentration Limnol. Oceanogr. 42:1-20. https://doi.org/10.4319/lo.1997.42.1.0001.

