# Programming-Assignment-3
This is my submission for the Third Programming Assignment. This program shows us Python Data Analysis (or Pandas as we call it). Pandas is a core Python library that provides high performance, easy-to-use data structures and data analysis tools for the Python Programming Language.

# My codes are as follows:

# Problem One: 

import pandas as pd

### Load the CSV file into a dataframe named cars
url = "http://bit.ly/Cars_file"
cars = pd.read_csv(url)

### Display the first five and last five rows of the dataframe
print("First 5 rows: ")
print(cars.head())

print("\nLast 6 rows: ")
print(cars.tail()) 


# Problem 2:

import pandas as pd

### Load the CSV file into a dataframe named cars
url = "http://bit.ly/Cars_file"
cars = pd.read_csv(url)

### a. Display the first five rows with odd-numbered columns
print("First five rows with odd-numbered columns:")
print(cars.iloc[:5, ::2])  # Selects odd-numbered columns

### b. Display the row that contains the ‘Model’ of ‘Mazda RX4’
print("\nRow with 'Mazda RX4' model:")
mazda_rx4 = cars[cars['Model'] == 'Mazda RX4']
print(mazda_rx4)

### c. How many cylinders (‘cyl’) does the car model ‘Camaro Z28’ have?
print("\nCylinders in 'Camaro Z28':")
camaro_cylinders = cars.loc[cars['Model'] == 'Camaro Z28', 'cyl']
print(camaro_cylinders.values[0])

### d. Determine how many cylinders (‘cyl’) and what gear type (‘gear’) do the car models ‘Mazda RX4 Wag’, 
### ‘Ford Pantera L’ and ‘Honda Civic’ have.
print("\nCylinders and gear type for specific models:")
models = ['Mazda RX4 Wag', 'Ford Pantera L', 'Honda Civic']
subset = cars[cars['Model'].isin(models)][['Model', 'cyl', 'gear']]
print(subset)

# Authors:
Jerome Oldan
1    Mazda RX4 Wag    6     4
18     Honda Civic    4     4
28  Ford Pantera L    8     5

# Authors:
Jerome Oldan
