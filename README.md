# COVID-Employment-Analysis

__This notebook describes several examples of queries to the US Bureau of Labor Statistics API and cleans the data into a tidy vertical format.__

The __Bureau of Labor Statistics__ is a unit of the US Dept. of Labor whose mission is to collect and publish data related to the American economy.

### BLS API
The BLS API v2 requires that you [register (for free)](https://data.bls.gov/registrationEngine/) before you proceed with any API request. Once registered, you must store your API key in a config file or environment variable. This notebook reads the API key from a config file module named __api_key__. 

The API serves data from a POST request with your API key and specific query IDs.


### Finding your query ID
To query BLS data, you must know the specific query ID. Query IDs are specific down to the level of Alabama/Statewide/Total Nonfarm, or deeper. From the [BLS Data site](https://www.bls.gov/data/), click on __One-Screen__ and narrow your search to find the series IDs in the format you are looking for.

### blspandas import
This notebook imports functions from a module called blspandas.py, included in the git repo. The functions in this file are wrappers for many of the functions described by [this article by BD Economics](https://www.bd-econ.com/blsapi.html). 

### Queries
This notebook performs three queries for employment changes between January and June 2020 categorized by: 

1. State
2. Race
3. Industry

After each query and cleaning, the data will be saved as a .csv file and added to a SQLite database named __blsdata.db__.