# Data and Analytics Engineer - Challenge

**Author:** André Areosa  
**Date:** October 2024

## Objective
The objective of this challenge is:
1. Evaluate data processing capabilities.
2. Evaluate the quality of the code and accuracy of the results.
3. Evaluate communication skills through the report.

## Dataset Overview
This challenge is based on a modified version of the Kaggle competition [Bike Sharing Demand](https://www.kaggle.com/c/bike-sharing-demand) and includes two datasets:

### 1. bikes_rental.csv
This dataset contains hourly rental data for the years 2011 and 2012. The columns are as follows:
- `datetime`: Hourly date + timestamp.
- `season`: Season indicator (1 = spring, 2 = summer, 3 = fall, 4 = winter).
- `workingday`: Indicates whether the day is neither a weekend nor a holiday.
- `weather`: General weather condition (Nice, Cloudy, Light rain, Heavy rain).
- `temp`: Temperature in Celsius.
- `humidity`: Relative humidity.
- `windspeed`: Wind speed.
- `count`: Number of rentals.
- `company_id`: ID of the company that rented bikes at that datetime.

### 2. companies.csv
This dataset contains the `id` and `name` of bike rental companies:
- `id`: Company ID.
- `name`: Company name.

## Process Overview

### 1. Data Extraction
The data extraction process included the following two steps:
- Unzip the bike rental dataset.
- Read the CSV files from the zip file into a DataFrame using pandas.

### 2. Data Cleaning
To ensure data consistency and readability, I performed the following data cleaning tasks using pandas:
- Converted the `datetime` column from string format to `datetime` format.
- Mapped `season` numbers to their corresponding season names for better readability.
- Cleaned the `workingday` column by removing any quotes and casting the values as integers.

### 3. Analysis
For answering the questions, I used both **pandas** and **DuckDB**, a modern, embedded analytics database designed for efficient data processing and querying. DuckDB operates within the same process as the notebook, eliminating network overhead and simplifying deployment.

- **Pandas** was used for basic data manipulation and transformation.
- **DuckDB** was used for SQL queries, providing powerful in-memory analytics.

### 4. Visualization
To createplots and visualizations I used **Matplotlib** and **Seaborn**.

## Questions

1. **How many times was Wednesday the day of the week with the highest rental count?**

2. **Compute the ranking of each company regarding the total number of rentals.** The output should include a table with the columns:
   - `rank`: Starting with 1 for the company with the highest number of rentals.
   - `company_name`: The company name as provided by the `companies.csv` dataset.
   - `count_rentals`: Total number of rentals.

3. **On which day did each hour get its highest number of rentals?** The output should be a table sorted by hour with the following columns:
   - `hour`: Hour of the day from 0 to 23.
   - `date`: The date on which the `hour` had the highest number of rentals.
   - `count_rentals`: The highest number of rentals for that hour.

4. **Compare the daily count of rentals between 2011 and 2012.** Use whichever approach(es) and/or visualization(s) that best showcase the comparison.

5. **Illustrate the effect of `weather`, `temp`, `humidity`, and `windspeed` on the number of rented bikes.** Use whichever approach(es) and/or visualization(s) that best illustrate the answers.

## Getting Started
To run the analysis:
1. Clone the repository.
2. Install the required packages. `pip install pandas duckdb matplotlib seaborn`
3. Open the Jupyter Notebook and run the code cells sequentially.

