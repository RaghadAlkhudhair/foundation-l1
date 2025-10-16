# Operators ➕➖✖️➗
## Doing Math with Your Variables

### Learning Objectives
By the end of this lesson, students will:
- Use arithmetic operators (+, -, *, /) with variables
- Understand operator precedence and order of operations
- Perform calculations in their programs
- Use comparison operators (==, !=, <, >, <=, >=)
- Apply logical operators (and, or, not)

---

## What are Operators? 🤔

**Operators are special symbols that tell Python what to do with your data!**

Think of operators as:
- **Math tools** for calculations
- **Comparison tools** for decisions
- **Logic tools** for complex thinking

### Real-World Analogy: Calculator Buttons
- **+ button** = Addition operator
- **- button** = Subtraction operator
- **× button** = Multiplication operator
- **÷ button** = Division operator

---

## Arithmetic Operators 🧮

### 1. Addition (+)
```python
# Basic addition
a = 5
b = 3
result = a + b
print("5 + 3 = " + str(result))  # Output: 5 + 3 = 8

# Adding variables
score = 100
bonus = 50
total_score = score + bonus
print("Total score: " + str(total_score))  # Output: Total score: 150
```

### 2. Subtraction (-)
```python
# Basic subtraction
money = 100
spent = 25
remaining = money - spent
print("Money left: $" + str(remaining))  # Output: Money left: $75

# Temperature change
current_temp = 85
temp_drop = 10
new_temp = current_temp - temp_drop
print("New temperature: " + str(new_temp) + "°F")  # Output: New temperature: 75°F
```

### 3. Multiplication (*)
```python
# Basic multiplication
length = 5
width = 3
area = length * width
print("Area: " + str(area) + " square units")  # Output: Area: 15 square units

# Calculating total cost
price_per_item = 2.50
quantity = 4
total_cost = price_per_item * quantity
print("Total cost: $" + str(total_cost))  # Output: Total cost: $10.0
```

### 4. Division (/)
```python
# Basic division
total_points = 100
number_of_tests = 4
average = total_points / number_of_tests
print("Average: " + str(average))  # Output: Average: 25.0

# Speed calculation
distance = 120
time = 2
speed = distance / time
print("Speed: " + str(speed) + " mph")  # Output: Speed: 60.0 mph
```

---

## Real-World Examples 🌟

### Example 1: Shopping Calculator
```python
print("🛒 Shopping Calculator 🛒")

# Get item information
item_name = input("What are you buying? ")
price = float(input("How much does it cost? $"))
quantity = int(input("How many do you want? "))
tax_rate = 0.08  # 8% tax

# Calculate costs
subtotal = price * quantity
tax_amount = subtotal * tax_rate
total = subtotal + tax_amount

# Display results
print("\n📄 Receipt:")
print("Item: " + item_name)
print("Price each: $" + str(price))
print("Quantity: " + str(quantity))
print("Subtotal: $" + str(subtotal))
print("Tax (8%): $" + str(tax_amount))
print("Total: $" + str(total))
```

### Example 2: Grade Calculator
```python
print("📊 Grade Calculator 📊")

# Get test scores
test1 = float(input("Test 1 score: "))
test2 = float(input("Test 2 score: "))
test3 = float(input("Test 3 score: "))
homework = float(input("Homework average: "))

# Calculate weighted average
test_average = (test1 + test2 + test3) / 3
final_grade = (test_average * 0.7) + (homework * 0.3)

# Display results
print("\n📈 Grade Report:")
print("Test Average: " + str(test_average))
print("Homework Average: " + str(homework))
print("Final Grade: " + str(final_grade))

if final_grade >= 90:
    print("Grade: A - Excellent!")
elif final_grade >= 80:
    print("Grade: B - Good job!")
elif final_grade >= 70:
    print("Grade: C - Keep trying!")
else:
    print("Grade: F - Study harder!")
```

### Example 3: Pizza Party Planner
```python
print("🍕 Pizza Party Planner 🍕")

# Get party information
num_people = int(input("How many people are coming? "))
slices_per_person = 3
slices_per_pizza = 8
cost_per_pizza = 12.99

# Calculate pizza needs
total_slices_needed = num_people * slices_per_person
pizzas_needed = total_slices_needed / slices_per_pizza
pizzas_to_order = int(pizzas_needed) + 1  # Round up
total_cost = pizzas_to_order * cost_per_pizza

# Display plan
print("\n🎉 Party Plan:")
print("People: " + str(num_people))
print("Slices needed: " + str(total_slices_needed))
print("Pizzas to order: " + str(pizzas_to_order))
print("Total cost: $" + str(total_cost))
print("Have a great party!")
```

---

## Comparison Operators 🔍

### What are Comparison Operators?
**They compare two values and return True or False!**

### 1. Equal (==)
```python
age = 16
can_drive = (age == 16)
print("Can drive: " + str(can_drive))  # Output: Can drive: True

# Check if passwords match
password1 = "mypassword123"
password2 = "mypassword123"
passwords_match = (password1 == password2)
print("Passwords match: " + str(passwords_match))  # Output: Passwords match: True
```

### 2. Not Equal (!=)
```python
favorite_color = "blue"
user_guess = "red"
correct_guess = (user_guess != favorite_color)
print("Wrong guess: " + str(correct_guess))  # Output: Wrong guess: True
```

### 3. Greater Than (>)
```python
score = 85
passing_grade = 70
passed = (score > passing_grade)
print("Passed: " + str(passed))  # Output: Passed: True
```

### 4. Less Than (<)
```python
temperature = 32
freezing_point = 32
is_cold = (temperature < freezing_point)
print("Is cold: " + str(is_cold))  # Output: Is cold: False
```

### 5. Greater Than or Equal (>=)
```python
age = 18
voting_age = 18
can_vote = (age >= voting_age)
print("Can vote: " + str(can_vote))  # Output: Can vote: True
```

### 6. Less Than or Equal (<=)
```python
items_in_cart = 5
max_items = 10
cart_ok = (items_in_cart <= max_items)
print("Cart is OK: " + str(cart_ok))  # Output: Cart is OK: True
```

---

## Logical Operators 🧠

### 1. AND (and)
```python
# Both conditions must be true
age = 16
has_license = True
can_drive = (age >= 16) and has_license
print("Can drive: " + str(can_drive))  # Output: Can drive: True

# Weather example
temperature = 75
is_sunny = True
perfect_weather = (temperature > 70) and is_sunny
print("Perfect weather: " + str(perfect_weather))  # Output: Perfect weather: True
```

### 2. OR (or)
```python
# At least one condition must be true
is_weekend = False
is_holiday = True
day_off = is_weekend or is_holiday
print("Day off: " + str(day_off))  # Output: Day off: True

# Grade example
test_score = 85
homework_score = 95
good_grade = (test_score >= 80) or (homework_score >= 90)
print("Good grade: " + str(good_grade))  # Output: Good grade: True
```

### 3. NOT (not)
```python
# Reverses the result
is_raining = False
is_sunny = not is_raining
print("Is sunny: " + str(is_sunny))  # Output: Is sunny: True

# Age check
age = 15
is_adult = not (age < 18)
print("Is adult: " + str(is_adult))  # Output: Is adult: False
```

---

## Fun Interactive Examples 🎮

### Example 1: Math Quiz Game
```python
print("🧮 Math Quiz Game 🧮")

# Generate random numbers
import random
num1 = random.randint(1, 10)
num2 = random.randint(1, 10)
operation = random.choice(['+', '-', '*'])

# Calculate correct answer
if operation == '+':
    correct_answer = num1 + num2
elif operation == '-':
    correct_answer = num1 - num2
else:
    correct_answer = num1 * num2

# Ask the question
print("What is " + str(num1) + " " + operation + " " + str(num2) + "?")
user_answer = int(input("Your answer: "))

# Check the answer
if user_answer == correct_answer:
    print("🎉 Correct! Great job!")
else:
    print("❌ Wrong! The answer was " + str(correct_answer))
```

### Example 2: Age-Based Recommendations
```python
print("🎯 Age-Based Recommendations 🎯")

age = int(input("How old are you? "))

# Age-based recommendations
if age < 13:
    print("You're a kid! Recommended activities:")
    print("- Play outside")
    print("- Read books")
    print("- Learn new things")
elif age < 18:
    print("You're a teenager! Recommended activities:")
    print("- Study hard")
    print("- Play sports")
    print("- Learn programming!")
else:
    print("You're an adult! Recommended activities:")
    print("- Get a job")
    print("- Pay bills")
    print("- Still learn programming!")

# Additional checks
can_vote = age >= 18
can_drive = age >= 16
can_work = age >= 14

print("\nYour privileges:")
print("Can vote: " + str(can_vote))
print("Can drive: " + str(can_drive))
print("Can work: " + str(can_work))
```

### Example 3: Weather Decision Maker
```python
print("🌤️ Weather Decision Maker 🌤️")

temperature = int(input("What's the temperature? "))
is_raining = input("Is it raining? (yes/no): ").lower() == "yes"
is_windy = input("Is it windy? (yes/no): ").lower() == "yes"

# Make recommendations
print("\n🌤️ Weather Recommendations:")

if temperature > 80 and not is_raining:
    print("☀️ Perfect beach weather! Go swimming!")
elif temperature > 70 and not is_raining:
    print("🌞 Great day for outdoor activities!")
elif temperature > 60:
    print("🌤️ Nice day for a walk or bike ride!")
elif temperature > 32:
    print("🧥 Cool day - wear a jacket!")
else:
    print("🥶 Very cold! Stay inside and drink hot chocolate!")

if is_raining:
    print("☔ It's raining - perfect day to read or play video games!")
if is_windy:
    print("💨 It's windy - be careful outside!")
```

---

## Operator Precedence 📊

### Order of Operations (PEMDAS)
1. **P**arentheses
2. **E**xponents
3. **M**ultiplication and **D**ivision (left to right)
4. **A**ddition and **S**ubtraction (left to right)

```python
# Example with different precedence
result1 = 2 + 3 * 4  # = 2 + 12 = 14
result2 = (2 + 3) * 4  # = 5 * 4 = 20

print("2 + 3 * 4 = " + str(result1))
print("(2 + 3) * 4 = " + str(result2))

# Complex calculation
total = 100 + (50 * 2) - (25 / 5)  # = 100 + 100 - 5 = 195
print("100 + (50 * 2) - (25 / 5) = " + str(total))
```

---

## Common Mistakes (And How to Fix Them!) ❌➡️✅

### Mistake 1: Using = Instead of ==
```python
# ❌ Wrong
age = 16
if age = 16:  # This is assignment, not comparison!
    print("You are 16")

# ✅ Correct
age = 16
if age == 16:  # This is comparison
    print("You are 16")
```

### Mistake 2: Forgetting to Convert Input to Numbers
```python
# ❌ Wrong
num1 = input("Enter first number: ")
num2 = input("Enter second number: ")
result = num1 + num2  # This concatenates strings!
print("Sum: " + result)  # Output: Sum: 12 (if user entered 1 and 2)

# ✅ Correct
num1 = int(input("Enter first number: "))
num2 = int(input("Enter second number: "))
result = num1 + num2  # This adds numbers!
print("Sum: " + str(result))  # Output: Sum: 3 (if user entered 1 and 2)
```

### Mistake 3: Wrong Operator for Division
```python
# ❌ Wrong
a = 10
b = 3
result = a / b
print("Result: " + str(int(result)))  # This truncates the decimal

# ✅ Correct
a = 10
b = 3
result = a / b
print("Result: " + str(result))  # This shows the decimal
```

---

## Fun Challenges! 🎯

### Challenge 1: Personal Finance Tracker
Create a program that tracks personal finances:

```python
print("💰 Personal Finance Tracker 💰")

# Get financial information
income = float(input("Monthly income: $"))
rent = float(input("Monthly rent: $"))
food = float(input("Monthly food expenses: $"))
entertainment = float(input("Monthly entertainment: $"))

# Calculate totals
total_expenses = rent + food + entertainment
savings = income - total_expenses
savings_percentage = (savings / income) * 100

# Display results
print("\n📊 Financial Summary:")
print("Income: $" + str(income))
print("Total Expenses: $" + str(total_expenses))
print("Savings: $" + str(savings))
print("Savings Percentage: " + str(savings_percentage) + "%")

if savings > 0:
    print("✅ You're saving money! Great job!")
else:
    print("❌ You're spending more than you earn. Time to budget!")
```

### Challenge 2: Fitness Calculator
Create a program that calculates fitness metrics:

```python
print("💪 Fitness Calculator 💪")

# Get user information
weight = float(input("Your weight (lbs): "))
height = float(input("Your height (inches): "))
age = int(input("Your age: "))
activity_level = input("Activity level (low/medium/high): ").lower()

# Calculate BMI
bmi = (weight / (height * height)) * 703

# Calculate daily calories (rough estimate)
if activity_level == "low":
    calories = weight * 15
elif activity_level == "medium":
    calories = weight * 17
else:
    calories = weight * 20

# Display results
print("\n📈 Fitness Report:")
print("BMI: " + str(round(bmi, 1)))
print("Daily Calories Needed: " + str(int(calories)))

if bmi < 18.5:
    print("Category: Underweight")
elif bmi < 25:
    print("Category: Normal weight")
elif bmi < 30:
    print("Category: Overweight")
else:
    print("Category: Obese")
```

### Challenge 3: Game Score Tracker
Create a program that tracks game scores:

```python
print("🎮 Game Score Tracker 🎮")

# Get game information
player_name = input("Player name: ")
level = int(input("Current level: "))
score = int(input("Current score: "))
time_played = int(input("Time played (minutes): "))

# Calculate metrics
score_per_minute = score / time_played
level_progress = (level / 100) * 100  # Assuming max level is 100

# Display results
print("\n🏆 Game Statistics for " + player_name + ":")
print("Level: " + str(level))
print("Score: " + str(score))
print("Time Played: " + str(time_played) + " minutes")
print("Score per Minute: " + str(round(score_per_minute, 2)))
print("Level Progress: " + str(round(level_progress, 1)) + "%")

# Performance rating
if score_per_minute > 100:
    print("Rating: ⭐⭐⭐ Excellent!")
elif score_per_minute > 50:
    print("Rating: ⭐⭐ Good!")
else:
    print("Rating: ⭐ Keep practicing!")
```

---

## What's Next? 🚀

You've learned how to do math and make comparisons with your variables! Now you can:
- Perform calculations in your programs
- Compare values and make decisions
- Use logical operators for complex thinking

**In the next lesson, you'll learn:**
- How to use if statements to make decisions
- How to create different paths in your programs
- How to make your programs smarter!

---

## Practice Time! 💪

**Try these exercises:**

1. **Create a program that calculates the area of different shapes**
2. **Make a program that determines if someone can vote**
3. **Build a program that calculates tips for restaurants**
4. **Design a program that converts temperatures between Celsius and Fahrenheit**

**Remember:** Operators make your programs powerful and able to do real calculations!

---

## Fun Facts! 🎉

- **Python follows PEMDAS** just like math class!
- **Comparison operators** always return True or False
- **Logical operators** help you make complex decisions
- **You can combine** many operators in one expression!

---

## Discussion Questions 💭

1. **What was the most interesting calculation you made?**
2. **How do you think operators help make programs more useful?**
3. **What kind of real-world problems could you solve with operators?**

---

## Next Up: If Statements! 🤔

In the next lesson, you'll learn how to make your programs make decisions and choose different paths!

**Keep calculating and comparing!** 🎉
