Titanic Passenger List Analysis

Project Overview

This project involves analyzing the Titanic Passenger List dataset as part of the HNG Internship Stage Zero Task. The goal is to perform an initial exploration of the dataset, identify key insights, and communicate findings through a brief technical report. This README provides a comprehensive overview of the project, including steps for data exploration, analysis, and report generation.

Dataset Information

The Titanic Passenger List dataset contains information about passengers aboard the RMS Titanic, including their survival status, demographic details, and ticket information. The dataset is available from Kaggle and consists of three files:

train.csv: The training dataset with full details of 891 passengers. test.csv: The test dataset used for model predictions (not used in this initial analysis). gender_submission.csv: A sample submission file for predictions (not used in this initial analysis).

Project Structure

train.csv: The main dataset used for analysis.

README.md: Detailed documentation of the project.

visualizations/: Directory containing visualization images used in the report.

Data Exploration and Analysis

Step 1

I loaded the dataset into my Python notebook and ran the following code to display the first few rows to understand its structure:

python

Copy code

import pandas as pd

Load the dataset

titanic_data = pd.read_csv('train.csv')

Display the first few rows

titanic_data.head()

From this, I observed the dataset includes columns such as PassengerId, Survived, Pclass, Name, Sex, Age, SibSp, Parch, Ticket, Fare, Cabin, and Embarked.

Step 2: Summary Statistics

Next, I generated summary statistics to get an overview of the data:

python

Copy code

Summary statistics

titanic_data.describe(include='all')

The summary statistics provided insights into the numerical and categorical variables, showing counts, mean values, and distributions.

Step 3: Visualizations

Survival Count Plot

I plotted a bar chart for the survival count using the following code:

python

Copy code

import seaborn as sns

import matplotlib.pyplot as plt

plt.figure(figsize=(10, 6))

sns.countplot(data=titanic_data, x='Survived')

plt.title('Survival Count')

plt.savefig('visualizations/survival_count.png') # Save as an image

plt.show() survival_count

![survival_count](https://github.com/olayimikatimileyin/Titanic-Passenger-List-Analysis/assets/173846132/8ea3c4d2-251e-4ba6-91b3-2f449b8e7564)

From the visuals, I observed that a smaller proportion of passengers survived (approx. 38%) compared to those who did not survive (approx. 62%).

Passenger Class Distribution

Next, I plotted the distribution of passenger classes:

python

Copy code

plt.figure(figsize=(10, 6))

sns.countplot(data=titanic_data, x='Pclass')

plt.title('Passenger Class Distribution')

plt.savefig('visualizations/passenger_class_distribution.png') # Save as an image

plt.show()

passenger_class_distribution

![passenger_class_distribution](https://github.com/olayimikatimileyin/Titanic-Passenger-List-Analysis/assets/173846132/86dc9615-2053-433b-9975-52af49eee66a)

The visualization revealed that the majority of passengers were in the 3rd class, followed by 1st and 2nd classes. This indicates a higher number of lower-class passengers on board.

Age Distribution

I also plotted the age distribution of the passengers:

python

Copy code

plt.figure(figsize=(10, 6))

sns.histplot(data=titanic_data, x='Age', bins=30, kde=True)

plt.title('Age Distribution')

plt.savefig('visualizations/age_distribution.png') # Save as an image

plt.show()

![age_distribution](https://github.com/olayimikatimileyin/Titanic-Passenger-List-Analysis/assets/173846132/ed22ae07-ffae-4fd7-b210-f07f14132cef)


age_distribution

From this plot, I observed that the age distribution is right-skewed with most passengers being in their 20s and 30s. There are also significant numbers of children and elderly passengers.

Step 4: Initial Insights

Based on the data exploration and visualizations, I identified the following initial insights:

Survival Distribution
Approximately 38% of passengers survived the disaster, while 62% did not. This indicates a higher fatality rate among the passengers.

Passenger Class Distribution
The majority of passengers were in the 3rd class, suggesting a larger number of lower-class passengers on board. The distribution of passenger classes is as follows:

1st Class: 216 passengers

2nd Class: 184 passengers

3rd Class: 491 passengers 3. Age Distribution

The age distribution of passengers is right-skewed, with most passengers in their 20s and 30s. There are also significant numbers of children and elderly passengers. The dataset contains some missing values for the age variable, which would need to be addressed in a more detailed analysis. 4. Gender Distribution

There are more male passengers (577) compared to female passengers (314). This gender imbalance could be relevant in analyzing survival rates, as historical accounts suggest women and children were prioritized during evacuation.

Embarkation Points
The majority of passengers embarked from Southampton (S), followed by Cherbourg (C) and Queenstown (Q):

Southampton (S): 644 passengers

Cherbourg (C): 168 passengers

Queenstown (Q): 77 passengers

Fare Distribution
The fare paid by passengers varies widely, with a mean fare of 32.20 and a standard deviation of 49.69. This indicates some passengers paid significantly higher fares, potentially

reflecting differences in accommodation and services.

Technical Report

The final step involves writing a technical report to communicate the findings. The report includes:

Introduction: Brief description of the dataset and purpose of the review.

Observations: Presentation of initial insights supported by visualizations.

Conclusion: Summary of observations and suggestions for further analysis.

The report is published as a blog post on Medium with the required visualizations and links to the HNG Internship websites.

Conclusion

This project provides an initial exploration of the Titanic Passenger List dataset, identifying key insights and presenting them in a well-structured technical report. The analysis

forms a foundation for further, more detailed investigations.
