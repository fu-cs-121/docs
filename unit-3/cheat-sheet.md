# Final Exam: Cheat Sheet

This cheat sheet is designed to help you recall key Python concepts you'll need for your final exam. It's divided by units, with important concepts and code snippets for each task.

Hint: Pay special attention to code comments starting with `# TODO`

---

## Unit 1: Pet Card

In this unit, you'll create a function to print a pet card with the pet's name and an emoji based on its species.

#### **Defining a Function with Parameters**

```python
def print_card(name, species):
    # Code to print the pet card
```

- Start a function with `def`, followed by the function name and parameters in parentheses.
- Indent the code inside the function.

#### **Printing Horizontal Lines**

```python
print('-' * 20)  # Prints a line of 20 hyphens
```

- Multiply a string by a number to repeat it.
- Useful for creating separators or lines.

#### **Centering Text in a Given Width**

```python
text = "😺 Whiskers"
centered_text = text.center(20)
print(centered_text)
```

- Use `.center(width)` to center a string within a specified width.
- Pads the text with spaces on both sides.

#### **Combining Variables and Strings**

```python
print(f"{emoji} {name}")
```

- Use f-strings (`f"..."`) to embed variables directly in strings. Place variables inside `{}`.

#### **Prompting for User Input**

```python
species = input("Enter pet type (cat or dog): ")
name = input("Enter pet name: ")
```

- `input()` displays a prompt and waits for the user to type a response.
- The response is stored as a string variable.

#### **Using Conditional Statements (if needed)**

```python
if species == 'cat':
    emoji = '😺'
elif species == 'dog':
    # TODO: set emoji to the dog emojiy (🐶)
```

- Use `if`, `elif`, and `else` to handle different cases.
- Assign the appropriate emoji based on the species.

---

<div style="page-break-after: always;"></div>

## Unit 2: Virtual Pet Simulator

In this unit, you'll create a simple simulator where a virtual pet has hunger, happiness, and energy levels.

#### Creating a Dictionary

```python
pet = {
    "name": "",
    "hunger": 5,
    # TODO:Add happiness and energy levels
}
```

- Dictionary keys are strings, and values can be any data type. Access values with `pet["key"]`.

#### Assigning a Value from User Input

```python
pet["name"] = input("What is your pet's name? ")
```

- Assign the user's input directly to a dictionary key.

#### Creating an Infinite Loop

```python
while True:
    # Code that repeats indefinitely
```

- Use `break` to exit the loop when needed.

#### Displaying the Pet's Status

```python
print(f'{pet["name"]} has {pet["hunger"]} hunger, ...etc.')
```

- Use f-strings to neatly display multiple variables.

#### Prompting for an Action

```python
action = input("What would you like to do (feed, play, rest, or quit)? ").lower()
```

- Convert input to lowercase to make comparison easier.

#### Handling User Actions with Conditionals

```python
if action == "feed":
    pet["hunger"] -= 1
elif action == "play":
    # TODO: Update happiness level
elif action == "rest":
    # TODO: Update energy level
elif action == "quit":
    print("Goodbye!")
    # TODO: exit the loop (hint: use `break`)
else:
    print("Invalid input. Please enter 'feed', 'play', 'rest', or 'quit'.")
    # TODO: skip back to the top of the loop (hint: use `continue`)
```

- Subtract or add to the pet's attributes based on the action.

#### Updating Numerical Values in a Dictionary

```python
pet["hunger"] -= 1  # Decreases hunger by 1
```

- Use `+=` to increase and `-=` to decrease numeric values.

---

<div style="page-break-after: always;"></div>

## Unit 3: Pet Shelter

In this unit, you'll work with classes and file input to manage a collection of pets in a shelter.

#### Defining a Class

```python
class Pet:
    def __init__(self, name, species, birth_year):
        self.name = name
        # TODO: assign other attributes
```

- Use `class` to define a new class.
- The `__init__` method initializes object attributes.

#### Adding a Method to a Class

```python
def print_info(self):
    print(f'{self.name} the {self.species}, born in {self.birth_year}')
```

- Define methods to perform actions using the object's data.
- `self` refers to the instance of the class.

#### Creating a Shelter Class

```python
class Shelter:
    def __init__(self):
        # Initialize an empty list to store pets
        self.pets = []
```

- Initialize a list to store pet objects.

#### Loading Pets from a File

```python
def load_pets(self, filename):
    with open(filename, 'r') as f:
        f.readline()  # Skip the header line
        for line in f:
            name, species, birth_year = line.strip().split(',')
            # TODO: Create a new Pet instance using the `Pet` class
            # TODO: Add the pet to `self.pets`

```

- Use `with open()` to read from a file.
- `f.readline()` skips the header line.
- `line.strip().split(',')` splits the line into parts.

#### Printing All Pets

```python
def print_pets(self):
    for pet in self.pets:
        pet.print_info()
```

- Loop through the list of pets and call their `print_info` method.

#### Using the Shelter Class

```python
shelter = Shelter()
shelter.load_pets("pets.csv")
shelter.print_pets()
```

- Create an instance of `Shelter`.
- Load pet data from a file.
- Display information about all pets.
