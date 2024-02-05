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

- Class-Wise Survival and Non-Survival Analysis
- Age Distribution
- Fare Distribution
- Passengers with Siblings or Spouses
- Passengers with Parents or Children
- Survival Rate by Age Group
- Embarkation Port Analysis

### Data Analysis
Queries worked with

- Class-wise non-survival Analysis
    - Investigate the non-survival rates in each passenger class. Understand how non-survival varies among the different classes.
      
SELECT "pclass",
	ROUND(AVG(CASE WHEN "survived" = 0
THEN 1 ELSE 0 END) * 100) AS
non_survival_rate_percentage
FROM titanic
GROUP BY "pclass";

- Class-wise Survival Analysis
   - Investigate the survival rates in each passenger class. Understand how survival proportions vary among different classes.

SELECT Pclass, ROUND(AVG(Survived)*100) AS survival_rate
FROM titanic GROUP BY Pclass;

- Age Distribution
  - Explore the distribution of passenger ages and analyze the age demographics.
    
  SELECT Age, COUNT (*) AS passenger_count
  FROM titanic GROUP BY Age ORDER BY Age;

- Fare Distribution
   - Examine the distribution of fares paid by passengers. Understand the range and variability in fare values.
     
  SELECT Fare, COUNT (*) AS
  passenger_count
  FROM titanic
  GROUP BY Fare
  ORDER BY Fare;

- Passengers with Siblings or Spouses
  - Explore the distribution of passengers based on the number of parents or children on board.
    
  SELECT SibSP, COUNT (*) as passenger_count
  FROM titanic GROUP BY SibSp ORDER BY SibSp;

- Passengers with Parents or Children
  - Explore the distribution of passengers based on the number of parents or children on board.
    
  SELECT Parch, COUNT (*) as passenger_count FROM titanic
  GROUP BY Parch ORDER BY Parch;

- Survival Rate by Age Group
  - Group passengers into age categories and analyze the survival rate within each group.
    
  SELECT
    CASE
	WHEN Age IS NULL THEN 'Unknown'
      WHEN Age < 18 THEN 'Child'
      WHEN Age >= 18 AND Age < 60
  THEN 'Adult'
      ELSE 'Senior'
    END as age_group,
    ROUND(AVG("survived") * 100)
	AS survival_rate
  FROM titanic
  GROUP BY age_group

- Embarkation Port Analysis
  - Analyze the distribution of passengers based on the embarkation port. Understand the composition of passengers from different ports.

  SELECT Embarked, COUNT (*) as
  passenger_count
  FROM titanic
  GROUP BY Embarked;

### Results/Findings

Compacted visualization: 

The break-down analysis visualized results are summarized as follows:
- Class-Wise non-survival Analysis [View Here](https://public.tableau.com/views/Class-WiseNon-SurvivalRate/Sheet2?:language=en-US&:display_count=n&:origin=viz_share_link)
  	- As portrayed in the visual findings, Pclass 3 has the highest non-survival rate at 76%, while Pclass 2 is at 53% and Pclass 1 is at 37%
  	  
- Class-Wise Survival Analysis [View Here](https://public.tableau.com/views/Class-WiseSurvivalAnalysis/Class-WiseSurvivalAnalysis?:language=en-US&:display_count=n&:origin=viz_share_link)
  	- As shown in the visual findings. Pclass 1 has the highest percentage of people who survived.
 
- Age Distribution Analysis [View Here](https://public.tableau.com/views/AgeDistribution_17068894085370/AgeDistribution?:language=en-US&:display_count=n&:origin=viz_share_link)
    	- Age distribution visualization shows 177 passengers who's age is unknown.

- Passengers with Siblings or Spouses [View Here](https://public.tableau.com/views/PassengerswithSiblingsSpouse/Sheet1?:language=en-US&:display_count=n&:origin=viz_share_link)
  	- The passengers with siblings or spouses visualization shows that there are over 283 passengers that have over 1 sibling or spouse and over 608 passengers that has neither.

- Passengers with Parents or Children [View Here](https://public.tableau.com/views/PassengerswithParentsandchildren/PassengerswithParentsandChildren?:language=en-US&:display_count=n&:origin=viz_share_link)
  	- Visualizations shows 208 passengers that has parents/children and 678 passengers without either.


  


