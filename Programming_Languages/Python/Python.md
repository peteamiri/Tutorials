# Python

## For more information

* [Python official documentation site](https://www.python.org/doc/)
* [Python 3 documentation](https://docs.python.org/3/)
* [Python Anywhere](https://www.pythonanywhere.com/)

## Various Sample Code for python

* [batteries_included](https://www.pythonanywhere.com/batteries_included/)

```python
def factorial(n):
    if n == 0:
        return 1
    else:
        return n * factorial(n - 1)

# Test the factorial function
number = 5
result = factorial(number)
print(f"The factorial of {number} is {result}")
vbnet
Copy code

```

When rendered, it will appear as a code block with syntax highlighting for Python.

In this code, we define a recursive function called factorial that takes an integer n as input. The base case is when n is equal to 0, in which case the function returns 1. Otherwise, it recursively calls itself with n - 1 as the argument and multiplies the current value of n with the result.

We then test the factorial function by calculating the factorial of 5 and storing the result in the result variable. Finally, we print out the result using formatted string literals (f-string).

This code will output:

```python
The factorial of 5 is 120
```


### Data Proccessing Code

```python

import pandas as pd

# Read data from a CSV file
data = pd.read_csv('data.csv')

# Explore the data
print("Number of rows:", data.shape[0])
print("Number of columns:", data.shape[1])
print("Column names:", data.columns)

# Filter the data
filtered_data = data[data['Category'] == 'Books']

# Sort the data
sorted_data = filtered_data.sort_values('Price', ascending=False)

# Perform calculations
total_sales = sorted_data['Price'].sum()
average_price = sorted_data['Price'].mean()

# Display the results
print("Total sales:", total_sales)
print("Average price:", average_price)

```

In this example, we assume that you have a CSV file named `data.csv` containing your data. We use the Pandas library to read the data into a DataFrame object called data. We then explore the data by printing the number of rows, number of columns, and column names.

Next, we filter the data to keep only the rows where the `Category` column is equal to 'Books'. We sort the filtered data by the 'Price' column in descending order.

We then perform calculations on the sorted data, calculating the total sales by summing the 'Price' column and finding the average price using the mean() function.

Finally, we display the results by printing the total sales and average price.

Please note that you may need to adjust the code based on your specific data and requirements.
