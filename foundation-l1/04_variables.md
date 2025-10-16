# Variables 📦
## Storing Information in Your Programs

### Learning Objectives
By the end of this lesson, students will:
- Understand what variables are and why they're important
- Create and use variables to store different types of data
- Name variables following good practices
- Use variables to make programs more flexible and powerful

---

## What are Variables? 🤔

**Variables are like labeled boxes that store information!**

Think of variables as:
- **Storage containers** for your data
- **Labels** that help you find information later
- **Memory slots** that remember things for you

### Real-World Analogy: School Locker
- **Locker** = Variable
- **Locker Number** = Variable name
- **Books inside** = Data stored in the variable
- **You can change** what's inside anytime!

---

## Why Do We Need Variables? 🌟

### Without Variables (Hard to Change)
```python
print("Hello, Sarah!")
print("Sarah is 15 years old")
print("Sarah's favorite color is blue")
print("Sarah likes pizza")
```

### With Variables (Easy to Change!)
```python
name = "Sarah"
age = 15
favorite_color = "blue"
favorite_food = "pizza"

print("Hello, " + name + "!")
print(name + " is " + str(age) + " years old")
print(name + "'s favorite color is " + favorite_color)
print(name + " likes " + favorite_food)
```

**See the difference?** With variables, you can easily change the person's information!

---

## Creating Variables 📝

### Basic Syntax
```python
variable_name = value
```

### Rules for Variable Names
1. **Start with a letter** (not a number)
2. **Use letters, numbers, and underscores** only
3. **No spaces** (use underscores instead)
4. **Be descriptive** (name tells you what it stores)

### Good vs Bad Variable Names
```python
# ✅ Good names
student_name = "Alex"
student_age = 14
favorite_game = "Minecraft"

# ❌ Bad names
a = "Alex"           # Not descriptive
student name = "Alex" # Has a space
2name = "Alex"       # Starts with number
```

---

## Types of Data in Variables 🗂️

### 1. Text (Strings)
```python
name = "Sarah"
school = "Lincoln Middle School"
favorite_color = "purple"
```

### 2. Numbers (Integers)
```python
age = 15
grade = 8
number_of_pets = 2
```

### 3. Decimal Numbers (Floats)
```python
height = 5.4
weight = 120.5
temperature = 72.3
```

### 4. True/False (Booleans)
```python
is_student = True
has_pets = False
likes_pizza = True
```

---

## Real-World Examples 🌟

### Example 1: Student Information System
```python
print("📚 Student Information System 📚")

# Store student information
student_name = "Emma Johnson"
student_id = 12345
grade_level = 9
gpa = 3.8
is_honor_student = True
favorite_subject = "Computer Science"

# Display the information
print("Student: " + student_name)
print("ID: " + str(student_id))
print("Grade: " + str(grade_level))
print("GPA: " + str(gpa))
print("Honor Student: " + str(is_honor_student))
print("Favorite Subject: " + favorite_subject)
```

### Example 2: Shopping Cart
```python
print("🛒 Shopping Cart 🛒")

# Store item information
item_name = "Gaming Headset"
item_price = 79.99
quantity = 2
is_on_sale = True
discount_percent = 20

# Calculate total
subtotal = item_price * quantity
discount_amount = subtotal * (discount_percent / 100)
total = subtotal - discount_amount

# Display information
print("Item: " + item_name)
print("Price: $" + str(item_price))
print("Quantity: " + str(quantity))
print("On Sale: " + str(is_on_sale))
print("Discount: " + str(discount_percent) + "%")
print("Total: $" + str(total))
```

### Example 3: Weather Station
```python
print("🌤️ Weather Station 🌤️")

# Store weather data
city = "New York"
temperature = 72.5
humidity = 65
is_sunny = True
wind_speed = 12.3

# Display weather report
print("Weather Report for " + city)
print("Temperature: " + str(temperature) + "°F")
print("Humidity: " + str(humidity) + "%")
print("Sunny: " + str(is_sunny))
print("Wind Speed: " + str(wind_speed) + " mph")
```

---

## Interactive Variable Examples 🎮

### Example 1: Personal Profile Creator
```python
print("👤 Personal Profile Creator 👤")

# Get information from user
name = input("What's your name? ")
age = input("How old are you? ")
favorite_color = input("What's your favorite color? ")
favorite_food = input("What's your favorite food? ")
has_pets = input("Do you have pets? (yes/no): ")

# Store the information
print("\n📋 Your Profile:")
print("Name: " + name)
print("Age: " + age)
print("Favorite Color: " + favorite_color)
print("Favorite Food: " + favorite_food)
print("Has Pets: " + has_pets)
```

### Example 2: Game Character Creator
```python
print("🎮 Game Character Creator 🎮")

# Create character
character_name = input("What's your character's name? ")
character_class = input("What class? (Warrior, Mage, Archer): ")
character_level = input("What level? (1-100): ")
character_health = input("Health points: ")
character_mana = input("Mana points: ")

# Display character stats
print("\n⚔️ Character Stats:")
print("Name: " + character_name)
print("Class: " + character_class)
print("Level: " + character_level)
print("Health: " + character_health)
print("Mana: " + character_mana)
print("Ready for adventure!")
```

### Example 3: Recipe Calculator
```python
print("👨‍🍳 Recipe Calculator 👨‍🍳")

# Recipe information
recipe_name = input("What are you making? ")
servings = input("How many servings? ")
cooking_time = input("How long does it take? (minutes): ")
difficulty = input("Difficulty level? (Easy/Medium/Hard): ")

# Display recipe info
print("\n📖 Recipe Information:")
print("Dish: " + recipe_name)
print("Servings: " + servings)
print("Cooking Time: " + cooking_time + " minutes")
print("Difficulty: " + difficulty)
print("Bon appétit!")
```

---

## Changing Variables 🔄

### You Can Change Variables Anytime!
```python
# Start with one value
score = 0
print("Score: " + str(score))

# Change the value
score = 10
print("Score: " + str(score))

# Change it again
score = 25
print("Score: " + str(score))
```

### Real-World Example: Score Tracker
```python
print("🎯 Score Tracker 🎯")

# Starting score
score = 0
print("Starting score: " + str(score))

# Game events
print("You scored a goal! +10 points")
score = score + 10
print("Current score: " + str(score))

print("You found a bonus! +5 points")
score = score + 5
print("Current score: " + str(score))

print("You completed a level! +20 points")
score = score + 20
print("Final score: " + str(score))
```

---

## Common Mistakes (And How to Fix Them!) ❌➡️✅

### Mistake 1: Forgetting to Convert Numbers to Text
```python
# ❌ Wrong
age = 15
print("I am " + age + " years old")

# ✅ Correct
age = 15
print("I am " + str(age) + " years old")
```

### Mistake 2: Using Wrong Variable Name
```python
# ❌ Wrong
name = "Sarah"
print("Hello, " + student_name + "!")

# ✅ Correct
name = "Sarah"
print("Hello, " + name + "!")
```

### Mistake 3: Not Using Quotes for Text
```python
# ❌ Wrong
favorite_color = blue

# ✅ Correct
favorite_color = "blue"
```

### Mistake 4: Using Spaces in Variable Names
```python
# ❌ Wrong
student name = "Alex"

# ✅ Correct
student_name = "Alex"
```

---

## Fun Challenges! 🎯

### Challenge 1: Personal Diary
Create a program that stores and displays personal information:

```python
print("📔 Personal Diary 📔")

# Store personal info
name = input("Your name: ")
birthday = input("Your birthday: ")
hobby = input("Your hobby: ")
dream_job = input("Your dream job: ")
favorite_place = input("Your favorite place: ")

# Display diary entry
print("\n📝 Diary Entry:")
print("Today I'm thinking about " + name + ".")
print("I was born on " + birthday + ".")
print("I love " + hobby + ".")
print("When I grow up, I want to be a " + dream_job + ".")
print("My favorite place is " + favorite_place + ".")
print("What a great day!")
```

### Challenge 2: School Report Card
Create a program that tracks grades:

```python
print("📊 School Report Card 📊")

# Get student info
student_name = input("Student name: ")
math_grade = input("Math grade: ")
science_grade = input("Science grade: ")
english_grade = input("English grade: ")
history_grade = input("History grade: ")

# Display report card
print("\n🎓 Report Card for " + student_name)
print("Math: " + math_grade)
print("Science: " + science_grade)
print("English: " + english_grade)
print("History: " + history_grade)
print("Keep up the great work!")
```

### Challenge 3: Pet Care Tracker
Create a program that tracks pet information:

```python
print("🐕 Pet Care Tracker 🐕")

# Pet information
pet_name = input("Pet's name: ")
pet_type = input("Type of pet: ")
pet_age = input("Pet's age: ")
last_vet_visit = input("Last vet visit: ")
favorite_toy = input("Favorite toy: ")

# Display pet profile
print("\n🐾 Pet Profile:")
print("Name: " + pet_name)
print("Type: " + pet_type)
print("Age: " + pet_age)
print("Last Vet Visit: " + last_vet_visit)
print("Favorite Toy: " + favorite_toy)
print(pet_name + " is such a good " + pet_type + "!")
```

---

## What's Next? 🚀

You've learned how to store and organize information using variables! Now you can:
- Keep track of different types of data
- Make your programs more flexible
- Store user input for later use

**In the next lesson, you'll learn:**
- How to do math with variables
- How to use operators (+, -, *, /)
- How to make calculations in your programs!

---

## Practice Time! 💪

**Try these exercises:**

1. **Create a program that stores your family's information**
2. **Make a program that tracks your favorite movies and books**
3. **Build a program that stores information about your friends**
4. **Design a program that keeps track of your daily activities**

**Remember:** Variables make your programs powerful and flexible!

---

## Fun Facts! 🎉

- **Variables are like memory** - they remember things for you
- **You can change variables** anytime in your program
- **Good variable names** make your code easy to understand
- **Every programming language** uses variables to store data!

---

## Discussion Questions 💭

1. **What was the most interesting thing you stored in a variable?**
2. **How do you think variables help make programs more useful?**
3. **What kind of information would you like to store in a program?**

---

## Next Up: Operators! ➕➖✖️➗

In the next lesson, you'll learn how to do math and calculations with your variables!

**Keep storing and organizing information!** 🎉
