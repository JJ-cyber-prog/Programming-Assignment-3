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

The output produced by the code: 

First 5 rows: 
               Model   mpg  cyl   disp   hp  drat     wt   qsec  vs  am  gear  \
0          Mazda RX4  21.0    6  160.0  110  3.90  2.620  16.46   0   1     4   
1      Mazda RX4 Wag  21.0    6  160.0  110  3.90  2.875  17.02   0   1     4   
2         Datsun 710  22.8    4  108.0   93  3.85  2.320  18.61   1   1     4   
3     Hornet 4 Drive  21.4    6  258.0  110  3.08  3.215  19.44   1   0     3   
4  Hornet Sportabout  18.7    8  360.0  175  3.15  3.440  17.02   0   0     3   

   carb  
0     4  
1     4  
2     1  
3     1  
4     2  

Last 6 rows: 
             Model   mpg  cyl   disp   hp  drat     wt  qsec  vs  am  gear  \
27    Lotus Europa  30.4    4   95.1  113  3.77  1.513  16.9   1   1     5   
28  Ford Pantera L  15.8    8  351.0  264  4.22  3.170  14.5   0   1     5   
29    Ferrari Dino  19.7    6  145.0  175  3.62  2.770  15.5   0   1     5   
30   Maserati Bora  15.0    8  301.0  335  3.54  3.570  14.6   0   1     5   
31      Volvo 142E  21.4    4  121.0  109  4.11  2.780  18.6   1   1     4   

    carb  
27     2  
28     4  
29     6  
30     8  
31     2  


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

The output produced by the code:

First five rows with odd-numbered columns:
               Model  cyl   hp     wt  vs  gear
0          Mazda RX4    6  110  2.620   0     4
1      Mazda RX4 Wag    6  110  2.875   0     4
2         Datsun 710    4   93  2.320   1     4
3     Hornet 4 Drive    6  110  3.215   1     3
4  Hornet Sportabout    8  175  3.440   0     3

Row with 'Mazda RX4' model:
       Model   mpg  cyl   disp   hp  drat    wt   qsec  vs  am  gear  carb
0  Mazda RX4  21.0    6  160.0  110   3.9  2.62  16.46   0   1     4     4

Cylinders in 'Camaro Z28':
8

Cylinders and gear type for specific models:
             Model  cyl  gear
1    Mazda RX4 Wag    6     4
18     Honda Civic    4     4
28  Ford Pantera L    8     5

# Authors:
Jerome Oldan
