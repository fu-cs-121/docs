# Study Guide: Essential Concepts for Processing Text Data in Python

This guide covers fundamental programming concepts necessary for processing and analyzing text data using Python. It is designed to help you read data from files, manipulate and analyze that data, and write updated data back to files—all without relying on external libraries.

---

## Table of Contents

1. **Reading Data from Text Files**
2. **Working with Data Structures**
3. **Parsing and Converting Data**
4. **Using List Comprehensions**
5. **Performing Calculations on Data**
6. **Adjusting Data Values**
7. **Writing Data to Text Files**
8. **Defining and Using Functions**
9. **Formatting Output**
10. **Additional Tips**

---

## 1. Reading Data from Text Files

### Opening and Reading Files

To read data from a file, use the `open()` function along with a `with` statement. This ensures the file is properly closed after its contents are read.

```python
with open('data.txt', 'r') as file:
    for line in file:
        print(line)
```

### Skipping Headers

If the file has a header row (e.g., column names), you can skip it using the `next()` function.

```python
with open('data.txt', 'r') as file:
    next(file)  # Skip the header line
    for line in file:
        print(line)
```

---

## 2. Working with Data Structures

### Lists and Dictionaries

- **List**: An ordered collection of items.
- **Dictionary**: A collection of key-value pairs.

### Examples

**List of Values**

```python
numbers = [1, 2, 3, 4, 5]
```

**Dictionary**

```python
person = {'name': 'Alice', 'age': 30, 'city': 'New York'}
```

**List of Dictionaries**

```python
data = [
    {'name': 'Alice', 'score': 90},
    {'name': 'Bob', 'score': 85}
]
```

---

## 3. Parsing and Converting Data

### Splitting Lines into Fields

Assuming data is comma-separated:

```python
line = 'Alice,90'
fields = line.strip().split(',')  # ['Alice', '90']
```

### Converting Strings to Numbers

Use `int()` for integers and `float()` for decimal numbers.

```python
score = int(fields[1])  # Converts '90' to 90
```

### Removing Whitespace

Use the `strip()` method to remove leading and trailing whitespace.

```python
text = '  Hello World  '
clean_text = text.strip()  # 'Hello World'
```

---

## 4. Using List Comprehensions

List comprehensions provide a concise way to create lists based on existing lists.

### Example: Extracting Data from a List of Dictionaries

Suppose you have a list of dictionaries:

```python
data_list = [
    {'name': 'Alice', 'score': 90},
    {'name': 'Bob', 'score': 85},
    {'name': 'Charlie', 'score': 95}
]
```

**Using a Loop**

```python
scores = []
for item in data_list:
    scores.append(item['score'])
```

**Using a List Comprehension**

```python
scores = [item['score'] for item in data_list]
```

Both methods will produce the same `scores` list:

```python
[90, 85, 95]
```

### Advantages of List Comprehensions

- **Concise**: Shorter and often more readable code.
- **Efficient**: Can be faster than using loops in some cases.

---

## 5. Performing Calculations on Data

### Summing Values

To sum numeric values in a list:

```python
numbers = [10, 20, 30]
total = sum(numbers)  # 60
```

### Calculating Averages

Average = Total Sum / Number of Items

```python
numbers = [10, 20, 30]
average = sum(numbers) / len(numbers)  # 20.0
```

### Calculating Totals from a List of Dictionaries

```python
data = [
    {'quantity': 5, 'price': 2.0},
    {'quantity': 3, 'price': 1.5}
]

total_value = sum(item['quantity'] * item['price'] for item in data)  # 16.5
```

---

## 6. Adjusting Data Values

### Adjusting Numerical Values

To adjust numerical values by a certain rate (e.g., increasing prices by 10%):

```python
adjustment_rate = 1.10  # 10% increase
for item in data:
    item['price'] *= adjustment_rate
```

---

## 7. Writing Data to Text Files

### Writing to a File

Open a file in write mode and write data line by line.

```python
with open('output.txt', 'w') as file:
    file.write('Name,Score\n')  # Write header
    for item in data:
        line = f"{item['name']},{item['score']}\n"
        file.write(line)
```

### Formatting Data for Writing

Ensure data is converted to strings before writing.

```python
line = ','.join([item['name'], str(item['score'])])
file.write(line + '\n')
```

---

## 8. Defining and Using Functions

Functions encapsulate reusable code blocks, allowing you to organize your code and avoid repetition.

### Defining Functions with Parameters and Return Values

```python
def add(a, b):
    return a + b

result = add(5, 3)  # 8
```

### Passing Parameters

Functions can accept parameters to make them more flexible.

```python
def greet(name):
    return f"Hello, {name}!"

message = greet('Alice')
print(message)  # Hello, Alice!
```

### Returning Values

Functions can return values that can be used elsewhere in your code.

```python
def calculate_total(scores):
    return sum(scores)

scores = [90, 85, 95]
total_score = calculate_total(scores)
print(total_score)  # 270
```

### Example: Refactoring Code into a Function

Suppose you have code that reads data from a file and processes it at the root level.

**Original Code**

```python
data_list = []
with open('data.txt', 'r') as file:
    file.readline()  # Skip header
    for line in file:
        fields = line.strip().split(',')
        record = {
            'name': fields[0],
            'score': int(fields[1])
        }
        data_list.append(record)

# Continue processing data_list...
```

**Refactored into a Function**

By moving this code into a function, you can reuse it and keep your code organized.

```python
def load_data(filename):
    data_list = []
    with open(filename, 'r') as file:
        file.readline()  # Skip header
        for line in file:
            fields = line.strip().split(',')
            record = {
                'name': fields[0],
                'score': int(fields[1])
            }
            data_list.append(record)
    return data_list

# Now you can call the function
data_list = load_data('data.txt')

# Continue processing data_list...
```

### Benefits of Using Functions

- **Reusability**: Functions can be called multiple times with different parameters.
- **Organization**: Helps structure your code, making it easier to read and maintain.
- **Modularity**: Changes in the function code don't require changes where the function is called.

---

## 9. Formatting Output

### Printing with Specific Decimal Places

Use formatted strings (f-strings) to control the number of decimal places.

```python
value = 123.456789
print(f"Value rounded to two decimal places: {value:.2f}")  # 123.46
```

### Aligning Text Output

```python
print(f"{'Name':<10}{'Score':>5}")
print(f"{'Alice':<10}{95:>5}")
```

Output:

```
Name        Score
Alice         95
```

---

## 10. Additional Tips

### Using the `len()` Function

To get the number of items in a list:

```python
number_of_records = len(data_list)
print(f"Number of records loaded: {number_of_records}")
```

### Avoiding Division by Zero

When calculating averages, check if the denominator is not zero.

```python
if len(data_list) > 0:
    average = total / len(data_list)
else:
    average = 0
```

---

## Conclusion

By understanding and applying these concepts, you can effectively process and analyze text data using Python. Practice by working through the exercise provided and experimenting with different data sets and adjustment factors. These foundational skills are essential for any data processing tasks you may encounter.
