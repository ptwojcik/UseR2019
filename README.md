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

## Presentation from UseR! 2019 (lightning talk)

## Extended materials



## Author: Piotr Wójcik

* [assistant professor at the University of Warsaw, Faculty of Economic Sciences (FES UW)](http://coin.wne.uw.edu.pl/pwojcik/)
* founder and head of [Data Science Lab](http://dslab.wne.uw.edu.pl) at FES UW
* expert in the use of R and SAS software for data processing and advanced modeling
* initiator, head and lecturer in post-graduate studies "Data Science in business applications. Workshops using the R software" (in Polish): [http://datascience.wne.uw.edu.pl](http://datascience.wne.uw.edu.pl)
* many years of professional experience of a quantitative analyst in the financial, telecommunications and marketing research sector

## Intensity of night-time lights -- data

* NTLI data is based on **satellite images** collected and processed by the National Oceanic and Athmosferic Administration (NOAA)
* **NOAA** provides two types of data:
    * [Version 4 DMSP-OLS](https://ngdc.noaa.gov/eog/dmsp/downloadV4composites.html) -- average annual data for the period 1992--2013
    * [Version 1 VIIRS](https://www.ngdc.noaa.gov/eog/viirs/download_dnb_composites.html) -- monthly data since April 2012 and averaged annual (only 2015 and 2016)
* night-time lights intensity (**NTLI**) is measured for pixels with the size of 30×30 (DMSP-OLS) or 15x15 (VIIRS) arc seconds
* it relates to **less than $1~km^2$** on the equator (about $0.5~km^2$ in Europe)
* for each pixel NTLI data is provided in *digital numbers* (**DN**) on the scale 0--63 (DMSP-OLS) or 0--16384 (VIIRS)
* NTLI data can be **agregated** to the level of any territorial units

## Limitations of NTLI data

* **limitation of the measurement scale** for DMSP-OLS -- impossible to distinguish between the intensity of light in city centers and the periphery
* VIIRS data available for a relatively short period
* measurements from different years / satellites / types of NTLI data are not directly comparable
