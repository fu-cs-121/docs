# Simple Python Testing with Assertions

Testing your code is an essential practice that helps ensure your programs work as expected. In this tutorial, we'll learn how to use **assertions** to test Python classes and methods in a beginner-friendly way.

## What Are Assertions?

An `assert` statement in Python checks if a condition is `True`. If the condition is `False`, an `AssertionError` is raised. This is useful for testing because it immediately tells you when something is wrong.

### Example of an `assert` Statement

```python
# Example of an assertion
x = 5
assert x == 5, "x should be equal to 5"  # This passes and does nothing

assert x == 10, "x should be equal to 10"  # This raises an AssertionError
```

If the condition in the `assert` statement fails (i.e., it evaluates to `False`), Python will raise an `AssertionError` with the optional error message.

---

## Step-by-Step Guide to Writing Tests

Let’s say we have a simple class called `BankAccount` that manages deposits and withdrawals:

### 1. Define Your Business Logic Class

Create a file named `bank_account.py` with the following code:

```python
# bank_account.py

class BankAccount:
    def __init__(self, initial_balance=0):
        self.balance = initial_balance

    def deposit(self, amount):
        self.balance += amount

    def withdraw(self, amount):
        if amount > self.balance:
            raise ValueError("Insufficient funds")
        self.balance -= amount

    def get_balance(self):
        return self.balance
```

### 2. Write Tests Using Assertions

Create a new file named `tests.py` to write your tests.

```python
# tests.py

from bank_account import BankAccount

def test_bank_account():
    # Test creating a new account with an initial balance
    account = BankAccount(100)
    assert account.get_balance() == 100, "Initial balance should be 100"

    # Test depositing money
    account.deposit(50)
    assert account.get_balance() == 150, "Balance should be 150 after deposit"

    # Test withdrawing money
    account.withdraw(30)
    assert account.get_balance() == 120, "Balance should be 120 after withdrawal"

    # Test withdrawing more than the balance
    try:
        account.withdraw(200)
    except ValueError:
        pass  # Test passed because the exception was raised
    else:
        assert False, "Expected ValueError when withdrawing more than the balance"

    print("All tests passed!")

# Run the tests
if __name__ == "__main__":
    test_bank_account()
```

### 3. Explanation of the `tests.py` File

- **Importing Your Class**: We import `BankAccount` from `bank_account.py` to test its functionality.
- **Writing Tests**: We define a function called `test_bank_account()` and use `assert` statements to check if the methods of `BankAccount` are working correctly.
- **Handling Exceptions**: We use a `try-except` block to test if withdrawing more money than available raises a `ValueError`. If it does, the test passes. Otherwise, we raise an `AssertionError`.
- **Running the Tests**: The `if __name__ == "__main__":` block ensures that `test_bank_account()` runs when we execute `tests.py` directly.

---

## Running Your Tests

1. Open a terminal or command prompt.
2. Navigate to the directory where `tests.py` is located.
3. Run the file using Python:
   ```bash
   python tests.py
   ```

If all tests pass, you will see:

```
All tests passed!
```

If a test fails, Python will raise an `AssertionError` with the message you provided, helping you quickly identify what went wrong.

---

## Best Practices for Simple Testing

1. **Organize Tests in Separate Files**: Keeping your tests in a separate file, like `tests.py`, makes your project more organized.
2. **Use Descriptive Error Messages**: When writing `assert` statements, always include an error message. This makes debugging easier if a test fails.
3. **Test Different Scenarios**: Think of edge cases and potential errors. For example, test what happens when you try to withdraw more money than you have.
4. **Run Tests Often**: Make testing a regular part of your coding workflow to catch issues early.

---

This approach gives students a straightforward way to start testing their code, and they can easily extend it as they become more comfortable. Once they're ready for more advanced testing, they can transition to using frameworks like `unittest` or `pytest`.

Let me know if you need any more details or examples!
