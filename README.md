# datafun-06-eda
Module 6 Project
Melissa Stone Rogers, June 3, 2024

## Introduction
Professional project to create an exploratory data analysis (EDA) project using GitHub, Git, Jupyter, pandas, Seaborn and other popular data analytics tools.
Commands were used on a Mac machine running zsh.  

## How to Install and Run the Project
Create project repository in Github and clone to your machine.

```
git clone project.url
```

```
python3 -m venv .venv
source .venv/bin/activate
```

Create requirements.txt in the root project folder. 
```
touch requirements.txt
```

Install required packages 
```
pip install requests matplotlib pandas seaborn pyarrow
```

## Freeze Requirements

```
python3 -m pip freeze > requirements.txt
```

## Add .gitignore File
Add .gitignore file to the root project folder. 
```
touch .gitignore
```
Add the following to your .gitignore file: 
- .venv/
- .vscode/
- .ipynb_checkpoints/

## Initial Project Save
```
git add .
git commit -m "initial"                         
git push origin main
```
## Project Data Set
For this project, a data set from Seaborn will be used. The data file is flights.csv and contains data of the number of passengers in given months and years. 
[Flights Data Set](https://github.com/mwaskom/seaborn-data/blob/master/flights.csv)


## Exploratory Data Analysis within Jupyter
Create a new juypyter file. 
```
touch filename.ipynb
```

## Import Dependencies 

```
import matplotlib.pyplot as plt
import pandas as pd
import seaborn as sns
import pyarrow as pa
```
## Follow Steps to Complete EDA
### Data Acquisition
```
# Load the dataset into a pandas DataFrame - adjust this process for your custom data
df = sns.load_dataset('flights')

# Inspect first rows of the DataFrame
print(df.head())
```
### Initial Data Inspection
```
print(df.head(10))
print(df.shape)
print(df.dtypes)
```
### Initial Descriptive Statistics
```
print(df.describe())
```
### Initial Data Distribution for Numerical Columns
```
# Inspect histogram by numerical column
df['passengers'].hist()

# Inspect histograms for all numerical columns
df.hist()

# Show all plots
plt.show()
```
### Initial Data Distribution for Categorical Columns 
```
# Inspect value counts by categorical column
df['month'].value_counts()

# Inspect value counts for all categorical columns
for col in df.select_dtypes(include=['object', 'category']).columns:
    # Display count plot
    sns.countplot(x=col, data=df)
    plt.title(f'Distribution of {col}')
    plt.show()

# Show all plots
plt.show()
```
### Initial Data Transformation and Feature Engineering
```
# Rename the column
flights.rename(columns={'passengers': 'customers'}, inplace=True)


# Add new column and calculate the cumulative sum of customers
flights['cumulative_customers'] = flights['customers'].cumsum()


# Print transformations
print(flights.head())

# Print column names
print(flights.columns)
```
### Initial Visualizations 
This section provides three different visualizations and discussions of the data. A box plot, line plot, and bar graph were used. 
#### Part 1, box plot
```
# Create a box plot to depict outliers
plt.figure(figsize=(10, 6))
sns.boxplot(x=flights['customers'])

# Set the title and labels
plt.title('Box Plot of Customers')
plt.xlabel('Customers')

# Show the plot
plt.show()
```
#### Part 2, line plot
```
# Create a line plot
sns.lineplot(data=flights, x='year', y='customers')

# Set the title and labels
plt.title('Number of Customers Over Time')
plt.xlabel('Year')
plt.ylabel('Number of Customers')

# Show the plot
plt.show()
```
#### Part 3, bar graph
```
# Calculate the total number of customers for each month
total_customers_by_month = flights.groupby('month', observed=True)['customers'].sum().reset_index()

# Sort the data by total customers in descending order
total_customers_by_month = total_customers_by_month.sort_values(by='customers', ascending=False)

# Create a bar plot
plt.figure(figsize=(10, 6))
sns.barplot(data=total_customers_by_month, x='month', y='customers', order=total_customers_by_month['month'])

# Set the title and labels
plt.title('Total Number of Customers by Month')
plt.xlabel('Month')
plt.ylabel('Total Number of Customers')

# Show the plot
plt.show()
```

### Summary
Within each visualization of data, observations and conclusions were noted. 


## Complete Your Project
Save your project and push back to your repository. 
```
git add .
git commit -m "final"                         
git push origin main
```

## Project Summary


## Specification

This project was built to the following specification:
https://github.com/denisecase/datafun-06-spec