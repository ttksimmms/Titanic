# Titanic
## Project Overview
Welcome to my SQL Skills Showcase repository! This project will demonstrate my knowledge and proficiency in SQL using the famous Titanic Dataset. This repository serves as a testament to my ability to extract valuable information from real-world datasets and present findings through SQL queries. It is a demonstration of my proficiency in database management, querying, and data analysis.
### Tools
- Excel - Data Cleaning 
  - [Download here](https://www.kaggle.com/datasets/shuofxz/titanic-machine-learning-from-disaster/download?datasetVersionNumber=1) 
- PostgreSQL and PgAdmin - Data Analysis and Visualization
- Tableau - Creating Reports

### Data Cleaning/Preparation

Several data preparation tasks were performed to make the dataset suitable for analysis. The following tasks were performed:
1.	Data Aggregation
2.	Filtering and Sorting
3.	Subsetting Data
4.	Working with NULL Values
5.	Handling Missing Values
6.	Dealing with duplicates
7.	Calculating Percentages
   
### Exploratory Data Analysis

EDA involved gaining insights into various aspects of the Titanic dataset to allow the presentation of meaningful visualizations based on the results, such as:

- Survival Analysis by Gender
  - Calculate the survival rate for male and female passengers separately. Compare the proportions of survivors and non-survivors based on gender.
- Class-Wise Survival Analysis:
  - Investigate the survival rates in each passenger class. Understand how survival proportions vary among different classes.
- Age Distribution:
  - Explore the distribution of passenger ages. Analyze the age demographics to identify trends and potential outliers.
- Fare Distribution:
  - Examine the distribution of fares paid by passengers. Understand the range and variability in fare values.
- Passengers with Siblings or Spouses:
  - Analyze the number of siblings or spouses each passenger had on board. Understand the prevalence of familial relationships.
- Passengers with Parents or Children:
  - Explore the distribution of passengers based on the number of parents or children on board.
- Survival Rate by Age Group:
  - Group passengers into age categories and analyze the survival rate within each group.
- Embarkation Port Analysis:
  - Analyze the distribution of passengers based on the embarkation port. Understand the composition of passengers from different ports.

### Data Analysis
Code worked with

- Survival Analysis by Gender
  
  SELECT Sex, AVG(Survived ::numeric) AS
  survival_rate
  FROM titanic GROUP BY Sex;

- Class-wise Survival Analysis

  SELECT Pclass, AVG(Survived: :numeric)
  AS survival_rate
  FROM titanic
  GROUP BY Pclass;

- Age Distribution
  
  SELECT Age, COUNT (*) AS passenger_count
  FROM titanic GROUP BY Age ORDER BY Age;

- Fare Distribution:
  
  SELECT Fare, COUNT (*) AS
  passenger_count
  FROM titanic
  GROUP BY Fare
  ORDER BY Fare;

- Passengers with Siblings or Spouses

  SELECT SibSP, COUNT (*) as passenger_count
  FROM titanic GROUP BY SibSp ORDER BY SibSp;

- Passengers with Parents or Children

  SELECT Parch, COUNT (*) as passenger_count FROM titanic
  GROUP BY Parch ORDER BY Parch;

- Survival Rate by Age Group

  Select
    CASE
      WHEN Age < 18 THEN 'Child'
      WHEN Age >= 18 AND Age < 60
  THEN 'Adult'
      ELST 'Senior'
    END as age_group,
    AVG(Survived: :numeric) as
  survival_rate
  FROM titanic
  GROUP BY age_group

- Embarkation Port Analysis

    SELECT Embarked, COUNT (*) as
    passenger_count
    FROM titanic
    GROUP BY Embarked;

### Results/Findings

The analysis results are summarized as follows:
