# Overview

Welcome to my analysis of the data job market, specifically targeting data analyst roles. This project stems from a desire to better navigate and comprehend the job market. It examines the top-paying and in-demand skills to help identify the best job opportunities for data analysts.

The data, sourced from [Luke Barousse's Python Course](https://lukebarousse.com/python), serves as the foundation for my analysis, providing detailed information on job titles, salaries, locations, and essential skills. Using a series of Python scripts, I address key questions such as the most demanded skills, salary trends, and the correlation between demand and salary in the data analytics field.

# The Questions

Below are the questions I want to answer in my project:

1. What are the most in-demand skills for the top three most popular data roles?
2. How are the in-demand skills trending for Data Analysts?
3. How well do jobs and skills pay for Data Analysts?
4. What are the optimal skills for Data Analysts to learn? (High Demand and High Paying)

# Tools used

For my in-depth exploration of the data analyst job market, I utilized several key tools:

1.  **Python:** The backbone of my analysis, enabling me to process the data and uncover critical insights. I also used the following Python libraries:
     1. **Pandas Library:** Used for data analysis.
     2. **Matplotlib Library:** Utilized for data visualization.
     3. **Seaborn Library:** Assisted in creating advanced visualizations.
2. **Jupyter Notebooks:** The platform I used to run my Python scripts, which allowed for seamless integration of notes and analysis.
3. **Visual Studio Code:** My preferred editor for executing Python scripts.
4. **Git & GitHub:** Crucial for version control and sharing my code and analysis, facilitating collaboration and project tracking.

# Data Preparation and Cleanup

This section outlines the steps taken to prepare the data for analysis, ensuring accuracy and usability.

## Import & Clean Up Data

I start by importing necessary libraries and loading the dataset, followed by initial data cleaning tasks to ensure data quality.

```python
# Importing libraries
import ast
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
from datasets import load_dataset

# Loading data
data = load_dataset("lukebarousse/data_jobs")
df = data['train'].to_pandas()

# Cleaning data
df['job_posted_date'] = pd.to_datetime(df['job_posted_date'])
df['job_skills'] = df['job_skills'].apply(lambda x: ast.literal_eval(x)if pd.notna(x) else x)
```

## Filter US Jobs

To focus my analysis on the U.S. job market, I apply filters to the dataset, narrowing down to roles based in the United States.

```python
df_us = df[df['job_country'] == 'United States']
```
 
 ## EDA for Data Analyst Jobs in US
In this section, I conducted an Exploratory Data Analysis (EDA) specifically focused on data analyst jobs in the United States. The objective was to gain a comprehensive understanding of the job market, identify trends, and extract meaningful insights.
View my notebook with detailed steps here: [1_EDA](1_EDA.IPYNB)

### RESULTS

 ![Data analyst job in different job loactions in US] (2_PYTHON_PROJECT/images/data_analyst_roles_per_location.png)



