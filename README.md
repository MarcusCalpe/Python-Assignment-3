# Python-Assignment-3
Made by Marcus Nathan J. Calpe | 2ECE-D
This repository contains the source code for ECE2112 Programming Assessment #3 with solutions to three Python programming problems.

# A. POSITIONAL AND LABEL-BASED SLICING
```python
cars = pd.read_csv('cars.csv')
print("Shape: ", cars.shape)
```
These first lines were used to import the `pandas` library and aliased it as `pd`, which is presumed to be the universal stanrad convention. The `read_csv` function converts the raw values into a structured, two-dimensional DataFrame named `cars`. The second line `cars.shape` returns a tuple of rows and columns to confirm the shape of the dataset.

```
cars_6_to_10 = cars.iloc[5:10]
```
This line `i.loc` was used for positional slicing where the slice exclude the upper bound therefore `[5:10]` extracts position 5, 6, 7, 8, and 9. After this, it is converted into a variable named `cars_6_to_10`.
```python
cars_6_to_10.loc[:,['Model', 'mpg', 'cyl', 'hp', 'gear']]
```
Lastly, this line used `.loc` to slice specific column names rather than positions. The colon `:` before the comma selects all rows within this current subset, while the list on the right side of the comma indicates which columns to extract and their specific order.
# B. MODEL LOOKUP
```python
toyota = cars.loc[cars['Model'] == 'Toyota Corolla']
```
This line demonstrates Boolean indexing wherein the inner statement `cars['Model'] == 'Toyota Corolla` becomes a condition to scan the entire column and generate a `True` or `False` value. The outer `.loc[]` applies a filter that only lets the `True` value pass through and assigns it to the `toyota` variable.

```python
pontiac = cars.loc[cars['Model'] == 'Pontiac Firebird'].loc[:,['Model', 'mpg', 'hp', 'wt']]
```
This final line isloates the `Pontiac Firebird` row using the same Boolean logic as the pervious one. Instead of obtaining all information of the `Pontiac Firebird`, a second `.loc` is inserted to remove unneeded data and keeping only the requested specific statistics.

# C. MULTI-MODEL SUBSETTING
```python
selected_cars = cars.loc[[2,27,29],['Model','mpg','cyl','hp','gear']]
```
In this line, instead of doing another Boolean indexing, this choose specific rows using their exact positions `[2, 27, 29]`, which correspond respectively to the Datsun 710, Lotus Europa, and Ferrari Dino in the raw data. After this, `.loc` simultaneously filters the rows and columns of the requested statistics including their respective values.

README file Version History:
September 5, 2026 - Initial README output Created
September 5, 2026 - Uploaded Python Assignment #3 and cars.csv
