# ECE2112---ADVANCED-PROGRAMMING---PA3
# SACABEN, MARIA DANIELA C. 2ECE-C

# Data Analysis with Pandas - Cars Dataset

# Overview
This project demonstrates the use of pandas in Python for data manipulation, subsetting, slicing, and indexing using the cars.csv dataset.

The project is divided into two main problems:
1. Problem 1 → Loading the dataset and displaying the first and last rows.
2. Problem 2 → Extracting specific information using subsetting, slicing, and indexing operations.

# Files in the Repository
- `cars.csv` → Dataset containing car specifications.
- `problem1.py` → Python script for Problem 1 (loading and displaying rows).
- `problem2.py` → Python script for Problem 2 (subsetting, slicing, indexing).
- `README.md` → Documentation file (this file).

# Requirements
- Python 3.7 or later
- pandas library

Install pandas if not already installed:
  `pip install pandas`

# How to Run the Code
1. Place the `cars.csv` file in the same directory as the Python scripts.
2. Run the scripts from the terminal or your IDE:

 `python problem1.py `
 `python problem2.py `

# Problem 1 - Load Data & Display Rows
Tasks:
a. Load the `cars.csv` file into a DataFrame named cars.
b. Display the first five rows.
c. Display the last five rows.
d. Concatenate both results together.

# Code:
 `import pandas as pd `

#Load the csv file
 `cars = pd.read_csv('cars.csv') `

#Locate the first 5 rows
 `first = cars.loc[cars.index[0:5]] `

#Locate the last 5 rows
 `last = cars.loc[cars.index[27:32]] `

#Concatenate first & last
 `print(pd.concat([first, last])) `

#Alternative using head() and tail()
 `print(pd.concat([cars.head(5), cars.tail(5)])) `

 # Sample Output
 <img width="707" height="415" alt="image" src="https://github.com/user-attachments/assets/84bb7f8e-e231-4d1d-9d4b-7150bccec859" />


# Problem 2 - Subsetting, Slicing, and Indexing
Tasks:
a. Display the first five rows with odd-numbered columns (1, 3, 5, 7...).
b. Display the row where the Model = Mazda RX4.
c. Find the number of cylinders (cyl) for the car model Camaro Z28.
d. Find the cylinders (cyl) and gear type (gear) for:
  - Mazda RX4 Wag
  - Ford Pantera L
  - Honda Civic

# Code
 `import pandas as pd `

#Load the csv file
 `cars = pd.read_csv('cars.csv') `

#a. First five rows with odd-numbered columns
 `print(cars.iloc[0:5, 0:13:2]) `

#b. Row with 'Mazda RX4'
 `print(cars.loc[cars['Model'] == 'Mazda RX4']) `

#c. Cylinders in Camaro Z28
 `n = cars.loc[cars['Model'] == 'Camaro Z28', 'cyl'].values[0] `
 `print("Cylinders in Camaro Z28:", n) `

#d. Cylinders and Gear for selected models
 `models = ['Mazda RX4 Wag', 'Ford Pantera L', 'Honda Civic'] `
 `MD = cars.set_index("Model") `
 `print(MD.loc[models, ["cyl", "gear"]]) `

# Sample Output
a. First 5 rows, odd-numbered columns

<img width="410" height="221" alt="image" src="https://github.com/user-attachments/assets/1ae2e9e7-f742-4462-8229-72119e33e4bf" />

b. Mazda RX4 Row

<img width="643" height="80" alt="image" src="https://github.com/user-attachments/assets/26730df7-d715-48e4-a9a6-53a588b81fbe" />

c. Cylinders in Camaro Z28

<img width="38" height="32" alt="image" src="https://github.com/user-attachments/assets/3135f5de-278c-41b2-92d4-ddb2e8bb5bc1" />

d. Cylinders & Gear Types

<img width="232" height="190" alt="image" src="https://github.com/user-attachments/assets/b24c06ae-5ecf-4ad9-9353-1f519bed83b2" />



