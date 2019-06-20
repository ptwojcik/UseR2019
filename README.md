# Measuring inequalities from space. Analysis of satellite raster images with R

## Abstract

Data on night-time light intensity is increasingly used by social science researchers as a proxy for economic development. Calculated from weather  
satellite recordings, it provides annual data for the whole globe in gridded format with pixels covering less than one square kilometer. This allows researchers 
to aggregate these data at the level of subnational units and analyze it together with other socio-economic indicators. Satellite images are freely available as 
large raster files. 

The aim of this presentation is to show how to analyze these data step by step in R – starting from importing the data to R, then correctly 
imposing a map of a selected area (e.g. shapefile) on the raster object, limiting the satellite image to the selected spatial extent and finally aggregating 
the data for the analyzed territorial units and visualizing the result. 

In addition, correlation between night-time light intensity and selected socio-economic indicators (e.g. population, GDP) will be analyzed for world countries, US states and 
UE regions (NUTS2 and NUTS3). 

## R packages

dplyr, sf, raster, ggplot2, leaflet, WDI, eurostat
