# Unit 2 Study Guide: File I/O, CSV Handling, Data Structures, and Functions

_The most up-to-date version of this guide is available at: bit.ly/cs121-unit2-guide_

This guide covers fundamental programming techniques for reading, processing, and analyzing CSV data in Python. You will learn how to work with files, manage data with lists and dictionaries, perform calculations, and write updated information back to files—all through reusable functions that return values you can work with.

---

## Table of Contents

1. Reading Data from Files and CSVs
2. Working with Lists and Dictionaries
3. Parsing and Converting Data
4. Loading CSV Data Using the csv Module
5. Performing Calculations on Data
6. Adjusting Data Values
7. Writing Data to Files and CSVs
8. Defining and Using Functions  
     8.1. Functions for Data Loading  
     8.2. Functions for Data Processing
9. Formatting Output and Additional Tips

---

## 1. Reading Data from Files and CSVs

### Opening and Reading Files

Use the `open()` function with a `with` statement to safely read data from files:

```python
with open('data.txt', 'r') as file:
    for line in file:
        print(line.strip())
```

### Skipping Headers

If your file has a header row, skip it using `next()`:

```python
with open('data.txt', 'r') as file:
    next(file)  # Skip header
    for line in file:
        print(line.strip())
```

---

## 2. Working with Lists and Dictionaries

### Lists

A list is an ordered collection of items:

```python
fruits = ['apple', 'banana', 'cherry']
```

### Dictionaries

A dictionary stores key-value pairs, which are useful for representing records:

```python
fruit_info = {'name': 'apple', 'quantity': 10, 'price': 0.5}
```

### Combining Both

Often you’ll work with a list of dictionaries to represent multiple rows of data:

```python
inventory = [
    {'name': 'apple', 'quantity': 10, 'price': 0.5},
    {'name': 'banana', 'quantity': 15, 'price': 0.3}
]
```

---

## 3. Parsing and Converting Data

### Splitting and Cleaning Data

When reading from a plain text file, you may need to split a line into fields and remove extra whitespace:

```python
line = "apple,10,0.5\n"
fields = line.strip().split(',')  # ['apple', '10', '0.5']
```

### Converting Data Types

Convert string values to numbers for calculations:

```python
quantity = int(fields[1])
price = float(fields[2])
```

---

## 4. Loading CSV Data Using the csv Module

Python’s `csv` module makes it easy to work with CSV files. Using `DictReader` handles the header row and creates dictionaries for each row automatically.

### Example: Using csv.DictReader

```python
import csv

with open('data.csv', 'r', newline='') as csvfile:
    reader = csv.DictReader(csvfile)
    data_list = []
    for row in reader:
        # Convert string values to appropriate data types
        row['quantity'] = int(row['quantity'])
        row['price'] = float(row['price'])
        data_list.append(row)

print("Data loaded:", data_list)
```

_Key Concepts:_

- **Automatic Header Handling:** Each row becomes a dictionary with keys matching the header.
- **Data Conversion:** Converting strings to numeric types ensures data is ready for calculations.

---

## 5. Performing Calculations on Data

### Calculating Totals and Averages

For a list of dictionaries, calculate totals by looping through each item:

```python
total_value = 0
total_quantity = 0
for item in data_list:
    total_value += item['quantity'] * item['price']
    total_quantity += item['quantity']

if total_quantity != 0:
    average_price = total_value / total_quantity
else:
    average_price = 0

print("Total value:", total_value)
print("Average price:", average_price)
```

_Concepts Covered:_

- **Multiplying Values:** Multiply quantity by price for each record.
- **Looping:** Use a standard `for` loop to process data.
- **Conditional Checks:** Prevent division by zero when calculating averages.

---

## 6. Adjusting Data Values

To modify numerical values across your data records—such as adjusting prices for inflation—use a loop to update each item.

### Example: Adjusting Prices by a Fixed Rate

```python
inflation_rate = 1.10  # Represents a 10% increase
for item in data_list:
    item['price'] = item['price'] * inflation_rate

print("Adjusted data:", data_list)
```

_Concepts Covered:_

- **Iterating Over Dictionaries:** Modify each record using a loop.
- **Arithmetic Operations:** Apply multiplication to adjust values.

---

## 7. Writing Data to Files and CSVs

### Writing to a Text File

Write output line by line:

```python
with open('output.txt', 'w') as file:
    for item in data_list:
        line = f"{item['name']},{item['quantity']},{item['price']:.2f}\n"
        file.write(line)
```

### Writing to a CSV File Using csv.DictWriter

```python
import csv

with open('updated_data.csv', 'w', newline='') as csvfile:
    fieldnames = ['name', 'quantity', 'price']
    writer = csv.DictWriter(csvfile, fieldnames=fieldnames)
    writer.writeheader()
    for item in data_list:
        writer.writerow(item)
```

_Concepts Covered:_

- **File Output:** Writing strings and formatted data to files.
- **CSV Formatting:** Using `DictWriter` to create CSV rows from dictionaries automatically.

---

## 8. Defining and Using Functions

Encapsulating repeated operations into functions makes your code organized and reusable. In the sections below, we provide examples of functions that load and process data, including how they return values and how you can use these returned values in your program.

### 8.1. Functions for Data Loading

When loading data from a file or CSV, define a function that:

- Accepts a filename as a parameter.
- Opens the file, processes each line or row.
- Returns a list of dictionaries (or any other data structure) that contains the processed data.

**Example: Loading CSV Data**

```python
def load_csv_data(filename):
    import csv
    data_list = []
    with open(filename, 'r', newline='') as csvfile:
        reader = csv.DictReader(csvfile)
        for row in reader:
            # Convert data types as needed
            row['quantity'] = int(row['quantity'])
            row['price'] = float(row['price'])
            data_list.append(row)
    return data_list

# Using the function:
inventory = load_csv_data('data.csv')
print("Inventory loaded:", inventory)
```

_Explanation:_

- The function `load_csv_data` encapsulates the CSV loading process.
- It returns a list of dictionaries that can be used later for further processing.

### 8.2. Functions for Data Processing

Once data is loaded, you can define functions to process it. For example, you might want to calculate totals or averages.

**Example: Calculating Totals and Averages**

```python
def calculate_totals(data):
    total_value = 0
    total_quantity = 0
    for item in data:
        total_value += item['quantity'] * item['price']
        total_quantity += item['quantity']
    if total_quantity != 0:
        average_price = total_value / total_quantity
    else:
        average_price = 0
    return total_value, average_price

# Using the function:
inventory_total, average_unit_price = calculate_totals(inventory)
print(f"Total Inventory Value: ${inventory_total:.2f}")
print(f"Average Price per Unit: ${average_unit_price:.2f}")
```

_Explanation:_

- The function `calculate_totals` processes the data by iterating over each dictionary.
- It calculates the total value and total quantity, then computes the average price.
- Both values are returned as a tuple. When calling the function, you can unpack the returned values into separate variables.

_Usage in a Program:_
By combining these functions, you can create a program that first loads data from a file, processes it, and then uses the returned values for further actions such as displaying output or writing to another file.

---

## 9. Formatting Output and Additional Tips

### Formatting Numerical Output

Use formatted strings (f-strings) to display numbers with a fixed number of decimal places:

```python
print(f"Total value: ${inventory_total:.2f}")
print(f"Average price: ${average_unit_price:.2f}")
```

### Useful Functions

- **len():** Get the number of records in a list.
- **strip():** Remove unwanted whitespace from strings.
- **join():** Concatenate list items into a single string when needed.
