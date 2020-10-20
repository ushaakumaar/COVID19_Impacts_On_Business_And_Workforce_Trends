# Project Title: COVID-19 Impacts on Business and Workforce Trends
***

[About](#about) | [Questions Analyzed](#questions-analyzed) | [Data Source](#data-source) | [Install Dependencies](#install-dependencies) | [Data Analysis Process](#data-analysis-process) | [Summary Findings](#summary-findings) | [Contributors](#contributors)


# About
***

COVID-19 has been one of the most unpredictable and transformative pandemics in recorded history. It has been overwhelming because most businesses could not sustain, and many people lost their jobs. Our team decided to study the overall impacts of this pandemic on various businesses and workforce trends in the US. 

This project analyzes COVID-19-related business trends through a detailed assessment of unemployment rates, economic fluctuations, and factors (e.g., demographics, travel, personal habits) that likely contribute to the growth or contraction US during the worldwide pandemic. Correlations and associations between various factors and increased downturn point to specific, consistent vulnerabilities.

# Questions Analyzed
***

COVID-19 impacts and the questions we wanted to analyze as part of this project:
* **Unemployment** - Which ethnic group, industry and states had the highest and lowest unemployment rates during the pandemic?
* **Businesses** - Which businesses economically benefitted or lost the most due to COVID-19?
* **Airlines & Travel Routes** - Which airlines and travel routes were most affected during the pandemic?
* **Mobility Trends** - Is there any relationship between the total COVID-19 cases and mobility trends (i.e., people staying at home) in the US?
* **Safest Travel Destination** - In the current situation, which is the US's safest travel destination right now?

# Data Source
***

* **Unemployment**
    - [Unemployment Rates for various Races](https://beta.bls.gov/dataQuery/find?st=0&r=20&q=unemployment&more=0&fq=cg:[Unemployment+and+Labor+Force+Status])
    - [Unemployment Rates for various Industries](https://beta.bls.gov/dataQuery/find?st=0&r=20&q=unemployment&more=0&fq=cg:[Establishments%2FBusinesses%2FFirms])
    - [Unemployment Rates for all US States](https://beta.bls.gov/dataQuery/find?st=0&r=20&q=unemployment&more=0&fq=cg:[Geography])

* **Businesses**
    - [Jupyter Notebook Script](https://github.com/ushaakumaar/Python-Project-1/blob/main/business-stock-retrieval.ipynb) was written based on the python script available in [kaggle](https://www.kaggle.com/jacksoncrow/download-nasdaq-historical-data) to retrieve all NASDAQ traded stock prices on 2019/12/31(Pre COVID), 2020/03/31, 2020/06/30 and 2020/10/09 into a CSV file for further analysis.

* **Airlines & Travel Routes**
    - Wrote a Jupyter Notebook Script to split the csv file in the downloads folder available in [Kaggle](https://www.kaggle.com/akulbahl/covid19-airline-flight-delays-and-cancellations) to retrieve all airlines data from January 2020 to June 2020 into nine CSV files (300,000 rows of data in each file) for further analysis.

* **Mobility Trends**
    - [US Mobility _(Population staying at home)_ Data](https://data.bts.gov/)
    - [US National Level COVID data](https://raw.githubusercontent.com/nytimes/covid-19-data/master/us.csv)

* **Safest Travel Destination**
    - [US County-Level Population Data](https://www2.census.gov/programs-surveys/popest/tables/2010-2019/counties/totals/co-est2019-annres-06.xlsx)
    - [US County-Level COVID data](https://github.com/nytimes/covid-19-data/blob/master/us-counties.csv)
    - [US County-Level data for Mapping](https://raw.githubusercontent.com/plotly/datasets/master/geojson-counties-fips.json)

# Install Dependencies
***

* **Businesses**

>`pip install yfinance`

* **Mobility Trends**

>`pip install sodapy`

>Update APP Token, Key ID, Key Secret from [https://data.bts.gov](https://data.bts.gov) in config.py file

* **Safest Travel Destination**

>`conda install plotly`

>`conda install -c plotly plotly-orca`

>`conda install -c plotly plotly-geo`

>`conda install -c plotly plotly_express==0.4.1`

# Data Analysis Process
***
The project collects data from multiple sources cited above, performs normalization and aggregations after that, and, based on the data, generates various plots/maps to analyze and determine useful insights and draw conclusions to answer the questions.

## Data Clean Up and Data Wrangling

Performed following data clean up and wrangling steps wherever required. The cleaned and transformed data was used for the remaining steps.

* Cleaned up the data by removing NaNs and duplicates
* Converted the data to appropriate data types
* Merged multiple sources of data into one dataset and used it for the remaining steps

## Summary Statistics

* **Unemployment**
    - Chose the US states that were most affected (or) less affected due to the pandemic to generate the plot

* **Businesses**
    - Calculated the percentage of change in stock price for each specified period
    - Top 10 and Bottom 10 performing businesses were determined

* **Airlines & Travel Routes**
    - The route that has maximum cancellations was determined
    - The Route that has maximum delays was determined
    - Airline that has maximum cancellations was determined
    - Airline that has maximum delays was determined

* **Safest Travel Destination**
    - Top 15 Safest travel destinations at County Level in the US was determined

## Data Visualization

* **Unemployment**
    - Generated a [line plot](https://github.com/ushaakumaar/Python-Project-1/blob/main/Images/state_lineplot.png) with Unemployment Rates for all US states
    - Generated a [line plot](https://github.com/ushaakumaar/Python-Project-1/blob/main/Images/states_interested_lineplot.png) with Unemployment Rates for the States that were most affected (or) less affected due to the pandemic
    - Generated a [line plot](https://github.com/ushaakumaar/Python-Project-1/blob/main/Images/race_lineplot.png) with Unemployment Rates for various races
    - Generate a [line plot](https://github.com/ushaakumaar/Python-Project-1/blob/main/Images/industry_lineplot.png) with Unemployment Rates for ten chosen industries
    
* **Businesses**
    - Generated a [line plot](https://github.com/ushaakumaar/Python-Project-1/blob/main/Images/top_10_business_lineplot.png) for top 10 performing businesses with Pre COVID, Mar 2020, June 2020 and Oct 2020 Profit % Changes
    - Generated a [bar plot](https://github.com/ushaakumaar/Python-Project-1/blob/main/Images/top_10_business_barplot.png) for top 10 performing businesses with Oct 2020 Profit % Changes
    - Generated a [line plot](https://github.com/ushaakumaar/Python-Project-1/blob/main/Images/bottom_10_business_lineplot.png) for bottom 10 performing businesses with Pre COVID, Mar 2020, June 2020 and Oct 2020 Profit % Changes
    - Generated a [bar plot](https://github.com/ushaakumaar/Python-Project-1/blob/main/Images/bottom_10_business_barplot.png) for bottom 10 performing businesses with Oct 2020 Profit % Changes

* **Airlines & Travel Routes**
    - Generated a [bar plot](https://github.com/ushaakumaar/Python-Project-1/blob/main/Images/route_cancellations_bar.png) with Total Cancellations per Routes (Top 15)
    - Generated a [bar plot](https://github.com/ushaakumaar/Python-Project-1/blob/main/Images/airlines_cancellations_bar.png) with Total Cancellations per Airlines

* **Mobility Trends**
    - Generated a [scatter plot](https://github.com/ushaakumaar/Python-Project-1/blob/main/Images/mobility_cases_scatterplot.png) with a linear regression model to see if there is a correlation between population staying at home and covid cases at national level.
    - Generated a [scatter plot](https://github.com/ushaakumaar/Python-Project-1/blob/main/Images/mobility_death_scatterplot.png) with linear regression model to see if there is correlation between population staying at home and covid deaths at national level.
    - Generated a [line plot](https://github.com/ushaakumaar/Python-Project-1/blob/main/Images/mobility_lineplot.png) to show the mobility and covid trend at national level

* **Safest Travel Destination**
    - Generated a [bar plot](https://github.com/ushaakumaar/Python-Project-1/blob/main/Images/population_diff_bar.png) showing the Percentage of Population difference between 2018 and 2019 at US County Level
    - Generated a [bar plot](https://github.com/ushaakumaar/Python-Project-1/blob/main/Images/top_15_safest_counties_bar.png) showing the Top 15 Safest Counties to Travel
    - Generated a [Plotly Map](https://github.com/ushaakumaar/Python-Project-1/blob/main/Images/safe-county-map.png) showing the County level Covid Cases
    
## Data Analysis

We looked across all the generated figures/tables/maps and noted the observations and inferences. We included these observations at the bottom of the notebook for each question.

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

Summarized overall Analysis for all the questions in the project in [Summary Findings Jupyter Notebook](https://github.com/ushaakumaar/Python-Project-1/blob/main/Summary_Findings.ipynb)


# Programming Language / Applications Used
***

  * Python 
    - Pandas Library
    - Matplotlib Library
  * Jupyter Notebook

# Contributors
---

- Crystal Dalsania ([cdalsania](https://github.com/cdalsania))
- Usha Saravanakumar ([ushaakumaar](https://github.com/ushaakumaar))
- Prarthna Ashutoshmunidottir ([Prarthna-design](https://github.com/Prarthna-design))
- Chahnaz Kbaisi ([Chahnaz-Kbaisi](https://github.com/Chahnaz-Kbaisi))
- Susan Thomas ([SusanCThomas](https://github.com/SusanCThomas))
- Jame'l Brown ([JayyMaurice2020](https://github.com/JayyMaurice2020))