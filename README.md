# US Hate Crime Analysis

1. [Background](#background)
2. [Inspiration](#inspiration)
3. [Methodologies](#methodologies)
    - [Data Gathering](#data-gathering)
    - [Data Exploration](#data-exploration)
    - [Data Pre-processing](#data-pre-processing)
    
<a name='background'></a>
## Background

<a name='inspiration'></a>
## Analysis Question

1. How US hate crime trends in 2010 to 2018?
2. What biases that used for most of the cases?
3. What are the usual criminal acts commited on US hate crime?

<a name='methodologies'></a>
## Methodologies

This analysis will be using three tools:
1. **Python 3.7 in Jupyter Notebook**, for data gathering and preprocessing.
2. **Excel 365**, for data visualization.
3. **Powerpoint 365**, for data analysis report poster.

<a name='data-gathering'></a>
### Data Gathering

Data obtained from [United States Hate Crimes (1991-2018)](https://www.kaggle.com/louissebye/united-states-hate-crimes-19912017) that preprocessed and posted by [Louisse Bye](https://www.kaggle.com/louissebye). Data gathered from [FBI: Crime Data Explorer](https://crime-data-explorer.fr.cloud.gov/downloads-and-docs). This data consist of several files:

|File Name|Description|
|:---|:---|
|HC Readme.docx|Provide further information about technical definitions used in dataset|
|NIBRS_DataDictionary.pdf|Data dictionary to provide definitions/information|
|hate_crime.csv|the data|

<a name='data-exploration'></a>
### Data Exploration

1. **Multi-Value Columns Exploration**
<br>Some columns in HateCrimeTable (hate_crime.csv) have multiple value. These columns are 'OFFENSE_NAME, 'LOCATION_NAME', and 'BIAS_DESC'. These multi-value columns need to be parsed and convert to another table. Another way to improve readability is to cluster each category in multi-value columns. The clustering will use external information as references and will be done manually. Both method will make visualization easier and data more representable.

<a name='data-pre-processing'></a>
### Data Pre-processing

1. **Cleaning Data**
<br>This analysis will only using reported incident from 2010 to 2018. Some listed state won't be included too (Guam, Hawaii, and Federal) for the sake of better map visualization.

2. **Clustering Each Category in Multi-Value Columns**
<br>Category-Cluster mapping can be seen in this file. Cluster will be used to reduce variety of category. This will make vizualiation more readable.

3. **Parse Multi-Value Columns**
<br>Multi-value column will be normalized by creating another table.

4. **Rename, Rearangge and Convert DataFrame to .csv**
<br>Further analysis will be done on Excel. csv format is choos because it easier to processed.
