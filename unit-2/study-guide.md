# Unit 2 Study Guide: File I/O, Data Structures, and Functions

_The most up-to-date version of this guide is available at: bit.ly/cs121-unit2-guide_

This guide covers essential programming techniques for reading and processing data stored in files. You’ll learn how to work with files, manage data with lists and dictionaries, perform calculations, adjust values, and write updated information back to files—all by writing your own functions.

---

## Table of Contents

1. [Reading Data from Files](#reading-data-from-files)
2. [Working with Lists and Dictionaries](#working-with-lists-and-dictionaries)
3. [Parsing and Converting Data](#parsing-and-converting-data)
4. [Defining and Using Functions](#defining-and-using-functions)
5. [Performing Calculations on Data](#performing-calculations-on-data)
6. [Adjusting Data Values](#adjusting-data-values)
7. [Writing Data to Files](#writing-data-to-files)
8. [Formatting Output and Additional Tips](#formatting-output-and-additional-tips)

---

## 1. Reading Data from Files

Use Python’s built-in `open()` function along with a `with` statement to read data safely.

**Example: Reading a File Line-by-Line**

```python
with open('data.txt', 'r') as file:
    for line in file:
        print(line.strip())
```

If your file contains a header, you can skip it with:

```python
with open('data.txt', 'r') as file:
    next(file)  # Skip the header line
    for line in file:
        print(line.strip())
```

---

## 2. Working with Lists and Dictionaries

### Lists

Lists store ordered collections of items. For example:

```python
numbers = [1, 2, 3, 4, 5]
```

### Dictionaries

Dictionaries store key-value pairs and are ideal for representing records:

```python
record = {'label': 'Sample', 'count': 10, 'metric': 2.5}
```

### Combining Both

Often you will work with a list of dictionaries to represent multiple records:

```python
data = [
    {'label': 'A', 'count': 5, 'metric': 1.2},
    {'label': 'B', 'count': 8, 'metric': 3.4}
]
```

---

## 3. Parsing and Converting Data

When processing raw file data, split each line into parts and convert strings to the appropriate types.

**Example: Splitting and Converting a Line**

```python
line = "ItemX,20,4.75\n"
parts = line.strip().split(',')  # ['ItemX', '20', '4.75']
label = parts[0]
count = int(parts[1])
metric = float(parts[2])
```

---

## 4. Defining and Using Functions

Encapsulating code into functions makes your programs modular and easier to test. Each function should take input parameters, process data, and return output values. For instance, you might write a function that reads a file and returns a list of records.

**Example: Loading Data from a File**

```python
def load_data(file_path):
    """
    Reads a file where each line contains three comma-separated values:
    a label (string), a count (integer), and a metric (float).
    Returns a list of dictionaries with keys: 'label', 'count', 'metric'.
    """
    records = []
    with open(file_path, 'r') as file:
        # Optionally skip the header if the file has one:
        # next(file)
        for line in file:
            parts = line.strip().split(',')
            record = {
                'label': parts[0],
                'count': int(parts[1]),
                'metric': float(parts[2])
            }
            records.append(record)
    return records

# Example usage:
data_records = load_data('data.txt')
print(f"Loaded {len(data_records)} records.")
```

---

## 5. Performing Calculations on Data

Once you have loaded your data into a list of dictionaries, you can perform calculations such as totals and averages.

**Example: Calculating Total Value and Average Metric**

```python
def compute_summary(records):
    total_value = 0
    total_count = 0
    for rec in records:
        total_value += rec['count'] * rec['metric']
        total_count += rec['count']
    average_metric = total_value / total_count if total_count != 0 else 0
    return total_value, average_metric

# Example usage:
total, average = compute_summary(data_records)
print(f"Total value: {total:.2f}")
print(f"Average metric: {average:.2f}")
```

---

## 6. Adjusting Data Values

You may need to update each record in your data (for example, to apply a discount or adjustment factor).

**Example: Applying an Adjustment Factor**

```python
def adjust_values(records, adjustment_factor):
    """
    Adjusts the 'metric' of each record by multiplying it with an adjustment factor.
    The factor should be less than 1 for a reduction (e.g., 0.8 for a 20% discount).
    """
    for rec in records:
        rec['metric'] *= adjustment_factor
    return records

# Example usage:
adjusted_records = adjust_values(data_records, 0.8)
```

---

## 7. Writing Data to Files

After processing or adjusting data, you may want to write the results back to a file.

**Example: Writing Data to a Text File**

```python
with open('updated_data.txt', 'w') as file:
    for rec in data_records:
        # Format each record as a comma-separated line.
        line = f"{rec['label']},{rec['count']},{rec['metric']:.2f}\n"
        file.write(line)
```

---

## 8. Formatting Output and Additional Tips

When displaying numerical results, use formatted strings to control the number of decimal places.

**Example: Formatting Output**

```python
print(f"Total value: ${total:.2f}")
print(f"Average metric: {average:.2f}")
```

Additional tips:

- Use functions to keep your code modular.
- Test each function independently before integrating them into your main program.
