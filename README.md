# Exercise
This is an exercise that contains several tasks related to manipulating and combining various spatially explicit datasets into indicators of 
environmental impacts associated to land use activities and their application to agriculture and the nitrogen cycle.

# Software dependencies
Entire exercise is produced on Windows 10 Enterprise operating system and in QGIS (3.36.1-Maidenhead) Software. For bar plot visualisation R software (R version 4.3.1) is used. 
For calculation of _N inputs_ and _N surplus_ Microsoft Excel (Version 2403 Build 16.0.17425.20236) is used.

# Instructions on how to reproduce the results
Instructions are structured by the questions.

All the products of the exercises can be found here: https://1drv.ms/f/s!Ai7i64gE7uQqgf9iduMaQrU0yHvb2g

Products are: raster and vectors files, QGIS map templates, csv files, PDF plot, 2 global maps and R script for visualising bar plot. 

**Processing tools used in QGIS software:** Fix geometries, Dissolve, Raster Calculator, Zonal Statistics

**Question 1)**
Using the tool Raster calculator rasters of estimated yield and harvested area for 2005 were multiplied to obtain the global wheat production. 
To obtain the production in Mt (million tons) the obtained wheat production raster is multiplied with 10^-9. Raster is exported as tif format. 
Global map of wheat production is produced in the QGIS Map Print Layout.

**Question 2)**
Firstly, I fixed the geometries of GAUL 2 shapefile and then I dissolved it by the ADM0_Code column in the attribute table of the shapefile. Then, I used Zonal Statistics tool,
and specifically for the statistics to calculate I choose sum, input raster was the production raster obtained from the Question 1) and for the vector layer input dissolved shapefile
is used which now contains only GAUL 0. Product is exported as cvs.

**Question 3)**
N output in the harvested yield raster was calculated by multiplying raster of wheat production with the 0.02 in Raster calculator. Raster is exported in tif format.
Global map of N output in the harvested yield is produced in the QGIS Map Print Layout. 

**Question 4)**

**4a** To estimate the country-level values of N output in harvested wheat for the 10 biggest wheat producers again I used Zonal Statistics tool,
and specifically for the statistics to calculate I choose sum, input raster was the N output in the harvested yield raster obtained from the Question 2) 
and for the vector layer input dissolved shapefile is used which now contains only GAUL 0. With that I had all the neccessary numbers to calculate total N inputs and N surplus.
They were calculated as follows: 

_N inputs = N output / NUE_

_N surplus = N input - N output_

**4b** Visualisation for the N outputs and losses for the 10 countries that are the biggest wheat producers is done in R and using bar plot and exported as pdf. 

**4c** From the illustration it is visible that Central-East Asia (China, India and Pakistan) have high N losses and low NUE, and China and India are 2 biggest wheat producers. 
On the contrary, France has an NUE of almost 75% and the highest of all 10 producers. NUE of Germany, Canada, USA and Australia amounts to approximatelly 50%.

**Question 5)**

From my understanding this analysis can be really of use in different areas and first
and foremost to understand what is happening on the national levels, what can be the reasons for the numbers, and it can be interesting to delve into it because
it is always a involvement of several factors, such as environmental, socio-economic etc. Maybe units in which we decide to report are potential limitation, 
when we lose the small places because of the focus on biggest producers, maybe models will not capture the full picture because of the analysis. This is also maybe 
just one part of the N cycle.

**Question 6)**
Issue and assumptions: 

-Geometry issues with GAUL 2 shapefile

-Reporting in Mt units, I had doubts whether to continue to report in this unit when it came to the Question 3) and calculating N outputs in harvested yield

-Calculation of the N output in the harvested yield since it is written using the wheat production from the output of Question 1) so my assumption was to multiply 0.02
with the prodution obtained in Mt. 


















