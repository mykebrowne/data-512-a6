# data-512-a6

#### Repo for HCDS Final Project
This file describes the requirements and steps needed to re-produce an analysis of the relationship between opioid prescribing rate, opioid overdose rate and poverty rate in the US during 2006 to 2015.  

#### Software requirements 

- __[Jupyter notebook](http://jupyter.org/about.html)__ running an R kernel.  
- This can be done locally by __[installing](http://jupyter.org/install.html)__ Juypter notebook or, alternatively, on the Jupyter server. 
- If done locally, Python is a requirement (Python 3.3 or greater, or Python 2.7) for installing Jupyter. 


#### Licensing 

- Jupyter/jupyter is licensed under the __[BSD 3-clause "New" or "Revised" License](https://github.com/jupyter/jupyter/blob/master/LICENSE)__. 
- R as a package is licensed under GPL-2 | GPL-3. 
- Python 2.2 and above are licensed as per https://docs.python.org/3/license.html
- Opioid prescribing rates can be found at the __CDC website(         )__

Content accessed through the __[Wikimedia Rest API](https://en.wikipedia.org/api/rest_v1/)__ is licensed under the CC-BY-SA 3.0 and GFDL licenses. 
- Use of the Wikimedia Rest API is under the __[Wikimedia Terms of Use](https://wikimediafoundation.org/wiki/Terms_of_Use/en)__.
- Population data is provided by __[Population Reference Bureau](http://www.prb.org/DataFinder/Topic/Rankings.aspx?ind=14)__.
- Data concerning __[English Wikipedia articles on politicians by country](https://figshare.com/articles/Untitled_Item/5513449)__ are licensed under CC-BY-SA 4.0.


#### API documentation for ORES 

The ORES (Objective Revision Evaluation Services) __[API](https://ores.wikimedia.org/v3/#/scoring)__ has an end-point which, for a given: <br> 

- Context (the name of the Wikipedia project, in this case 'enwiki' for English language Wikipedia)
- Revision id (the id given to the last edit of a particular Wikipedia article)
- Model (scoring model - in this context wp10)

returns a JSON object with a key-value pair "prediction" and one of six quality values. <br>  

For example: https://ores.wikimedia.org/v3/scores/enwiki/235107991/wp10 returns prediction:  "Stub" 


#### Data file 

The __[data file](https://github.com/mykebrowne/data-512-a2/blob/master/page_quality_population.csv)__ created as part of this project has the following columns: <br> 

- country (character) 
- article_name (character) - the name of the English language Wikipedia article  
- revision_id (integer) - the id given to the last edit of the Wikipedia article 
- article_quality (character) - the quality of the article as predicted by ORES 
- population (integer) - the Mid-2015 population of the country <br> 

Please note that this list only includes arcticles from countries which are listed in the __[Mid-2015 population](http://www.prb.org/DataFinder/Topic/Rankings.aspx?ind=14)__ file from the Population Reference Bureau __and__ which have predicted scores from ORES. 


#### Steps to reproduce analysis 

This __[Jupyter notebook](https://github.com/mykebrowne/data-512-a2/blob/master/hcds-a2-bias.ipynb)__ contains the steps and code needed to reproduce this analysis.  


#### Reflection: Bias in data 
This exercise illustrated how bias can arise in data science projects both intentionally and unintentionally.  First, bias can arise due to the nature of the data itself.  For example, by using English language Wikipedia as the source for articles on politicians there is likely to be over-representation of articles from English speaking countries.  It is not unreasonable to think that by using Chinese language Wikipedia, for example, you might see a greater number of articles on Chinese politicians.  

Second, bias can be introduced through the way in which concepts in the underlying research question are operationalized.  In this example, the research seeks to understand the ways in which the coverage of politicians and the quality of this coverage varies across country.  Coverage and quality are qualitative terms which have been operationalized in specific, quantitative ways in order to facilitate analysis.  Coverage has been defined as the number of politician articles per population and quality defined as the proportion of articles which have been labelled 'Featured Article' or 'Good article' by the ORES algorithm.   These definitions, whilst sensible and defensible, are essentially arbitrary and therefore open to critical examination.  One obvious drawback from using articles per population as a measure of coverage is that it tends to privilege countries with small populations at the expense of countries with large populations.  This is evident from the list of top 10 countries by coverage which are exclusively micro-states; in contrast to the bottom 10 countries which include three of the top five most populous countries.   This definition inevitably constrains the usefulness of such a measure and highlights the importance of understanding the context in which research is being undertaken and the decisions that may be taken on its basis.    

Bias can also be introduced through methodological choices such as how to treat missing data.  In this example, articles which cannot be scored by ORES or which are from countries not listed in the Population Reference Bureau dataset are excluded.  As one of our colleagues pointed out on Slack this impacts countries including South Africa, South Korea and East Timor. 
