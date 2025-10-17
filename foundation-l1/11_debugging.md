# Debugging 🐛
## Finding and Fixing Errors in Your Programs

### Learning Objectives
By the end of this lesson, students will:
- Understand what debugging is and why it's important
- Identify common types of errors in Python
- Use debugging techniques to find and fix errors
- Write better code that's easier to debug

---

## What is Debugging? 🤔

**Debugging is the process of finding and fixing errors (bugs) in your programs!**

Think of debugging as:
- **Detective work** - finding clues to solve mysteries
- **Problem solving** - figuring out what went wrong
- **Learning opportunity** - understanding how your code works

### Real-World Analogy: Fixing a Car
- **Problem**: Car won't start
- **Investigation**: Check battery, fuel, engine
- **Solution**: Replace dead battery
- **Prevention**: Regular maintenance

---

## Types of Errors 🚨

### 1. Syntax Errors (Grammar Mistakes)
**These prevent your program from running at all!**

```python
# ❌ Syntax Error Examples
print("Hello World"  # Missing closing parenthesis
if x = 5:            # Using = instead of ==
for i in range(5)    # Missing colon
    print(i)

# ✅ Corrected
print("Hello World")
if x == 5:
    print("x is 5")
for i in range(5):
    print(i)
```

### 2. Runtime Errors (Logic Mistakes)
**These happen while your program is running!**

```python
# ❌ Runtime Error Examples
x = 10
y = 0
result = x / y  # ZeroDivisionError

numbers = [1, 2, 3]
print(numbers[5])  # IndexError

name = input("Enter your name: ")
age = int(name)  # ValueError if name isn't a number

# ✅ Corrected
x = 10
y = 0
if y != 0:
    result = x / y
else:
    print("Cannot divide by zero!")

numbers = [1, 2, 3]
if len(numbers) > 5:
    print(numbers[5])
else:
    print("Index out of range!")

name = input("Enter your name: ")
try:
    age = int(name)
except ValueError:
    print("Please enter a valid number!")
```

### 3. Logic Errors (Wrong Results)
**These make your program give wrong answers!**

```python
# ❌ Logic Error Example
def calculate_average(numbers):
    total = 0
    for num in numbers:
        total += num
    return total / len(numbers)  # Wrong! Should check if list is empty

# ✅ Corrected
def calculate_average(numbers):
    if len(numbers) == 0:
        return 0  # Handle empty list
    total = 0
    for num in numbers:
        total += num
    return total / len(numbers)
```

---

## Debugging Techniques 🔍

### 1. Print Statements (The Simplest Method)
**Add print statements to see what's happening!**

```python
def find_largest(numbers):
    print(f"Input numbers: {numbers}")  # Debug print
    
    if not numbers:
        print("List is empty!")  # Debug print
        return None
    
    largest = numbers[0]
    print(f"Starting with: {largest}")  # Debug print
    
    for i, num in enumerate(numbers):
        print(f"Checking {num} at index {i}")  # Debug print
        if num > largest:
            largest = num
            print(f"New largest: {largest}")  # Debug print
    
    print(f"Final result: {largest}")  # Debug print
    return largest

# Test the function
numbers = [3, 7, 2, 9, 1]
result = find_largest(numbers)
print(f"Largest number: {result}")
```

### 2. Step-by-Step Execution
**Trace through your code line by line!**

```python
def mystery_function(x, y):
    print(f"Step 1: x = {x}, y = {y}")
    
    if x > y:
        print("Step 2: x > y is True")
        result = x - y
        print(f"Step 3: result = {x} - {y} = {result}")
    else:
        print("Step 2: x > y is False")
        result = x + y
        print(f"Step 3: result = {x} + {y} = {result}")
    
    print(f"Step 4: returning {result}")
    return result

# Test with different values
print("Testing with x=5, y=3:")
mystery_function(5, 3)

print("\nTesting with x=2, y=7:")
mystery_function(2, 7)
```

### 3. Check Your Assumptions
**Make sure your assumptions are correct!**

```python
def divide_numbers(a, b):
    print(f"Dividing {a} by {b}")
    
    # Check assumptions
    if not isinstance(a, (int, float)):
        print(f"Error: {a} is not a number!")
        return None
    
    if not isinstance(b, (int, float)):
        print(f"Error: {b} is not a number!")
        return None
    
    if b == 0:
        print("Error: Cannot divide by zero!")
        return None
    
    result = a / b
    print(f"Result: {a} / {b} = {result}")
    return result

# Test with different inputs
divide_numbers(10, 2)
divide_numbers(10, 0)
divide_numbers("10", 2)
```

---

## Real-World Debugging Examples 🌟

### Example 1: Shopping Cart Bug
```python
print("🛒 Shopping Cart Debugging 🛒")

def calculate_total(items, prices):
    print(f"Items: {items}")
    print(f"Prices: {prices}")
    
    if len(items) != len(prices):
        print("Error: Number of items doesn't match number of prices!")
        return None
    
    total = 0
    for i in range(len(items)):
        print(f"Adding {items[i]}: ${prices[i]}")
        total += prices[i]
    
    print(f"Total: ${total}")
    return total

# Test the function
items = ["apple", "banana", "orange"]
prices = [1.50, 0.75, 2.00]

total = calculate_total(items, prices)
print(f"Final total: ${total}")

# Test with error
print("\nTesting with error:")
items_with_error = ["apple", "banana"]
prices_with_error = [1.50, 0.75, 2.00]  # Extra price

total_with_error = calculate_total(items_with_error, prices_with_error)
```
### Programming Spirit
When you find yourself stuck and debugging for an extended period, remember to take breaks. Step away from your computer, go for a walk, stay hydrated, and return to the problem with fresh eyes. This approach often leads to new insights and solutions.           

### Example 2: Grade Calculator Bug
```python
print("📊 Grade Calculator Debugging 📊")

def calculate_grade(score):
    print(f"Calculating grade for score: {score}")
    
    # Check if score is valid
    if not isinstance(score, (int, float)):
        print("Error: Score must be a number!")
        return None
    
    if score < 0 or score > 100:
        print("Error: Score must be between 0 and 100!")
        return None
    
    # Calculate grade
    if score >= 90:
        grade = "A"
    elif score >= 80:
        grade = "B"
    elif score >= 70:
        grade = "C"
    elif score >= 60:
        grade = "D"
    else:
        grade = "F"
    
    print(f"Grade: {grade}")
    return grade

# Test with different scores
scores = [95, 85, 75, 65, 55, -10, 150, "not a number"]

for score in scores:
    print(f"\nTesting score: {score}")
    grade = calculate_grade(score)
    if grade:
        print(f"Result: {grade}")
```

### Example 3: Password Validator Bug
```python
print("🔐 Password Validator Debugging 🔐")

def validate_password(password):
    print(f"Validating password: {password}")
    
    # Check if password is string
    if not isinstance(password, str):
        print("Error: Password must be a string!")
        return False
    
    # Check length
    if len(password) < 8:
        print("Error: Password must be at least 8 characters long!")
        return False
    
    # Check for uppercase
    has_upper = any(c.isupper() for c in password)
    print(f"Has uppercase: {has_upper}")
    if not has_upper:
        print("Error: Password must contain at least one uppercase letter!")
        return False
    
    # Check for lowercase
    has_lower = any(c.islower() for c in password)
    print(f"Has lowercase: {has_lower}")
    if not has_lower:
        print("Error: Password must contain at least one lowercase letter!")
        return False
    
    # Check for digit
    has_digit = any(c.isdigit() for c in password)
    print(f"Has digit: {has_digit}")
    if not has_digit:
        print("Error: Password must contain at least one digit!")
        return False
    
    print("Password is valid!")
    return True

# Test with different passwords
passwords = [
    "Password123",  # Valid
    "password123",  # No uppercase
    "PASSWORD123",  # No lowercase
    "Password",     # No digit
    "Pass1",        # Too short
    "",             # Empty
    12345           # Not a string
]

for password in passwords:
    print(f"\nTesting password: {password}")
    is_valid = validate_password(password)
    print(f"Valid: {is_valid}")
```

---

## Interactive Debugging Examples 🎮

### Example 1: Number Guessing Game Debug
```python
print("🎯 Number Guessing Game Debug 🎯")

import random

def play_guessing_game():
    secret_number = random.randint(1, 100)
    print(f"DEBUG: Secret number is {secret_number}")  # Debug info
    
    guesses = 0
    max_guesses = 7
    
    print("I'm thinking of a number between 1 and 100!")
    print("You have 7 guesses. Good luck!")
    
    while guesses < max_guesses:
        print(f"\nGuess {guesses + 1}/{max_guesses}")
        
        try:
            guess = int(input("Enter your guess: "))
            print(f"DEBUG: You guessed {guess}")  # Debug info
            
            guesses += 1
            
            if guess == secret_number:
                print("🎉 Congratulations! You guessed it!")
                print(f"It took you {guesses} guesses!")
                return True
            elif guess < secret_number:
                print("Too low! Try higher.")
                print(f"DEBUG: Secret number is higher than {guess}")  # Debug info
            else:
                print("Too high! Try lower.")
                print(f"DEBUG: Secret number is lower than {guess}")  # Debug info
                
        except ValueError:
            print("Error: Please enter a valid number!")
            print("DEBUG: Invalid input received")  # Debug info
            guesses -= 1  # Don't count invalid guesses
    
    print(f"😞 Game over! The number was {secret_number}")
    return False

# Play the game
play_guessing_game()
```

### Example 2: Calculator Debug
```python
print("🧮 Calculator Debug 🧮")

def safe_divide(a, b):
    print(f"DEBUG: Attempting to divide {a} by {b}")
    
    # Check if inputs are numbers
    if not isinstance(a, (int, float)):
        print(f"DEBUG: {a} is not a number!")
        return None
    
    if not isinstance(b, (int, float)):
        print(f"DEBUG: {b} is not a number!")
        return None
    
    # Check for division by zero
    if b == 0:
        print("DEBUG: Division by zero detected!")
        return None
    
    result = a / b
    print(f"DEBUG: {a} / {b} = {result}")
    return result

def calculator():
    while True:
        print("\nCalculator Menu:")
        print("1. Add")
        print("2. Subtract")
        print("3. Multiply")
        print("4. Divide")
        print("5. Exit")
        
        choice = input("Enter your choice (1-5): ")
        print(f"DEBUG: User chose option {choice}")
        
        if choice == "5":
            print("Goodbye!")
            break
        
        if choice in ["1", "2", "3", "4"]:
            try:
                num1 = float(input("Enter first number: "))
                num2 = float(input("Enter second number: "))
                print(f"DEBUG: Numbers entered: {num1}, {num2}")
                
                if choice == "1":
                    result = num1 + num2
                    print(f"Result: {num1} + {num2} = {result}")
                elif choice == "2":
                    result = num1 - num2
                    print(f"Result: {num1} - {num2} = {result}")
                elif choice == "3":
                    result = num1 * num2
                    print(f"Result: {num1} × {num2} = {result}")
                elif choice == "4":
                    result = safe_divide(num1, num2)
                    if result is not None:
                        print(f"Result: {num1} ÷ {num2} = {result}")
                    else:
                        print("Error: Cannot divide by zero!")
                        
            except ValueError:
                print("Error: Please enter valid numbers!")
                print("DEBUG: Invalid number input received")
        else:
            print("Invalid choice! Please try again.")
            print(f"DEBUG: Invalid choice '{choice}' received")

# Run the calculator
calculator()
```

### Example 3: Data Processing Debug
```python
print("📊 Data Processing Debug 📊")

def process_student_data(data):
    print(f"DEBUG: Processing data: {data}")
    
    if not isinstance(data, list):
        print("DEBUG: Data is not a list!")
        return None
    
    if len(data) == 0:
        print("DEBUG: Data list is empty!")
        return None
    
    results = []
    
    for i, student in enumerate(data):
        print(f"DEBUG: Processing student {i + 1}: {student}")
        
        if not isinstance(student, dict):
            print(f"DEBUG: Student {i + 1} is not a dictionary!")
            continue
        
        if "name" not in student:
            print(f"DEBUG: Student {i + 1} missing 'name' field!")
            continue
        
        if "scores" not in student:
            print(f"DEBUG: Student {i + 1} missing 'scores' field!")
            continue
        
        if not isinstance(student["scores"], list):
            print(f"DEBUG: Student {i + 1} scores is not a list!")
            continue
        
        if len(student["scores"]) == 0:
            print(f"DEBUG: Student {i + 1} has no scores!")
            continue
        
        # Calculate average
        total = 0
        for score in student["scores"]:
            if not isinstance(score, (int, float)):
                print(f"DEBUG: Invalid score {score} for student {student['name']}")
                continue
            total += score
        
        average = total / len(student["scores"])
        print(f"DEBUG: {student['name']} average: {average}")
        
        results.append({
            "name": student["name"],
            "average": average
        })
    
    print(f"DEBUG: Processed {len(results)} students")
    return results

# Test with sample data
sample_data = [
    {"name": "Alice", "scores": [85, 90, 78]},
    {"name": "Bob", "scores": [92, 88, 95]},
    {"name": "Charlie", "scores": []},  # Empty scores
    {"name": "Diana", "scores": [75, 80, "invalid"]},  # Invalid score
    "Not a student",  # Not a dictionary
    {"name": "Eve"},  # Missing scores
    {"scores": [90, 85]},  # Missing name
]

results = process_student_data(sample_data)
if results:
    print("\nResults:")
    for result in results:
        print(f"{result['name']}: {result['average']:.2f}")
```

---

## Common Debugging Mistakes (And How to Fix Them!) ❌➡️✅

### Mistake 1: Not Reading Error Messages
```python
# ❌ Wrong - Ignoring error messages
numbers = [1, 2, 3]
print(numbers[5])  # IndexError: list index out of range

# ✅ Correct - Read and understand error messages
numbers = [1, 2, 3]
try:
    print(numbers[5])
except IndexError as e:
    print(f"Error: {e}")
    print("The list only has 3 elements (indices 0-2)")
    print(f"Available indices: 0 to {len(numbers) - 1}")
```

### Mistake 2: Not Testing Edge Cases
```python
# ❌ Wrong - Only testing normal cases
def divide(a, b):
    return a / b

print(divide(10, 2))  # Works fine

# ✅ Correct - Test edge cases
def divide(a, b):
    if b == 0:
        return "Cannot divide by zero!"
    return a / b

print(divide(10, 2))    # Normal case
print(divide(10, 0))    # Edge case
print(divide(0, 5))     # Edge case
print(divide(-10, 2))   # Edge case
```

### Mistake 3: Not Using Debug Prints
```python
# ❌ Wrong - No debugging information
def find_max(numbers):
    max_num = numbers[0]
    for num in numbers:
        if num > max_num:
            max_num = num
    return max_num

# ✅ Correct - Add debug information
def find_max(numbers):
    print(f"Input: {numbers}")
    max_num = numbers[0]
    print(f"Starting max: {max_num}")
    
    for i, num in enumerate(numbers):
        print(f"Checking {num} at index {i}")
        if num > max_num:
            max_num = num
            print(f"New max: {max_num}")
    
    print(f"Final max: {max_num}")
    return max_num
```

---

## Fun Debugging Challenges! 🎯

### Challenge 1: Bug Hunt
Find and fix the bugs in this code:

```python
print("🐛 Bug Hunt Challenge 🐛")

def buggy_calculator(a, b, operation):
    if operation == "add":
        return a + b
    elif operation == "subtract":
        return a - b
    elif operation == "multiply":
        return a * b
    elif operation == "divide":
        return a / b
    else:
        return "Invalid operation"

# Test the function
print("Testing add:", buggy_calculator(5, 3, "add"))
print("Testing subtract:", buggy_calculator(5, 3, "subtract"))
print("Testing multiply:", buggy_calculator(5, 3, "multiply"))
print("Testing divide:", buggy_calculator(5, 3, "divide"))
print("Testing divide by zero:", buggy_calculator(5, 0, "divide"))
print("Testing invalid:", buggy_calculator(5, 3, "power"))

# Can you find the bugs? Fix them!
```

### Challenge 2: Debug the Grade System
Find and fix the bugs in this grade system:

```python
print("📚 Grade System Debug Challenge 📚")

def calculate_grade(score):
    if score >= 90:
        return "A"
    elif score >= 80:
        return "B"
    elif score >= 70:
        return "C"
    elif score >= 60:
        return "D"
    else:
        return "F"

def process_students(students):
    results = []
    for student in students:
        name = student["name"]
        score = student["score"]
        grade = calculate_grade(score)
        results.append({"name": name, "score": score, "grade": grade})
    return results

# Test data
students = [
    {"name": "Alice", "score": 95},
    {"name": "Bob", "score": 85},
    {"name": "Charlie", "score": 75},
    {"name": "Diana", "score": 65},
    {"name": "Eve", "score": 55},
    {"name": "Frank", "score": 105},  # What happens with this?
    {"name": "Grace", "score": -10},  # What about this?
]

results = process_students(students)
for result in results:
    print(f"{result['name']}: {result['score']} -> {result['grade']}")

# Can you find the bugs? Fix them!
```

### Challenge 3: Debug the Password Checker
Find and fix the bugs in this password checker:

```python
print("🔐 Password Checker Debug Challenge 🔐")

def check_password(password):
    if len(password) < 8:
        return False
    
    has_upper = False
    has_lower = False
    has_digit = False
    
    for char in password:
        if char.isupper():
            has_upper = True
        if char.islower():
            has_lower = True
        if char.isdigit():
            has_digit = True
    
    return has_upper and has_lower and has_digit

# Test passwords
passwords = [
    "Password123",  # Should be valid
    "password123",  # Should be invalid (no uppercase)
    "PASSWORD123",  # Should be invalid (no lowercase)
    "Password",     # Should be invalid (no digit)
    "Pass1",        # Should be invalid (too short)
    "",             # Should be invalid (empty)
    "Pass123",      # Should be valid
]

for password in passwords:
    is_valid = check_password(password)
    print(f"'{password}': {'Valid' if is_valid else 'Invalid'}")

# Can you find the bugs? Fix them!
```

---

## What's Next? 🚀

You've learned how to debug your programs and find errors! Now you can:
- Identify and fix different types of errors
- Use debugging techniques to solve problems
- Write more reliable code

**In the next lesson, you'll learn:**
- How to create functions to organize your code
- How to make your programs more modular and reusable
- How to build complex programs step by step!

---

## Practice Time! 💪

**Try these exercises:**

1. **Create a program with intentional bugs and practice fixing them**
2. **Make a program that handles errors gracefully**
3. **Build a program that validates user input**
4. **Design a program that logs debug information**

**Remember:** Debugging is a skill that improves with practice!

---

## Fun Facts! 🎉

- **The term "bug"** comes from a real bug found in a computer in 1947!
- **Debugging takes up** 50-90% of programming time!
- **Good debugging skills** make you a better programmer!
- **Every programmer** makes mistakes - it's part of learning!

---

## Discussion Questions 💭

1. **What was the most challenging bug you had to fix?**
2. **How do you think debugging helps you become a better programmer?**
3. **What debugging techniques do you find most helpful?**

---

## Next Up: Functions! 🔧

In the next lesson, you'll learn how to create functions to organize your code and make it reusable!

**Keep debugging and learning!** 🎉

