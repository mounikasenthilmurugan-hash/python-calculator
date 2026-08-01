# python-calculator# ============================================
# Simple Calculator Application
# Author: Written for a beginner Python learner
# ============================================

# ---- FUNCTION DEFINITIONS ----
# Each function below handles ONE operation.
# Keeping operations in separate functions makes the
# code reusable, organized, and easy to test.

def add(a, b):
    # Returns the sum of two numbers
    return a + b


def subtract(a, b):
    # Returns the difference of two numbers
    return a - b


def multiply(a, b):
    # Returns the product of two numbers
    return a * b


def divide(a, b):
    # Returns the division result of two numbers
    # We must check for division by zero, since dividing by
    # zero is mathematically undefined and crashes the program
    if b == 0:
        # Instead of crashing, we return a friendly error message
        return "Error: Division by zero is not allowed."
    return a / b


def get_number(prompt):
    # This helper function safely takes numeric input from the user.
    # It keeps asking until the user enters a valid number.
    while True:  # Loop forever until a valid number is entered
        user_input = input(prompt)  # Ask the user for input
        try:
            # Try converting the input to a float (handles decimals too)
            return float(user_input)
        except ValueError:
            # This runs if conversion fails (e.g., user typed "abc")
            print("Invalid input! Please enter a valid number.")


def show_menu():
    # Displays the calculator menu to the user
    print("\n===== CALCULATOR MENU =====")
    print("1. Add")
    print("2. Subtract")
    print("3. Multiply")
    print("4. Divide")
    print("5. Exit")
    print("============================")


# ---- MAIN PROGRAM LOOP ----
# This is the core loop that keeps the calculator running
# until the user chooses to exit.

while True:  # Infinite loop, broken only when user selects Exit
    show_menu()  # Display the menu every time

    choice = input("Enter your choice (1-5): ")  # Get the user's menu choice

    # Check if the user wants to exit
    if choice == "5":
        print("Thank you for using the calculator. Goodbye!")
        break  # Exits the while loop, ending the program

    # Validate that the choice is one of the expected menu options
    if choice not in ("1", "2", "3", "4"):
        print("Invalid choice! Please select a number between 1 and 5.")
        continue  # Skips the rest of the loop and shows the menu again

    # If we reach here, the choice is valid (1-4), so we ask for two numbers
    num1 = get_number("Enter the first number: ")
    num2 = get_number("Enter the second number: ")

    # Call the correct function based on the user's choice
    if choice == "1":
        result = add(num1, num2)
        symbol = "+"
    elif choice == "2":
        result = subtract(num1, num2)
        symbol = "-"
    elif choice == "3":
        result = multiply(num1, num2)
        symbol = "*"
    elif choice == "4":
        result = divide(num1, num2)
        symbol = "/"

    # Display the result to the user
    print(f"\nResult: {num1} {symbol} {num2} = {result}")

# 🧮 Simple Python Calculator

A beginner-friendly command-line calculator built in Python. Supports addition, subtraction, multiplication, and division with proper input validation and error handling.

## ✨ Features

- ➕ Add, ➖ Subtract, ✖️ Multiply, ➗ Divide
- Menu-driven interface with a `while` loop that runs until you exit
- Handles invalid (non-numeric) input gracefully
- Handles division by zero without crashing
- Clean, fully commented code — great for beginners learning Python

## 🛠️ Tech Stack

- Python 3

## 📸 Demo

```
===== CALCULATOR MENU =====
1. Add
2. Subtract
3. Multiply
4. Divide
5. Exit
============================
Enter your choice (1-5): 1
Enter the first number: 10
Enter the second number: 5

Result: 10.0 + 5.0 = 15.0
```

## 🚀 Getting Started

### Prerequisites
- Python 3.x installed on your machine

### Run it

```bash
git clone https://github.com/your-username/simple-python-calculator.git
cd simple-python-calculator
python calculator.py
```

## 📂 Project Structure

```
simple-python-calculator/
├── calculator.py    # Main program
└── README.md        # Project documentation
```

## 🧠 How It Works

- Each operation (`add`, `subtract`, `multiply`, `divide`) is its own function
- `get_number()` safely handles user input using `try/except`
- The main `while True` loop shows the menu repeatedly until the user selects **Exit**
- Invalid menu choices are caught and re-prompted using `continue`
- Division by zero returns a friendly error message instead of crashing

## 🔮 Future Improvements

- [ ] Add calculation history
- [ ] Support multi-step expressions (e.g., `5 + 3 * 2`)
- [ ] Add a simple GUI using Tkinter

## 📝 License

This project is open source and available under the [MIT License](LICENSE).

## 👤 Author

**Mounika Senthilmurugan**
B.Tech AIDS | Data Analytics Intern | Aspiring AI Developer

[LinkedIn](https://linkedin.com) · [GitHub](https://github.com)
