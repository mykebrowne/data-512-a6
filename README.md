# data-512-a6

#### Repo for HCDS Final Project
This file describes the requirements and steps needed to re-produce an analysis of the relationship between: 
1. Opioid prescribing rate 
2. Opioid overdose rate 
3. Poverty rate 

in the US during 2006 to 2015.  

#### Software requirements 

- __[Jupyter notebook](http://jupyter.org/about.html)__ running an R kernel.  
- This can be done locally by __[installing](http://jupyter.org/install.html)__ Juypter notebook or, alternatively, on the Jupyter server. 
- If done locally, Python is a requirement (Python 3.3 or greater, or Python 2.7) for installing Jupyter. 


#### Licensing 

- Jupyter/jupyter is licensed under the __[BSD 3-clause "New" or "Revised" License](https://github.com/jupyter/jupyter/blob/master/LICENSE)__. 
- R as a package is licensed under GPL-2 | GPL-3. 
- Python 2.2 and above are licensed as per https://docs.python.org/3/license.html
- Opioid prescribing data can be found at the __[CDC website](https://www.cdc.gov/drugoverdose/maps/rxstate2006.html)__
- Opioid overdose data can be accessed via the __[CDC WONDER database](https://wonder.cdc.gov/mcd-icd10.html)__ 
- Poverty data can be access at the __[US Census Bureau](https://factfinder.census.gov/faces/tableservices/jsf/pages/productview.xhtml?pid=ACS_16_1YR_S1701&prodType=table)__

CDC and US Census Bureau data are licensed under CC0 1.0 Universal. 


#### Data files 

There are three sets of data files used in this project: 

1. __[prescribing_rate.csv](https://github.com/mykebrowne/data-512-a6/blob/master/prescribing_rate.csv)__ which details the number of opioid prescriptions per 100 resident population at a state level during 2006 to 2015. 

2. __[Overdose_2006.txt](https://github.com/mykebrowne/data-512-a6/blob/master/Overdose_2006.txt)__ which details the number of opioid overdose deaths at a state level during 2006.  

__[Overdose_2006.txt](https://github.com/mykebrowne/data-512-a6/blob/master/Overdose_2007.txt)__ which details the number of opioid overdose deaths at a state level during 2007. 

etc. 

3. __[ACS_06_EST_S1701.csv](https://github.com/mykebrowne/data-512-a6/blob/master/ACS_06_EST_S1701.csv)__ which details the number of residents below the poverty threshold at a state level during 2006. 

__[ACS_07_1YR_S1701.csv](https://github.com/mykebrowne/data-512-a6/blob/master/ACS_07_1YR_S1701.csv)__ which details the number of residents below the poverty threshold at a state level during 2007. 

etc. 


#### Steps to reproduce analysis 

This __[Jupyter notebook](https://github.com/mykebrowne/data-512-a6/blob/master/hcds-a6-final-project-report.ipynb)__ contains the steps and code needed to reproduce this analysis.  


#### Abstract 
