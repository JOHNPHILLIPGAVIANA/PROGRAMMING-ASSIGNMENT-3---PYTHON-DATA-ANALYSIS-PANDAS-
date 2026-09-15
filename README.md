# PROGRAMMING ASSIGNMENT 3 - PYTHON DATA ANALYSIS (PANDAS)
## Gaviana, John Phillip V.
## 2ECE-A
This repository contains the Python program and readme file for Programming Assignment 3 - Python Data Analysis (Pandas). 

## Python Program and Explanation
```python
import pandas as pd
```
This loads the Pandas Library into Python

# A. Positional and Label-Based Slicing

## Python Program and Explanation
```python
#Loads the csv file into the notebook
cars = pd.read_csv('cars.csv')
cars

c = cars
c
```
### 1. Data Import and Variable Assignment (`pd.read_csv`, Variable Assignment)
**Purpose:** This reads the dataset into memory. The `pd.read_csv('cars.csv')` function loads the external comma-separated values file into a Pandas DataFrame named `cars`, which is subsequently aliased to `c` for streamlined variable reference in subsequent operations.

```python
c.shape
```
### 2. Dimension Inspection (`c.shape`)
**Purpose:** This inspects the structural bounds of the dataset. Executing `c.shape` returns a tuple representing the total dimensions of the DataFrame, confirming the presence of 32 rows and 12 columns.

```python
#Positional slicing which contains rows 6 through 10 of the dataset, where the first data row is row 1.
cars_6_to_10 = c.iloc[5:10]
cars_6_to_10 
```
### 3. Positional Row Selection (`c.iloc[5:10]`)
**Purpose:** This operation extracts a target subset of rows using integer-based indexing. The `.iloc[5:10]` indexer uses zero-based slicing to extract rows starting at index 5 up to (but excluding) index 10, isolating the 6th through 10th records of the dataset into `cars_6_to_10`.

```python
#Displays only the columns Model, mpg, cyl, hp, and gear in that order from the dataset containing rows 6 through 10.
(cars_6_to_10[['Model', 'mpg', 'cyl', 'hp', 'gear']])
```
### 4. Label-Based Column Filtering
**Purpose:** This applies column filtering to the row subset using explicit string labels. Passing a list of column names (`['Model', 'mpg', 'cyl', 'hp', 'gear']`) into the subset DataFrame filters out all unlisted attributes, displaying only the selected technical metrics for the specified vehicle range.


# B. Model Lookup

## Python Program and Explanation
```python
df = pd.read_csv('cars.csv')
df
```
### 1. Data Import (`pd.read_csv('cars.csv')`)
**Purpose:** This loads the raw dataset into memory using Pandas. The `pd.read_csv()` function parses the `cars.csv` file into a structured DataFrame assigned to `df`, making the dataset accessible for tabular querying operations.

```python
#Displays the complete row for Toyota Corolla
toyota = df[df['Model'] == 'Toyota Corolla']
toyota
```
### 2. Full Record Retrieval (`df[df['Model'] == 'Toyota Corolla']`)
**Purpose:** Executes Boolean filtering to retrieve a complete record based on a specific attribute value. The condition `df['Model'] == 'Toyota Corolla'` generates a boolean mask that identifies matching rows, returning a DataFrame containing all specification columns for the designated model.


```python
#Displays only the model, mpg, hp, and wt for Pontiac Firebird
pontiac = df.loc[df['Model'] == 'Pontiac Firebird', ['Model', 'mpg', 'hp', 'wt']]
pontiac
```
### 3. Targeted Attribute Lookup (`df.loc[..., ['Model', 'mpg', 'hp', 'wt']]`)
**Purpose:** This combines Boolean row filtering with explicit column subsetting using `.loc`. Passing the logical condition `df['Model'] == 'Pontiac Firebird'` isolates the matching record, while the column list `['Model', 'mpg', 'hp', 'wt']` restricts the output to display only those four specific metrics.

# C. Multi-Model Subsetting

## Python Program and Explanation
```python
cars = pd.read_csv('cars.csv')
cars
```
### 1. Data Import (`pd.read_csv('cars.csv')`)
**Purpose:** This imports the raw dataset into memory using Pandas. Calling `pd.read_csv('cars.csv')` processes the spreadsheet data into a structured DataFrame object assigned to `cars`.

```python
#Creates a Dataframe containing only the records for three models: Datsun 710,Lotus Europa, and Ferrari Dino.
selected_cars = cars.loc[cars['Model'].isin(['Datsun 710', 'Lotus Europa', 'Ferrari Dino']), ['Model', 'mpg', 'cyl', 'hp', 'gear']]
selected_cars
```
### 2. Multi-Condition Filtering and Column Selection (`.loc`, `.isin`)
**Purpose:** This isolates specific target records and limits the output attributes in a single step. The condition `cars['Model'].isin(...)` generates a boolean mask that matches any row where the vehicle name exists in the provided list. Passing this filter alongside the column array `['Model', 'mpg', 'cyl', 'hp', 'gear']` into `.loc` extracts those specific rows and columns into `selected_cars`.

```python
# Display Dataframe and its shape
display(selected_cars)
print(selected_cars.shape)
```
### 3. Display and Output Verification (`display()`, `.shape`)
**Purpose:** The presents the resulting subset and verifies its dimensions. The `display()` function outputs the formatted table, while `selected_cars.shape` prints the tuple `(3, 5)`, confirming that the filtered DataFrame strictly contains three rows and five columns.
