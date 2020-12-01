# US Hate Crime Analysis

[Background](#background) | [Inspiration](#inspiration) | [Methodologies](#methodologies) | [Data Gathering](#data-gathering) | [Data Exploration](#data-exploration) | [Data Pre-processing](#data-pre-processing) | [Poster](#poster) |
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
    
<a name='background'></a>
## Background
[`^ back to top`](#)

[**Hate crime**](https://en.wikipedia.org/wiki/Hate_crime), or also known as bias motivated crime, is a crime motivated by prejudice or intolerance toward an individual’s membership (or perceived membership) to a certain group. For example, some reported hate crime victim are assaulted just because his skin color is black. Unfortunately this kind of crime slowly became common things. Discrimantion keep increasing even when the majority of society constantly protest againts these. This analysis will create simple vizualitation about hate crime characteristics in US from 2010-2018. The result can be used for another country if the data is available. 

<a name='inspiration'></a>
## Inspiration
[`^ back to top`](#)

1. How US hate crime trends in 2010 to 2018?
2. What biases that used for most of the cases?
3. What are the usual criminal acts commited on US hate crime?

<a name='methodologies'></a>
## Methodologies
[`^ back to top`](#)

This analysis will be using three tools:
1. **Python 3.7 in Jupyter Notebook**, for data gathering and preprocessing.
2. **Excel 365**, for data visualization.
3. **Powerpoint 365**, for data analysis report poster.

<a name='data-gathering'></a>
### I. Data Gathering
[`^ back to top`](#)

Data obtained from [United States Hate Crimes (1991-2018)](https://www.kaggle.com/louissebye/united-states-hate-crimes-19912017) that preprocessed and posted by [Louisse Bye](https://www.kaggle.com/louissebye). Data gathered from [FBI: Crime Data Explorer](https://crime-data-explorer.fr.cloud.gov/downloads-and-docs). This data consist of several files:

|File Name|Description|
|:---|:---|
|hate_crime.csv|tabular data about each reported hate crime incidents|
|HC Readme.docx|Provide further information about technical definitions used in dataset|
|NIBRS_DataDictionary.pdf|Data dictionary to provide definitions/information|

<a name='data-exploration'></a>
### II. Data Exploration
[`^ back to top`](#)

1. **Multi-Value Columns Exploration**
<br>Some columns in HateCrimeTable (hate_crime.csv) have multiple value. These columns are 'OFFENSE_NAME, 'LOCATION_NAME', and 'BIAS_DESC'. These multi-value columns need to be parsed and convert to another table. Another way to improve readability is to cluster each category in multi-value columns. The clustering will use external information as references and will be done manually. Both method will make visualization easier and data more representable.
<br><br>![multi-value-column-example](https://github.com/avidito/us-hate-crime-report/blob/master/media/multi_value_example.png)
<br><pre>Example of Column with Multiple Value</pre>

<a name='data-pre-processing'></a>
### III. Data Pre-processing
[`^ back to top`](#)

1. **Cleaning Data**
<br>This analysis will only using reported incident from 2010 to 2018. Some listed state won't be included too (Guam, Hawaii, and Federal) for the sake of better map visualization.

2. **Clustering Each Category in Multi-Value Columns**
<br>Category-Cluster mapping can be seen in this file. Cluster will be used to reduce variety of category. This will make vizualiation more readable. Cluster information are shown in [visualization document](https://github.com/avidito/us-hate-crime-report/blob/master/visualization.xlsx).

3. **Parse Multi-Value Columns**
<br>Multi-value column will be normalized by creating another table. Each table connected with certain connection, describe by data diagram as follow,
<br><br>![data-diagram](https://github.com/avidito/us-hate-crime-report/blob/master/media/data_diagram.png)
<br><pre>                      Data Diagram</pre>

4. **Rename, Rearangge and Convert DataFrame to .csv**
<br>Further analysis will be done on Excel. csv format is choos because it easier to processed.

### IV. Visualization
<br>From the data, two kind of visualization are created: (1) [dashboard](https://github.com/avidito/us-hate-crime-report/blob/master/visualization.xlsx); and (2) poster ([ori](https://github.com/avidito/us-hate-crime-report/blob/master/media/poster.png); [mini](https://github.com/avidito/us-hate-crime-report/blob/master/media/poster_mini.png)). 

<a name='poster'></a>
### Poster
[`^ back to top`](#)

![poster](https://github.com/avidito/us-hate-crime-report/blob/master/media/poster_mini.png)
