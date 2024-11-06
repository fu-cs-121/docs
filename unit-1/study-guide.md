# Unit 1 Study Guide

This study guide is designed to help you master essential Python programming concepts covered in Unit 1 of CSC-121. It covers fundamental topics such as variables, data types, input/output operations, operators, conditionals, loops, functions, lists, random number generation, string manipulation, and input validation. Understanding these concepts will empower you to tackle a variety of programming challenges with confidence.

---

## Table of Contents

1. **Variables and Data Types**
2. **Input and Output Operations**
3. **Operators**
4. **Conditional Statements**
5. **Loops**
6. **Functions**
7. **Lists**
8. **Random Number Generation**
9. **String Manipulation**
10. **Input Validation**
11. **Additional Concepts**
12. **Conclusion**

---

## 1. Variables and Data Types

### Variables

Variables are containers for storing data values. In Python, you don't need to declare the type of a variable; you simply assign a value to it.

**Example:**

```python
age = 25
name = "Alice"
is_student = True
```

### Data Types

Python has several built-in data types:

- **Numeric Types:** `int`, `float`
- **Text Type:** `str`
- **Boolean Type:** `bool`
- **Sequence Types:** `list`

**Common Data Types:**

- **Integer (`int`):** Whole numbers, e.g., `10`, `0`, `-5`
- **Float (`float`):** Decimal numbers, e.g., `3.14`, `0.0`, `-2.5`
- **String (`str`):** Text data, e.g., `"Hello, World!"`
- **Boolean (`bool`):** Logical values, `True` or `False`

### Type Conversion

You can convert between data types using built-in functions:

- `int()`: Converts to integer
- `float()`: Converts to float
- `str()`: Converts to string

**Example:**

```python
age_str = "25"
age_int = int(age_str)
height = 5.9
height_int = int(height)  # Results in 5
```

---

## 2. Input and Output Operations

### The `input()` Function

The `input()` function allows you to receive input from the user as a string.

**Example:**

```python
name = input("What is your name? ")
```

### The `print()` Function

The `print()` function displays output to the console.

**Example:**

```python
print("Hello, World!")
print("Your name is", name)
```

### String Formatting

You can format strings using f-strings (formatted string literals) for more readable code.

**Example:**

```python
age = 25
print(f"You are {age} years old.")
```

---

## 3. Operators

### Arithmetic Operators

- `+`: Addition
- `-`: Subtraction
- `*`: Multiplication
- `/`: Division (results in a float)
- `//`: Floor Division (results in an integer)
- `%`: Modulus (remainder of division)
- `**`: Exponentiation

**Example:**

```python
sum = 10 + 5        # 15
difference = 10 - 5 # 5
product = 10 * 5    # 50
quotient = 10 / 3   # 3.333...
floor_div = 10 // 3 # 3
remainder = 10 % 3  # 1
power = 2 ** 3      # 8
```

### Comparison Operators

- `==`: Equal to
- `!=`: Not equal to
- `<`: Less than
- `<=`: Less than or equal to
- `>`: Greater than
- `>=`: Greater than or equal to

**Example:**

```python
x = 10
print(x == 10)  # True
print(x != 5)   # True
print(x > 5)    # True
```

### Logical Operators

- `and`: True if both operands are true
- `or`: True if at least one operand is true
- `not`: Inverts the truth value

**Example:**

```python
x = 10
print(x > 5 and x < 15)  # True
print(x < 5 or x > 15)   # False
print(not(x == 10))      # False
```

---

## 4. Conditional Statements

Conditional statements allow you to execute code blocks based on certain conditions.

### The `if` Statement

Executes a block of code if the condition is true.

**Syntax:**

```python
if condition:
    # Code to execute if condition is true
```

**Example:**

```python
age = 20
if age >= 18:
    print("You are an adult.")
```

### The `elif` Statement

Checks another condition if the previous ones were false.

**Syntax:**

```python
if condition1:
    # Code if condition1 is true
elif condition2:
    # Code if condition2 is true
```

**Example:**

```python
score = 85
if score >= 90:
    grade = 'A'
elif score >= 80:
    grade = 'B'
```

### The `else` Statement

Executes a block of code if all preceding conditions are false.

**Syntax:**

```python
if condition:
    # Code if condition is true
else:
    # Code if condition is false
```

**Example:**

```python
number = 5
if number % 2 == 0:
    print("Even number")
else:
    print("Odd number")
```

---

## 5. Loops

Loops are used to execute a block of code repeatedly.

### `for` Loops

Used for iterating over a sequence (like a list, tuple, or string).

**Syntax:**

```python
for variable in sequence:
    # Code to execute in each iteration
```

**Example:**

```python
for i in [1, 2, 3]:
    print(i)
```

### The `range()` Function

Generates a sequence of numbers.

**Syntax:**

- `range(stop)`
- `range(start, stop[, step])`

**Example:**

```python
for i in range(5):
    print(i)  # Prints numbers from 0 to 4

for i in range(1, 6):
    print(i)  # Prints numbers from 1 to 5

for i in range(0, 10, 2):
    print(i)  # Prints 0, 2, 4, 6, 8
```

### `while` Loops

Repeats as long as a condition is true.

**Syntax:**

```python
while condition:
    # Code to execute repeatedly
```

**Example:**

```python
count = 0
while count < 5:
    print(count)
    count += 1
```

### `while` Loops with Counters

You can use a `while` loop with a counter to limit the number of iterations, such as allowing the user a fixed number of attempts.

**Example:**

```python
attempts = 3
while attempts > 0:
    guess = input("Enter your guess: ")
    if guess == "correct":
        print("Correct!")
        break
    else:
        attempts -= 1
        print(f"Incorrect. You have {attempts} attempts remaining.")
```

---

## 6. Functions

Functions are reusable blocks of code that perform a specific task.

### Defining Functions

Use the `def` keyword to define a function.

**Syntax:**

```python
def function_name(parameters):
    # Code block
```

**Example:**

```python
def greet(name):
    print(f"Hello, {name}!")
```

### Calling Functions

Invoke a function by using its name followed by parentheses.

**Example:**

```python
greet("Alice")
```

### Parameters and Arguments

- **Parameters:** Variables listed in a function's definition.
- **Arguments:** Values passed to the function when called.

**Example:**

```python
def add(a, b):
    return a + b

result = add(5, 3)
```

### Return Values

Functions can return values using the `return` statement.

**Example:**

```python
def square(n):
    return n * n

print(square(4))  # Outputs 16
```

### Modifying and Extending Functions

Functions can be updated or extended to meet new requirements. You may need to modify existing functions or create new ones to support additional features in your programs.

**Example:**

```python
def greet(name):
    print(f"Hello, {name}!")

# Modified function to include time of day
def greet(name, time_of_day):
    print(f"Good {time_of_day}, {name}!")

greet("Alice", "morning")
```

---

## 7. Lists

Lists are ordered, mutable collections of items.

### Creating Lists

Use square brackets `[]` to create a list.

**Example:**

```python
numbers = [1, 2, 3, 4, 5]
```

### Accessing Elements

Use indices to access list elements. Indices start at 0.

**Example:**

```python
first = numbers[0]      # 1
last = numbers[-1]      # 5
```

### Modifying Lists

- **Append an Item:**

  ```python
  numbers.append(6)
  ```

- **Remove an Item:**

  ```python
  numbers.remove(3)     # Removes the first occurrence of 3
  ```

### Built-in List Functions

- **`len(list)`:** Returns the number of items
- **`sum(list)`:** Returns the sum of numeric items
- **`min(list)`:** Returns the smallest item
- **`max(list)`:** Returns the largest item

**Example:**

```python
total = sum(numbers)
count = len(numbers)
smallest = min(numbers)
largest = max(numbers)
```

---

## 8. Random Number Generation

The `random` module allows you to generate random numbers and select random elements.

### Importing the `random` Module

```python
import random
```

### Generating Random Numbers

- **Random Integer Between Two Values:**

  ```python
  n = random.randint(1, 10)  # Includes both endpoints
  ```

- **Random Float Between 0 and 1:**

  ```python
  f = random.random()
  ```

### Selecting Random Elements from a List

Use `random.choice()` to select a random element from a list.

**Example:**

```python
choices = ['apple', 'banana', 'cherry']
random_choice = random.choice(choices)
```

### Shuffling a List

```python
choices = ['a', 'b', 'c']
random.shuffle(choices)
```

### Shuffling a String

You can shuffle the characters of a string by converting it to a list, shuffling the list, and then joining the characters back into a string.

**Example:**

```python
import random

word = "hello"
word_list = list(word)
random.shuffle(word_list)
shuffled_word = ''.join(word_list)

```

---

## 9. String Manipulation

Strings are sequences of characters enclosed in quotes.

### String Methods

- **`lower()`:** Converts all characters to lowercase.

  ```python
  text = "Hello".lower()  # "hello"
  ```

- **`upper()`:** Converts all characters to uppercase.

  ```python
  text = "Hello".upper()  # "HELLO"
  ```

- **`isalpha()`:** Returns `True` if all characters are alphabetic and the string is not empty.

  ```python
  "Hello".isalpha()     # True
  "Hello123".isalpha()  # False
  ```

- **isdigit()**: Returns `True` if all characters are digits.

  ```python
  "123".isdigit()       # True
  "123abc".isdigit()    # False
  ```

- **`split()`:** Splits a string into a list based on a delimiter (default is space).

  ```python
  words = "This is a test".split()  # ['This', 'is', 'a', 'test']
  ```

- **`strip()`:** Removes leading and trailing whitespace.

  ```python
  text = "  Hello  ".strip()  # "Hello"
  ```

### Splitting and Joining Strings

- **Splitting:**

  ```python
  sentence = "one,two,three"
  items = sentence.split(',')  # ['one', 'two', 'three']
  ```

- **Joining:**

  ```python
  words = ['Join', 'these', 'words']
  sentence = ' '.join(words)  # "Join these words"
  ```

### Looping Through Strings

You can loop through each character in a string.

**Example:**

```python
text = "Hello"
for char in text:
    print(char)
```

---

## 10. Input Validation

Input validation ensures that the user input meets the required criteria.

### Checking for Empty Input

```python
user_input = input("Enter something: ")
if not user_input:
    print("You didn't enter anything!")
```

### Checking for Alphabetic Characters

```python
user_input = input("Enter a word: ")
if user_input.isalpha():
    print("Valid input!")
else:
    print("Please enter letters only.")
```

### Looping Until Valid Input is Received

```python
while True:
    guess = input("Enter your guess: ")
    if guess.isalpha():
        break  # Valid input, exit the loop
    else:
        print("Invalid input. Please enter letters only.")
```

---

## 11. Additional Concepts

### Looping Through Lists

**Example:**

```python
numbers = [1, 2, 3, 4, 5]
for num in numbers:
    print(num)
```

### Using `in` and `not in` Operators

Check if an item exists within a list or a character in a string.

**Example:**

```python
vowels = 'aeiou'
letter = 'e'
if letter in vowels:
    print("It's a vowel.")
```

### The `%` Modulus Operator

Returns the remainder of a division operation.

**Example:**

```python
number = 10
if number % 3 == 0:
    print("Divisible by 3!")
else:
    print("Not divisible by 3 :(")
```

---

## 12. Conclusion

This study guide covers the fundamental Python concepts that are essential for developing a solid foundation in programming. By understanding variables, data types, input/output operations, operators, conditionals, loops, functions, lists, random number generation, string manipulation, and input validation, you'll be well-equipped to tackle a wide range of programming challenges.
