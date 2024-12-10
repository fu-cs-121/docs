## Unit 3 (Final Exam) Study Guide

Below are the key concepts and tasks you should be familiar with for the final exam. This guide covers the essential topics from Units 1-3, including variables, data types, control flow, functions, data structures, and more.

---

# Table of Contents

1. Variables and Data Types
2. Input and Output
3. Control Flow (If/Else, Loops)
4. Functions
5. Data Structures (Lists, Dictionaries)
6. String and List Utility Functions
7. Object-Oriented Programming (Classes)
8. File I/O (Reading and Writing Files)
9. Assertions

---

## 1. Variables and Data Types

**What/Why:** Variables store information your program uses, and data types define the kind of information (e.g., integers, strings, booleans). Understanding variables and data types is foundational, as it allows you to handle input, perform calculations, and manipulate text and boolean logic correctly.

**Example:**

```python
name = "Alice"    # string
age = 30          # integer
pi = 3.14         # float
is_active = True  # boolean
```

---

## 2. Input and Output

**What/Why:** Input functions let your program receive data from a user or another source. Output functions, like `print()`, allow you to display results. This communication enables interactive programs and user-driven flows.

**Example:**

```python
user_input = input("Enter a value: ")
print("You entered:", user_input)
```

---

## 3. Control Flow (If/Else, Loops)

**What/Why:** Control flow structures allow your program to make decisions (`if/else`) and repeat actions (`while`/`for` loops). This logic dictates the program’s path, enabling complex behaviors like conditional processing and iterative tasks.

**If/Else Example:**

```python
score = 85
if score >= 90:
    print("Excellent")
elif score >= 70:
    print("Good")
else:
    print("Needs Improvement")
```

**Loop Example:**

```python
count = 0
while count < 3:
    print(count)
    count += 1

for color in ["red", "green", "blue"]:
    print(color)
```

---

## 4. Functions

**What/Why:** Functions are reusable blocks of code that perform specific tasks. They help organize logic, reduce repetition, and make code easier to read and maintain.

**Example:**

```python
def greet(name):
    return f"Hello, {name}!"

message = greet("Alice")
print(message)
```

---

## 5. Data Structures (Lists, Dictionaries)

**What/Why:** Data structures like lists and dictionaries hold multiple values in organized, accessible ways. Lists are ordered collections, while dictionaries map keys to values. These structures let you store, manipulate, and retrieve data efficiently.

**List Example:**

```python
fruits = ["apple", "banana", "cherry"]
print(fruits[0])        # "apple"
fruits.append("orange") # ["apple", "banana", "cherry", "orange"]
```

**Dictionary Example:**

```python
person = {"name": "Bob", "age": 25}
print(person["name"])   # "Bob"
person["city"] = "Paris"
```

**List of Dictionaries Example:**

```python
people = [
    {"name": "Alice", "age": 30},
    {"name": "Bob", "age": 25},
    {"name": "Charlie", "age": 40}
]
print(people[1]["name"]) # "Bob"
```

---

## 6. String and List Utility Functions

**What/Why:** Utility functions help you examine and manipulate strings and lists. By using built-ins like `len()`, or methods like `str.center()`, you can easily handle counts, formatting, and structural adjustments.

**String Utilities Example:**

```python
text = "Hello"
length = len(text)          # 5
centered = text.center(10)  # "   Hello  "
```

**List Utilities Example:**

```python
numbers = [10, 20, 30]
count = len(numbers)  # 3
numbers.extend([40, 50]) # [10, 20, 30, 40, 50]
```

---

## 7. Object-Oriented Programming (Classes)

**What/Why:** Classes let you bundle data (attributes) and functions (methods) together, modeling complex real-world entities. Object-oriented programming helps organize large codebases and makes it easier to reason about related functionality.

**Example:**

```python
class Car:
    def __init__(self, make, model):
        self.make = make
        self.model = model

    def description(self):
        return f"{self.make} {self.model}"

my_car = Car("Toyota", "Corolla")
print(my_car.description())  # "Toyota Corolla"
```

---

## 8. File I/O (Reading and Writing Files)

**What/Why:** File I/O allows you to persist data, load configurations, or process large sets of information stored outside your code. Reading lets you consume stored data, while writing lets you save new or updated information.

**Reading Files Example:**

```python
with open("input.txt", "r") as infile:
    for line in infile:
        line = line.strip()
        print(line)
```

**Writing Files Example:**

```python
with open("output.txt", "w") as outfile:
    outfile.write("Hello, world!\n")
```

---

## 9. Assertions

**What/Why:** `assert` statements are used to test assumptions in your code. If an assertion fails, it raises an error, indicating that something unexpected or incorrect occurred. Assertions help ensure that functions behave as intended and can catch bugs early.

**Example:**

```python
def add(a, b):
    return a + b

result = add(2, 2)
assert result == 4, "Addition result should be 4"
```
