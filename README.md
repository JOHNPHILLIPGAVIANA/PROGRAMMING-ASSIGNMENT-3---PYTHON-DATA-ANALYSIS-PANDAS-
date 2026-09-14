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
### 1. Data Ingestion & Alias Assignment (`pd.read_csv`, Variable Assignment)
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
**Purpose:** The final block applies column filtering to the row subset using explicit string labels. Passing a list of column names (`['Model', 'mpg', 'cyl', 'hp', 'gear']`) into the subset DataFrame filters out all unlisted attributes, displaying only the selected technical metrics for the specified vehicle range.
