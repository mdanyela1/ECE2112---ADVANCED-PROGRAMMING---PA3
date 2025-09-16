# ECE2112---ADVANCED-PROGRAMMING---PA3
# SACABEN, MARIA DANIELA C. 2ECE-C

# Data Analysis with Pandas - Cars Dataset

# Overview
This project demonstrates the use of **pandas** in Python to manipulate and analyze tabular data using the `cars.csv` dataset.  

The project is divided into two problems:
1. **Problem 1** → Loading data and displaying first & last rows.
2. **Problem 2** → Subsetting, slicing, and indexing to extract specific information.

---

# Files
- `cars.csv` → Dataset file containing car specifications.
- `problem1.py` → Python script for Problem 1.
- `problem2.py` → Python script for Problem 2.
- `README.md` → Documentation file (this file).

---

# Requirements
Ensure you have Python installed and install pandas with:

```bash
pip install pandas

# How to Run
1. Place cars.csv in the same directory as the scripts.
2. Run each script separately:

python problem1.py
python problem2.py

# Problem 1 - Load Data & Display Rows
a. Load the cars.csv file into a DataFrame named cars.
b. Display the first five rows.
c. Display the last five rows.
d. Concatenate the two results.

Code:
import pandas as pd

# Load the csv file in the same folder
cars = pd.read_csv('cars.csv')

# Locate the first 5 rows
first = cars.loc[cars.index[0:5]]

# Locate the last 5 rows
last = cars.loc[cars.index[27:32]]

# Concatenate first & last
print(pd.concat([first, last]))

# Alternative using head() and tail()
print(pd.concat([cars.head(5), cars.tail(5)]))

Sample Output:
             Model   mpg  cyl   disp   hp  drat    wt   qsec  vs  am  gear  carb
0        Mazda RX4  21.0    6  160.0  110  3.90  2.620  16.46   0   1     4     4
1    Mazda RX4 Wag  21.0    6  160.0  110  3.90  2.875  17.02   0   1     4     4
2       Datsun 710  22.8    4  108.0   93  3.85  2.320  18.61   1   1     4     1
3   Hornet 4 Drive  21.4    6  258.0  110  3.08  3.215  19.44   1   0     3     1
4 Hornet Sportabout 18.7    8  360.0  175  3.15  3.440  17.02   0   0     3     2
27    Lotus Europa  30.4    4   95.1  113  3.77  1.513  16.90   1   1     5     2
28  Ford Pantera L  15.8    8  351.0  264  4.22  3.170  14.50   0   1     5     4
29    Ferrari Dino  19.7    6  145.0  175  3.62  2.770  15.50   0   1     5     6
30   Maserati Bora  15.0    8  301.0  335  3.54  3.570  14.60   0   1     5     8
31     Volvo 142E   21.4    4  121.0  109  4.11  2.780  18.60   1   1     4     2

# Problem 2 - Subsetting, Slicing, and Indexing
a. Display the first five rows with odd-numbered columns (1, 3, 5, 7...).
b. Display the row where the Model is Mazda RX4.
c. Find the number of cylinders (cyl) for the car model Camaro Z28.
d. Determine how many cylinders (cyl) and what gear type (gear) the car models Mazda RX4 Wag, Ford Pantera L, and Honda Civic have.

Code:
import pandas as pd

# Load the csv file
cars = pd.read_csv('cars.csv')

# a. First five rows with odd-numbered columns
print(cars.iloc[0:5, 0:13:2])

# b. Row with 'Mazda RX4'
print(cars.loc[cars['Model'] == 'Mazda RX4'])

# c. Cylinders in Camaro Z28
n = cars.loc[cars['Model'] == 'Camaro Z28', 'cyl'].values[0]
print("Cylinders in Camaro Z28:", n)

# d. Cylinders and Gear for selected models
models = ['Mazda RX4 Wag', 'Ford Pantera L', 'Honda Civic']
MD = cars.set_index("Model")
print(MD.loc[models, ["cyl", "gear"]])

Sample Output:

a. First 5 rows, odd-numbered columns
             Model  cyl   hp     wt  vs  gear
0        Mazda RX4    6  110  2.620   0     4
1    Mazda RX4 Wag    6  110  2.875   0     4
2       Datsun 710    4   93  2.320   1     4
3   Hornet 4 Drive    6  110  3.215   1     3
4 Hornet Sportabout    8  175  3.440   0     3

b. Mazda RX4 Row
       Model   mpg  cyl   disp   hp  drat    wt   qsec  vs  am  gear  carb
0  Mazda RX4  21.0    6  160.0  110  3.90  2.62  16.46   0   1     4     4

c. Cylinders in Camaro Z28
Cylinders in Camaro Z28: 8

d. Cylinders & Gear Types
               cyl  gear
Model                    
Mazda RX4 Wag    6     4
Ford Pantera L   8     5
Honda Civic      4     4


