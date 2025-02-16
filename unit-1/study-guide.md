# Unit 1 Study Guide

This guide covers the essential Python concepts for CSC-121, including variables, data types, I/O operations, operators, conditionals, loops, functions, lists, random number generation, string manipulation, input validation, and additional topics. Mastering these fundamentals will equip you to tackle many programming challenges.

---

## Table of Contents

1. [Variables and Data Types](#1-variables-and-data-types)
2. [Input and Output Operations](#2-input-and-output-operations)
3. [Operators](#3-operators)
4. [Conditional Statements](#4-conditional-statements)
5. [Loops](#5-loops)
6. [Functions](#6-functions)
7. [Lists](#7-lists)
8. [Random Number Generation](#8-random-number-generation)
9. [String Manipulation](#9-string-manipulation)
10. [Input Validation](#10-input-validation)
11. [Additional Concepts](#11-additional-concepts)

---

## 1. Variables and Data Types

Variables store data without requiring an explicit declaration of type.

**Example:**

```python
age = 25
name = "Alice"
is_student = True
```

### Common Data Types

- **Integer (`int`):** Whole numbers (e.g., `10`, `0`, `-5`)
- **Float (`float`):** Decimal numbers (e.g., `3.14`, `-2.5`)
- **String (`str`):** Text (e.g., `"Hello, World!"`)
- **Boolean (`bool`):** Logical values (`True` or `False`)
- **List:** Ordered, mutable collections (e.g., `[1, 2, 3]`)

### Type Conversion

Convert between types using built-in functions:

```python
age_str = "25"
age_int = int(age_str)  # Converts to an integer

height = 5.9
height_int = int(height)  # Results in 5 (decimal truncated)
```

---

## 2. Input and Output Operations

### Getting User Input

Use `input()` to receive user input (always as a string):

```python
name = input("What is your name? ")
```

### Displaying Output

Use `print()` to display messages:

```python
print("Hello, World!")
print("Your name is", name)
```

### String Formatting

f-strings embed expressions within string literals:

```python
age = 25
print(f"You are {age} years old.")
```

---

## 3. Operators

### Arithmetic Operators

- `+` Addition
- `-` Subtraction
- `*` Multiplication
- `/` Division (results in a float)
- `//` Floor Division (integer division)
- `%` Modulus (remainder)
- `**` Exponentiation

**Example:**

```python
print(10 + 5)       # 15
print(10 - 5)       # 5
print(10 * 5)       # 50
print(10 / 3)       # 3.333...
print(10 // 3)      # 3
print(10 % 3)       # 1
print(2 ** 3)       # 8
```

### Comparison Operators

- `==` Equal to
- `!=` Not equal to
- `<` Less than
- `<=` Less than or equal to
- `>` Greater than
- `>=` Greater than or equal to

**Example:**

```python
x = 10
print(x == 10)  # True
print(x != 5)   # True
print(x > 5)    # True
```

### Logical Operators

- `and` Both conditions must be true
- `or` At least one condition must be true
- `not` Inverts a boolean value

**Example:**

```python
x = 10
print(x > 5 and x < 15)  # True
print(x < 5 or x > 15)   # False
print(not (x == 10))     # False
```

---

## 4. Conditional Statements

Execute code based on conditions using `if`, `elif`, and `else`.

### if Statement

```python
if condition:
    # Code if condition is True
```

**Example:**

```python
age = 20
if age >= 18:
    print("You are an adult.")
```

### elif Statement

```python
if condition1:
    # Code for condition1
elif condition2:
    # Code for condition2
```

**Example:**

```python
score = 85
if score >= 90:
    grade = 'A'
elif score >= 80:
    grade = 'B'
```

### else Statement

```python
if condition:
    # Code if condition is True
else:
    # Code if condition is False
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

Loops let you execute a block of code repeatedly.

### for Loops

Iterate over a sequence (list, string, etc.):

```python
for i in [1, 2, 3]:
    print(i)
```

#### Using range()

Generate a sequence of numbers:

```python
# 0 to 4:
for i in range(5):
    print(i)

# 1 to 5:
for i in range(1, 6):
    print(i)

# Even numbers from 0 to 8:
for i in range(0, 10, 2):
    print(i)
```

### while Loops

Repeat as long as a condition is true:

```python
count = 0
while count < 5:
    print(count)
    count += 1
```

### Input Validation with while Loops

```python
rating = input("Enter a rating (1-5): ")
while not rating.isdigit() or not (1 <= int(rating) <= 5):
    print("Invalid rating. Please enter a number between 1 and 5.")
    rating = input("Enter a rating (1-5): ")
```

### Infinite Loops (e.g., Game Loops)

```python
dollars = 100
while True:
    action = input("What do you want to buy (shirt or hat)? ").lower()
    if action == "shirt":
        if dollars < 30:
            print("Not enough money!")
            continue
        dollars -= 30
        print("You bought a shirt!")
    elif action == "hat":
        if dollars < 10:
            print("Not enough money!")
            continue
        dollars -= 10
        print("You bought a hat!")
    else:
        print("Invalid item!")

    if dollars < 10:
        print("You're broke!")
        break

    print(f"You have ${dollars} remaining.")
```

### Limited Attempts

```python
attempts = 3
while attempts > 0:
    guess = input("Enter your guess: ")
    if guess == "correct":
        print("Correct!")
        break
    attempts -= 1
    print(f"Incorrect. {attempts} attempt(s) remaining.")
```

---

## 6. Functions

Functions are reusable blocks of code.

### Defining and Calling Functions

```python
def greet(name):
    print(f"Hello, {name}!")

greet("Alice")  # Output: Hello, Alice!
```

### Parameters, Arguments, and Return Values

```python
def add(a, b):
    return a + b

result = add(5, 3)  # result is 8
```

### Extending Functions

```python
def greet(name, time_of_day):
    print(f"Good {time_of_day}, {name}!")

greet("Alice", "morning")  # Output: Good morning, Alice!
```

---

## 7. Lists

Lists are ordered, mutable collections.

### Creating and Accessing Lists

```python
numbers = [1, 2, 3, 4, 5]
print(numbers[0])   # First element
print(numbers[-1])  # Last element
```

### Modifying Lists

- **Append:**

  ```python
  numbers.append(6)
  ```

- **Remove:**

  ```python
  numbers.remove(3)  # Removes the first occurrence of 3
  ```

### Useful List Functions

```python
total = sum(numbers)
count = len(numbers)
smallest = min(numbers)
largest = max(numbers)
```

---

## 8. Random Number Generation

Use the `random` module to generate random values.

### Importing the Module

```python
import random
```

### Generating Random Numbers

- **Random Integer (inclusive):**

  ```python
  n = random.randint(1, 10)
  ```

- **Random Float (0 to 1):**

  ```python
  f = random.random()
  ```

### Random Choices and Shuffling

- **Random Element:**

  ```python
  fruits = ['apple', 'banana', 'cherry']
  choice = random.choice(fruits)
  ```

- **Shuffle a List:**

  ```python
  random.shuffle(fruits)
  ```

- **Shuffle a String:**

  ```python
  word = "hello"
  letters = list(word)
  random.shuffle(letters)
  shuffled_word = ''.join(letters)
  ```

---

## 9. String Manipulation

Strings are sequences of characters.

### Common String Methods

- **Lowercase:**

  ```python
  text = "Hello".lower()  # "hello"
  ```

- **Uppercase:**

  ```python
  text = "Hello".upper()  # "HELLO"
  ```

- **Alphabet Check:**

  ```python
  print("Hello".isalpha())  # True
  ```

- **Digit Check:**

  ```python
  print("123".isdigit())    # True
  ```

- **Split into a List:**

  ```python
  words = "This is a test".split()  # ['This', 'is', 'a', 'test']
  ```

- **Trim Whitespace:**

  ```python
  text = "  Hello  ".strip()  # "Hello"
  ```

### Joining Strings

```python
words = ['Join', 'these', 'words']
sentence = ' '.join(words)  # "Join these words"
```

### Iterating Over Characters

```python
for char in "Hello":
    print(char)
```

---

## 10. Input Validation

Ensure user input meets required criteria.

### Checking for Empty Input

```python
user_input = input("Enter something: ")
if not user_input:
    print("No input provided!")
```

### Validating Alphabetic Input

```python
word = input("Enter a word: ")
if word.isalpha():
    print("Valid input!")
else:
    print("Please use letters only.")
```

### Looping Until Valid Input

```python
while True:
    guess = input("Enter your guess (letters only): ")
    if guess.isalpha():
        break
    print("Invalid input. Try again.")
```

---

## 11. Additional Concepts

### Membership with `in` and `not in`

Check if an item exists in a sequence:

```python
vowels = "aeiou"
letter = input("Enter a letter: ")
if letter in vowels:
    print("It's a vowel.")
else:
    print("It's not a vowel.")
```
