# Employee Data Analysis with Python 

This project involves analyzing employee data using Python's powerful data manipulation and visualization libraries. The dataset contains various employee attributes, and several analyses are performed to extract meaningful insights.  

## Table of Contents  

- [Installation](#installation)  
- [Usage](#usage)  
- [Data Analysis Tasks](#data-analysis-tasks)  
- [Visualization](#visualization)  

## Installation  

To run this project, you'll need to have Python installed along with the following libraries:  

- pandas  
- numpy  
- matplotlib  
- seaborn  

You can install the required libraries using pip:  

```bash  
pip install pandas numpy matplotlib seaborn

Usage:

1. Clone the repository or download the script.
2. Make sure to have the dataset dataset_for_analysis.csv in the specified path.
3. Run the script to perform the analysis.

# importing the required libraries 

import pandas as pd 
import numpy as np 
import matplotlib.pyplot as plt
import seaborn as sns 


# laoding the dataset

data = pd.read_csv(r"C:\Users\ch.avinash chowdary\Downloads\dataset_for_analysis.csv")
print (data)

# Data analysis tasks 

# 1. Filter employees with a salary above 80,000

data1 = data[data['Salary'] > 80000]
print(data1)

# 2. Identify employees in the 'IT' department who joined after 2020

data['Joining Date'] = pd.to_datetime(data['Joining Date'])
data2= data[(data['Department'] == 'IT') & (data['Joining Date'] > '2020-12-31')]
print(data2)

# 3. Calculate the average salary of employees in each department

data3 = data.groupby ('Department')['Salary'].mean()
print(data3)

# 4. Find te top 5 performers from the dataset

data4 = data.sort_values(by='Performance Score', ascending=False).head(5)
print(data4)

# 5. Count the number of employees in each gender category

data5 = data['Gender'].value_counts()
print(data5)

# 6. Determine the employee with the highest salary

data6 = data.loc[data['Salary'].idxmax()]
print(data6)

# 7. Find employees aged between 30 and 40 working in 'Marketing'

data7 = data[(data ['Age'] >= 30) & (data['Age'] <=40) & (data['Department'] == 'Marketing')]
print(data7)

# 8. Find the average performance score of employees who joined before 2018

data8 = data[data['Joining Date'] < '2018-01-01']['Performance Score'].mean()
print(data8)

# 9. create a histogram of age distribution

data['Age'].plot(kind='hist', bins=10, title='Age Distribution')
plt.xlabel('Age')
plt.show()

# 10. Add a new column caluclating the years of experience

data['Joining Date'] = pd.to_datetime(data['Joining Date'])
data['Years of Experience'] = 2025 - data['Joining Date'].dt.year
print(data)

Discussion:

We welcome feedback and discussion on this project! If you have any suggestions for improvement, additional analyses you'd like to see, or general thoughts on the code, please feel free to open an issue or submit a pull request. Your contributions are greatly appreciated!

How to Share Your Thoughts:

Issues: Report any bugs or request feature enhancements.
Pull Requests: If you've made improvements, we encourage you to contribute!
Discussion: Use the Issues section to start a conversation or ask for help.
