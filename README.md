# Project Title: COVID-19 Impacts on Business and Workforce Trends
***

[About](#about) | [Questions Analyzed](#questions-analyzed) | [Data Source](#data-source) | [Data Analysis Process](#data-analysis-process) | [Summary Findings](#summary-findings) | [Contributors](#contributors)


# About
***

COVID-19 has been one of the most unpredictable and transformative pandemics in recorded history. It's been overall so exhausting since most businesses could not sustain and many people lost their jobs. So, our team decided to study the overall impacts of this pandemic on various businesses and workforce trends in US. 

This project analyzes COVID-19-related business trends through detailed assessment of unemployment rates, economic fluctuations, and factors (e.g., demographics, travel, personal habits) that likely contribute to growth and/or contraction in US during the worldwide pandemic. Correlations and associations between various factors and increased downturn clearly point to certain consistent vulnerabilities.

# Questions Analyzed
***

COVID-19 Impacts and the Questions we wanted to analyze as part of this project:
* **Unemployment** - Which ethnic group, industrial group and group of states had the highest and lowest unemployment rates during the pandemic?
* **Businesses** - Which businesses benefitted or suffered the most due to COVID-19?
* **Airlines & Travel Routes** - Which airlines and travel routes were most affected during the pandemic?
* **Mobility Trends** - Is there any relationship between the Total COVID-19 cases and Mobility trends (population staying at home) in US?
* **Safest Travel Destination** In the current situation, which is the safest travel destination in US right now?

# Data Source
***

* **Unemployment**
    - [Unemployment Rates for various Races](https://beta.bls.gov/dataQuery/find?st=0&r=20&q=unemployment&more=0&fq=cg:[Unemployment+and+Labor+Force+Status])
    - [Unemployment Rates for various Industries](https://beta.bls.gov/dataQuery/find?st=0&r=20&q=unemployment&more=0&fq=cg:[Establishments%2FBusinesses%2FFirms])
    - [Unemployment Rates for all US States](https://beta.bls.gov/dataQuery/find?st=0&r=20&q=unemployment&more=0&fq=cg:[Geography])

* **Businesses**
    - [Jupyter Notebook Script](https://github.com/ushaakumaar/Python-Project-1/blob/main/business-stock-retrieval.ipynb) was written based on the python script available in [kaggle](https://www.kaggle.com/jacksoncrow/download-nasdaq-historical-data) to retrieve all NASDAQ traded stock prices on 2019/12/31(Pre COVID), 2020/03/31, 2020/06/30 and 2020/10/09 into a CSV file for further analysis.

* **Airlines & Travel Routes**
    - [US Airlines Flight Delays and Cancellations Data](https://www.kaggle.com/akulbahl/covid19-airline-flight-delays-and-cancellations)

* **Mobility Trends**
    - [US Mobility _(Population staying at home)_ Data](https://data.bts.gov/)
    - [US National Level COVID data](https://raw.githubusercontent.com/nytimes/covid-19-data/master/us.csv)

* **Safest Travel Destination**
    - [US County Level Population Data](https://www2.census.gov/programs-surveys/popest/tables/2010-2019/counties/totals/co-est2019-annres-06.xlsx)
    - [US County Level COVID data](https://github.com/nytimes/covid-19-data/blob/master/us-counties.csv)
    - [US County Level data for Mapping](https://raw.githubusercontent.com/plotly/datasets/master/geojson-counties-fips.json)


# Data Analysis Process
***
The project reads data from multiple data sources cited above, performs normalization and aggregations on top of it, and generates various plots/maps based on the data to analyze and find useful insights to answer the questions.

## Data Clean Up and Data Wrangling

Following data clean up and wrangling steps were performed wherever required and the Cleaned and Transformed data was used for the remaining steps.

* Data for cleaned up removing NaNs/duplicates
* Data was converted to appropriate data types
* Data from multiple sources were merged to one dataset that could be 

## Summary Statistics

* **Unemployment**
    - US States that were most affected (or) less affected due to the pandemic were chosen to generate the plot

* **Businesses**
    - Percentage of change in stock price for each time period being assessed was calculated
    - Top 10 and Bottom 10 performing businesses were determined

* **Airlines & Travel Routes**
    - Route that has maximum cancellations was determined
    - Route that has maximum delays was determined
    - Airlines that has maximum cancellations was determined
    - Airlines that has maximum delays was determined

* **Safest Travel Destination**
    - Top 15 Safest travel destinations at County Level in US was determined

## Data Visualization

* **Unemployment**
    - Generated a [line plot](https://github.com/ushaakumaar/Python-Project-1/blob/main/Images/state_lineplot.png) with Unemployment Rates for all US states
    - Generated a [line plot](https://github.com/ushaakumaar/Python-Project-1/blob/main/Images/states_interested_lineplot.png) with Unemployment Rates for all US states that were most affected (or) less affected due to the pandemic
    - Generated a [line plot](https://github.com/ushaakumaar/Python-Project-1/blob/main/Images/race_lineplot.png) with Unemployment Rates for various races
    - Generate a [line plot](https://github.com/ushaakumaar/Python-Project-1/blob/main/Images/industry_lineplot.png) with Unemployment Rates for 10 chosen industries
    
* **Businesses**
    - Generated a [line plot](https://github.com/ushaakumaar/Python-Project-1/blob/main/Images/top_10_business_lineplot.png) for top 10 performing businesses with Pre COVID, Mar 2020, June 2020 and Oct 2020 Profit % Changes
    - Generated a [bar plot](https://github.com/ushaakumaar/Python-Project-1/blob/main/Images/top_10_business_barplot.png) for top 10 performing businesses with Oct 2020 Profit % Changes
    - Generated a [line plot](https://github.com/ushaakumaar/Python-Project-1/blob/main/Images/bottom_10_business_lineplot.png) for bottom 10 performing businesses with Pre COVID, Mar 2020, June 2020 and Oct 2020 Profit % Changes
    - Generated a [bar plot](https://github.com/ushaakumaar/Python-Project-1/blob/main/Images/bottom_10_business_barplot.png) for bottom 10 performing businesses with Oct 2020 Profit % Changes

* **Airlines & Travel Routes**
    - Generated a [bar plot](https://github.com/ushaakumaar/Python-Project-1/blob/main/Images/route_cancellations_bar.png) with Total Cancellations per Routes (Top 15)
    - Generated a [bar plot](https://github.com/ushaakumaar/Python-Project-1/blob/main/Images/airlines_cancellations_bar.png) with Total Cancellations per Airlines

* **Mobility Trends**
    - Generated a [scatter plot](https://github.com/ushaakumaar/Python-Project-1/blob/main/Images/mobility_cases_scatterplot.png) with linear regression model to see if there is correlation between population staying at home and covid cases at national level.
    - Generated a [scatter plot](https://github.com/ushaakumaar/Python-Project-1/blob/main/Images/mobility_death_scatterplot.png) with linear regression model to see if there is correlation between population staying at home and covid deaths at national level.
    - Generated a [line plot](https://github.com/ushaakumaar/Python-Project-1/blob/main/Images/mobility_lineplot.png) to show the mobility and covid trend at national level

* **Safest Travel Destination**
    - Generated a [bar plot](https://github.com/ushaakumaar/Python-Project-1/blob/main/Images/population_diff_bar.png) showing the Percentage of Population difference between 2018 and 2019 at US County Level
    - Generated a [bar plot](https://github.com/ushaakumaar/Python-Project-1/blob/main/Images/top_15_safest_counties_bar.png) showing the Top 15 Safest Counties to Travel
    - Generated a Plotly Map showing the County level Covid Cases
    
## Data Analysis

Looked across all generated figures/tables/maps and wrote the observations or inferences that can be made from the data. Included these observations at the bottom of notebook for each question.

## Jupyter Notebook files for each Question

* **Unemployment**
    - [Race - Data Retrieval & Analysis Script](https://github.com/ushaakumaar/Python-Project-1/blob/main/Race%20Unemployment%20Rate%20Compared.ipynb)
    - [States - Data Retrieval & Analysis Script](https://github.com/ushaakumaar/Python-Project-1/blob/main/State%20Unemployment%20.ipynb)
    - [Industries - Data Retrieval & Analysis Script](https://github.com/ushaakumaar/Python-Project-1/blob/main/Industry%20Unemployment%20Rate.ipynb)
    
* **Businesses**
    - [Data Retrieval Script](https://github.com/ushaakumaar/Python-Project-1/blob/main/business-stock-retrieval.ipynb)
    - [Data Analysis Script](https://github.com/ushaakumaar/Python-Project-1/blob/main/business-profit-loss.ipynb)

* **Airlines & Travel Routes**
    - [Data Retrieval & Analysis Script](https://github.com/ushaakumaar/Python-Project-1/blob/main/airlines.ipynb)

* **Mobility Trends**
    - [Data Retrieval & Analysis Script](https://github.com/ushaakumaar/Python-Project-1/blob/main/Mobility.ipynb)

* **Safest Travel Destination**
    - [Data Retrieval & Analysis Script](https://github.com/ushaakumaar/Python-Project-1/blob/main/safest-travel-route.ipynb)

# Summary Findings
***

Overall Analysis for all the questions in the project are summarized in [Summary Findings Jupyter Notebook](https://github.com/ushaakumaar/Python-Project-1/blob/main/Summary_Findings.ipynb)


# Programming Language / Applications Used
***

  * Python 
    - Pandas Library
    - Matplotlib Library
  * Jupyter Notebook

# Contributors
---

- Crystal Dalsania (dalsania.crystal@gmail.com)
- Usha Saravanakumar (ushaakumaar@gmail.com)
- Prarthna Ashutoshmunidottir(prarthna76@gmail.com)
- Chahnaz Kbaisi (chahnaz.k@comcast.net)
- Susan Thomas (sthomas.a4h@gmail.com)
- Jame'l Brown (JayyMaurice@gmail.com)