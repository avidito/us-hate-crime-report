<a name='top'></a>
# US Hate Crime Analysis

## Table of Contents
1. [Background](#background)
2. [Inspiration](#inspiration)
3. [Methodologies](#methodologies)
    - [Data Extraction](#data-extraction)
    - [Data Exploration](#data-exploration)
    - [Data Preprocessing](#data-preprocessing)
    - [Data Visualization](#data-visualization)
4. [Poster](#poster)

<a name='background'></a>
## Background
[`^ back to top`](#top)

[**Hate crime**](https://en.wikipedia.org/wiki/Hate_crime), also known as bias-motivated crime, is a crime motivated by prejudice or intolerance toward an individual's membership (or perceived membership) to a  group. For example, one of the victims of hate-crime was attacked for having dark color skin. Unfortunately, this kind of crime slowly became an everyday thing. Discrimination and racism keep increasing even though the majority of the public is protesting against these constantly. This analysis project will show some of the hate-crime characteristics in the US from 2010 to 2018. The US was chosen because the US government open the reported hate crimes incident to the public. The sources of data are mention below.

<a name='inspiration'></a>
## Inspiration
[`^ back to top`](#top)

1. How US hate crime trends in 2010 to 2018?
2. What are the biases that used in US hate crime incidents?
3. What are the criminal acts committed in US hate crime incidents?

<a name='methodologies'></a>
## Methodologies
[`^ back to top`](#top)

This analysis consist of several steps:

<br>![methodologies](https://github.com/avidito/us-hate-crime-report/blob/master/images/methodologies.png)<br>

This analysis will be using three tools:
1. **Python 3.7 in Jupyter Notebook (Anaconda)**, for data extraction and preprocessing.
2. **Excel 365**, for data visualization.
3. **Powerpoint 365**, for creating the report poster.

<a name='data-extraction'></a>
### I. Data Extraction
[`^ back to top`](#top)

Raw data can be gathered from [FBI: Crime Data Explorer](https://crime-data-explorer.fr.cloud.gov/downloads-and-docs). In this analysis, I use preprocessed data 
Data obtained from [United States Hate Crimes (1991-2018)](https://www.kaggle.com/louissebye/united-states-hate-crimes-19912017) that preprocessed and posted by [Louisse Bye](https://www.kaggle.com/louissebye). This data consist of several files:

|File Name|Description|
|:---|:---|
|hate_crime.csv|Tabular data about each reported hate crime incidents|
|HC Readme.docx|Provide further information about technical definitions used in dataset|
|NIBRS_DataDictionary.pdf|Data dictionary to provide definitions/information|

<a name='data-exploration'></a>
### II. Data Exploration
[`^ back to top`](#)

<<<<<<< HEAD
**HateCrimeTable (hate_crime.csv)** consist of **201.403 rows** and **28 columns**. Below is the list of HateCrimeTable columns and its value type.
|Column|Type|
|---|---|
|INCIDENT_ID|int64|
|DATA_YEAR|int64|
|ORI|object|
|PUB_AGENCY_NAME|object|
|PUB_AGENCY_UNIT|object|
|AGENCY_TYPE_NAME|object|
|STATE_ABBR|object|
|STATE_NAME|object|
|DIVISION_NAME|object|
|REGION_NAME|object|
|POPULATION_GROUP_CODE|object|
|POPULATION_GROUP_DESC|object|
|INCIDENT_DATE|object|
|ADULT_VICTIM_COUNT|float64|
|JUVENILE_VICTIM_COUNT|float64|
|TOTAL_OFFENDER_COUNT|int64|
|ADULT_OFFENDER_COUNT|float64|
|JUVENILE_OFFENDER_COUNT|float64|
|OFFENDER_RACE|object|
|OFFENDER_ETHNICITY|object|
|VICTIM_COUNT|int64|
|OFFENSE_NAME|object|
|TOTAL_INDIVIDUAL_VICTIMS|float64|
|LOCATION_NAME|object|
|BIAS_DESC|object|
|VICTIM_TYPES|object|
|MULTIPLE_OFFENSE|object|
|MULTIPLE_BIAS|object|

This report will only use columns that provide information to answer the quesitions from Inspiration section. These columns are:
|Column|Type|
|---|---|
|INCIDENT_ID|int64|
|DATA_YEAR|int64|
|STATE_NAME|object|
|REGION_NAME|object|
|OFFENSE_NAME|object|
|LOCATION_NAME|object|
|BIAS_DESC|object|

Below is one of the sample of data in HateCrimeTable.
|Column|Value|
|---|---|
|INCIDENT_ID|44|
|DATA_YEAR|1991|
|STATE_NAME|Arkansas|
|REGION_NAME|South|
|OFFENSE_NAME|Aggravated Assault;Destruction/Damage/Vandalism of Property|
|LOCATION_NAME|Highway/Road/Alley/Street/Sidewalk|
|BIAS_DESC|Anti-White|

#### Findings
**1. Multi-Values Columns**

Several column can have more than one value (multi-value columns). These columns are:
- **OFFENSE_NAME**
- **LOCATION_NAME**
- **BIAS_DESC**

The reason these columns can have multiple categories are some incident can't be categorized with only one category. For example, if the offender destroy victim's property and also harrassing them, the offender can be judged for two crimes but still in one incident. The offender can also "hate" more than one bias that victim's have. Some incident's location sometimes categorized as more than one category, or happen in several location.

Multi-values columns must be processed before it can be visualized. In this report, the multi-values columns will handled by creating new table for each columns. This approach can make reporting process easier.

**2. Too Many Categories**

Below is the frequency table for multi-values columns:

|Columns|Total Categories|
|---|---|

There are a lot of categories in each multi-values columns. To many categories will reduce readability of the report. To handle this problem, each column will be clustered. he clustering will use external information as references and will be done manually.

<a name='data-preprocessing'></a>
### III. Data Pre-processing
[`^ back to top`](#top)

**1. Cleaning Data**

This analysis will only using reported incident from 2010 to 2018. Following states won't be included:
- Guam
- Hawaii
- Federal

The reason is their location are hard to visualize with Excel Map Charts.
Total Rows: 57758 (28.68% of the total data)

**2. Parse Multi-Value Columns**

Multi-value column will be normalized by creating another table. Data diagram for this implementation are shown as follow:

<br>![data-diagram](https://github.com/avidito/us-hate-crime-report/blob/master/images/data_diagram.png)<br>

**3. Clustering Categories in Multi-Value Columns**

Category-Cluster mapping can be seen in this [file](https://github.com/avidito/us-hate-crime-report/blob/master/visualization.xlsx). Clustering will be used to reduce variety of category. The clustering uses information from many sources as references and will be done manually.

**4. Rename, Rearangge and Convert DataFrame to .csv**

This final step intends to make the data easier to analyze. Further analysis will be done on Excel.

<a name='data-visualization'></a>
### IV. Data Visualization
[`^ back to top`](#top)

There are two visualization from these data: (1) [dashboard](https://github.com/avidito/us-hate-crime-report/blob/master/visualization.xlsx); and (2) poster ([ori](https://github.com/avidito/us-hate-crime-report/blob/master/media/poster.png); [mini](https://github.com/avidito/us-hate-crime-report/blob/master/media/poster_mini.png)). 

<a name='poster'></a>
## Poster
[`^ back to top`](#top)

![poster](https://github.com/avidito/us-hate-crime-report/blob/master/images/poster_mini.png)
