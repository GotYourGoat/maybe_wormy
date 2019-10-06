# Exploring potential susceptibility to soil transmitted helminths
This project is being developed to conduct a preliminary analyses and develop models of the potential susceptibility of the Southern US to soil transmitted helminths (STHs). This is a work-in-progress expansion and refinement of my Advanced GIS capstone project where my focus was on developing a spatial model for Georgia’s potential susceptibility to STHs based on environmental and socioeconomic characteristics in the region.

## General Info/ Intro
This project is intended to explore the factors that relate to the potential susceptibility of a geographical region to hookworm/other intestinal parasite infection. It thus far incorporates soil data describing the soil's susceptibility to pollution (acquired from Georgia's WelSTROM project) and ACS 2017 5-year estimate data by census tract.

The use of GIS allows the creation of a spatial model of the areas where multiple factors (such as high poverty rate, high risk soil) are present, to determine where further investigation may be especially warranted.

## Status-
### GIS - in progress
GeorgiaMapping19_v1.mxd: the initial version of spatial join of soil and ACS layers with weighting. Can modify, add/remove layer and weightings. After the development of my initial model, I believe greater weight should have been given to soil characteristics.
- **Correct for educational attainment:** the education parameter used in the initial model looked at only HS graduation, but that gives an inaccurate picture. The data collection had discrete categories for:
 - High school Graduate (includes equivalency)
 - Some college no degree
 - Associate's degree
 - Bachelor's degree
 - Graduate or professional degree

- Currently refining and revising the approach taken during the development of my model of Georgia.
- Developing models with different thresholds in visualization.

GIS analyses - future
- If possible: Incorporate elevation and or flood models if they can be found at an appropriate scale.
- Expand to look at other environmental factors that may impact health in the region, such as large scale agriculture, brownsites, etc

### Website - in progress, not yet published
- This site has resources, history on hookworm and other related issues, current efforts, etc. It is intended to act as a collection of resources and avenues through which people can learn more, both about the history and current efforts taking place.
 - Looks at global impact, biology, history, economics of STHs
 - Provides information about current initiatives in the US to bring awareness and address factors that contribute to the susceptibility to STHs and other pathogens borne from poverty and unsanitary conditions.

### Python/jupyter notebooks - in progress
Uploaded files
- Revisit user prompts and docstrings.
- Add a .py version.
Add files that allow ways to visualize and explore the dat

## Technologies
Python 3.7
Jupyter notebook 5.7
Packages: Numpy, Pandas, Matplotlib, Seaborn

ArcGIS


## Features
Currently available:
### Jupyter
The jupyter notebooks uploaded are meant to allow the data from states’ census data to be processed and to perform exploratory analyses based on user-specified parameters.

*Note: This initial iteration has developed with the ACS 2017 5-year estimate data for Georgia, and has not been tested on other datasets.*

- fileCleaning_userfriendly.ipynb - a jupyter notebook for processing ACS data, intended to require limited understanding of programming.
- dataViz_2dist.ipynb - to allow users to perform basic visualizations of the data input, intended to require limited understanding of programming.

Coming Soon:
- Way to weight the files with shared census tracts (not including soil) outside of arcGIS
- GIS spatial analyses - in the process of reviewing and revising the models developed using ArcGIS during the initial project



## Screenshots/ Examples of project outputs

### Jupyter Notebooks
If using as-is, printed output/dialogs are used and user input required.
If you are using ACS data, be sure to remove/exclude the descriptive row when trying to perfom any calculations on the datasets, as it will otherwise cause errors due to multiple dataTypes

Example of dialog and output of dataViz_2dist.ipynb
![Example dialog of ...](https://github.com/kgmcdaid/maybe_wormy/blob/master/povPlotDialog.png)

![Example output of the ](https://github.com/kgmcdaid/maybe_wormy/blob/master/povPlot.png)

### ArcGIS -
Format: mxd file
- Spatially join the weighted ACS datasets to the weighted soil data.

Files used:
- [Soil data](https://www.welstrom.com/welstrom/rest/services/drastic_hydric_soils/MapServer) - available on Georgia’s WelSTROM site
- Poverty data (ACS 2017 5-year estimates)
- Plumbing data (ACS 2017 5-year estimates)
- Education data (ACS 2017 5-year estimates)
- CountyLines (not required for analysis)


Percent poverty layer

Image of the soil layer in arcGIS:
![Soil](https://github.com/kgmcdaid/maybe_wormy/blob/master/smaller_soils.png)



Image of the model created, where the index values are at at least 50% of the total possible index score.
This model used percentages, rather than percentiles in the rankings of Education (1-Highschool Graduate), Plumbing (Percent Incomplete Plumbing), Poverty(Percent Poverty).

The rankings were:
- Poverty (%Poverty):
 - min(0.5)-10: 1
 - 10-20.0: 2
 - 20-40.0: 4
 - 40-60.0: 8
 - 60-max(88.6): 10
- Education (1-HS)* note, the weighting is inaccurate for this, as HS attainment does not include anyone with education beyond HS.
 - min(22)-50: 5
 - 51-60: 4
 - 61-70: 3
 - 71-80: 2
 - 81-max(93): 1
- Percent Incomplete Plumbing:
 - 0-5: 1
 - 5-10: 2
 - 10-15: 6
 - 15-20: 8
 - 20-30.4: 10
- Soil DRASTIC score:
 - LOW: 1
 - AVERAGE: 5
 - HIGH: 10


![50_70_S15Mod2](https://github.com/kgmcdaid/maybe_wormy/blob/master/50_70_breaks_small.png)




## Setup
### Python , Jupyter Notebook

### ArcGIS
You can get access to arcGIS through subscription, but also when you sign up for one of their MOOCs or use a free trial.
There are other softwares available for GIS, including Carto (also proprietary) and QGIS (open source).


## Reason for the project
This is an area of research with limited exploration or funding in the past several decades. However, recent research provides some evidence for a renewed need for awareness about the parasites in parts of the U.S.
 - A study in Lowndes county Alabama by researchers from Baylor College of Medicine found that over 34% of the participants were infected with hookworms (McKenna et. al).
 - A study from 2008 there are 68,000 to 110,000 Appalachians infected with S. stercoralis (another STH) (Hotez 2008).

Little is known about the current prevalence of STHs in the region, but the “socioeconomic and environmental conditions may remain conducive to ongoing infection” (Starr & Montgomery 2011).
But with the decades of limited monitoring, accurate data remains scarce. This lack of monitoring, paired with the continued extreme poverty in parts of the United States, and regions in the having soil ill-suited for traditional septic systems makes the awareness of the issue all-too lacking.


For further studies, see below in Resources.
## Credits:
@sebowman - for the python-related parts of the project, provided feedback and input on code styling, user testing, specializing code for the desired audience, and more.

Barry Nickel at UCSC's [cisr lab](http://spatial.cisr.ucsc.edu/) for instruction in GIS and advice on the initial capstone project's scope and providing assistance in acquiring the shapefiles and layers used in the models.

## Resources
### Studies
NPR wrote a piece on the study by Baylor researchers and the findings of the UN Special Rapporteur, found [here](https://www.npr.org/sections/goatsandsoda/2017/12/12/570217635/the-u-n-looks-at-extreme-poverty-in-the-u-s-from-alabama-to-california)

McKenna, M. L., McAtee, S., Bryan, P. E., Jeun, R., Ward, T., Kraus, J., … Mejia, R. (2017).[Human Intestinal Parasite Burden and Poor Sanitation in Rural Alabama](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5817782/). The American journal of tropical medicine and hygiene, 97(5), 1623–1628. doi:10.4269/ajtmh.17-0396

Brooker, S., Bethony, J., & Hotez, P. J. (2004). [Human hookworm infection in the 21st century](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC2268732/). Advances in parasitology, 58, 197–288. doi:10.1016/S0065-308X(04)58004-1

Brooker, S., Clements, A. C., & Bundy, D. A. (2006). [Global epidemiology, ecology and control of soil-transmitted helminth infections.](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC1976253/) Advances in parasitology, 62, 221–261. doi:10.1016/S0065-308X(05)62007-6

Starr, M. C., & Montgomery, S. P. (2011). [Soil-transmitted Helminthiasis in the United States: a systematic review](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3183777/)--1940-2010. The American journal of tropical medicine and hygiene, 85(4), 680–684. doi:10.4269/ajtmh.2011.11-0214

[Topography of Poverty in the United States...](https://www.cdc.gov/pcd/issues/2007/oct/07_0091.htm)

### Writing a readme:
https://bulldogjob.com/news/449-how-to-write-a-good-readme-for-your-github-pr
https://github.com/ritaly/README-cheatsheet/blob/master/README.md



## Contact
Website url, tbd...
