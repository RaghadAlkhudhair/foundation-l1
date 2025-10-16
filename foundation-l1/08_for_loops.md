# For Loops 🔢
## Counting and Iterating Through Data

### Learning Objectives
By the end of this lesson, students will:
- Use for loops to iterate through data
- Understand the difference between for loops and while loops
- Use range() function to create number sequences
- Loop through lists and strings
- Use nested for loops for complex patterns

---

## What are For Loops? 🤔

**For loops repeat actions a specific number of times or for each item in a collection!**

Think of for loops as:
- **Counting machines** that do something for each number
- **Item processors** that handle each item in a list
- **Efficient workers** that know exactly how many times to repeat

### Real-World Analogy: Checking Homework
- **For each** homework assignment → Check if it's complete
- **For each** page in a book → Read the page
- **For each** student in class → Take attendance

---

## Basic For Loop Structure 📝

### Simple For Loop with Range
```python
for i in range(5):
    print("Count: " + str(i))
```

### For Loop with List
```python
fruits = ["apple", "banana", "orange"]
for fruit in fruits:
    print("I like " + fruit)
```

### For Loop with String
```python
word = "hello"
for letter in word:
    print("Letter: " + letter)
```

---

## The Range Function 🔢

### Basic Range
```python
# range(5) creates numbers 0, 1, 2, 3, 4
for i in range(5):
    print(i)
```

### Range with Start and End
```python
# range(1, 6) creates numbers 1, 2, 3, 4, 5
for i in range(1, 6):
    print(i)
```

### Range with Step
```python
# range(0, 10, 2) creates numbers 0, 2, 4, 6, 8
for i in range(0, 10, 2):
    print(i)
```

### Counting Down
```python
# range(10, 0, -1) creates numbers 10, 9, 8, 7, 6, 5, 4, 3, 2, 1
for i in range(10, 0, -1):
    print(i)
```

---

## Real-World Examples 🌟

### Example 1: Multiplication Table Generator
```python
print("📊 Multiplication Table Generator 📊")

number = int(input("Which multiplication table? "))
print(f"Multiplication table for {number}:")

for i in range(1, 13):
    result = number * i
    print(f"{number} x {i} = {result}")
```

### Example 2: Grade Calculator for Multiple Students
```python
print("📚 Grade Calculator for Multiple Students 📚")

num_students = int(input("How many students? "))
grades = []

for i in range(num_students):
    name = input(f"Student {i+1} name: ")
    score = int(input(f"{name}'s score: "))
    grades.append((name, score))

print("\n📊 Grade Report:")
for name, score in grades:
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
    
    print(f"{name}: {score} ({grade})")
```

### Example 3: Shopping List Calculator
```python
print("🛒 Shopping List Calculator 🛒")

items = []
prices = []

print("Enter your shopping items. Type 'done' when finished.")

while True:
    item = input("Item name (or 'done'): ")
    if item.lower() == "done":
        break
    
    price = float(input(f"Price of {item}: $"))
    items.append(item)
    prices.append(price)

print("\n📄 Shopping List:")
total = 0
for i in range(len(items)):
    print(f"{i+1}. {items[i]}: ${prices[i]}")
    total = total + prices[i]

print(f"\n💰 Total: ${total}")
print(f"Number of items: {len(items)}")
```

---

## Interactive Examples 🎮

### Example 1: Number Guessing Game with Hints
```python
print("🎯 Number Guessing Game with Hints 🎯")

import random
secret_number = random.randint(1, 100)
guesses = []

print("I'm thinking of a number between 1 and 100!")
print("I'll give you hints after each guess!")

for attempt in range(7):
    guess = int(input(f"Attempt {attempt + 1}/7 - Enter your guess: "))
    guesses.append(guess)
    
    if guess == secret_number:
        print("🎉 Congratulations! You guessed it!")
        print(f"It took you {attempt + 1} attempts!")
        break
    elif guess < secret_number:
        print("Too low! Try higher.")
    else:
        print("Too high! Try lower.")
    
    # Show guess history
    print("Your guesses so far:", guesses)

if secret_number not in guesses:
    print(f"😞 Game over! The number was {secret_number}")
    print("Your guesses:", guesses)
```

### Example 2: Text Analyzer
```python
print("📝 Text Analyzer 📝")

text = input("Enter some text: ")

# Count different types of characters
vowels = 0
consonants = 0
digits = 0
spaces = 0
special = 0

for char in text.lower():
    if char in "aeiou":
        vowels = vowels + 1
    elif char.isalpha():
        consonants = consonants + 1
    elif char.isdigit():
        digits = digits + 1
    elif char == " ":
        spaces = spaces + 1
    else:
        special = special + 1

print("\n📊 Text Analysis:")
print(f"Total characters: {len(text)}")
print(f"Vowels: {vowels}")
print(f"Consonants: {consonants}")
print(f"Digits: {digits}")
print(f"Spaces: {spaces}")
print(f"Special characters: {special}")

# Find the most common letter
letter_count = {}
for char in text.lower():
    if char.isalpha():
        letter_count[char] = letter_count.get(char, 0) + 1

if letter_count:
    most_common = max(letter_count, key=letter_count.get)
    print(f"Most common letter: '{most_common}' ({letter_count[most_common]} times)")
```

### Example 3: Pattern Generator
```python
print("🎨 Pattern Generator 🎨")

print("Choose a pattern:")
print("1. Stars")
print("2. Numbers")
print("3. Letters")
print("4. Custom")

choice = int(input("Enter your choice (1-4): "))
size = int(input("Enter pattern size: "))

if choice == 1:
    print("\n⭐ Star Pattern:")
    for i in range(size):
        print("*" * (i + 1))
        
elif choice == 2:
    print("\n🔢 Number Pattern:")
    for i in range(size):
        for j in range(i + 1):
            print(j + 1, end=" ")
        print()
        
elif choice == 3:
    print("\n🔤 Letter Pattern:")
    for i in range(size):
        for j in range(i + 1):
            print(chr(65 + j), end=" ")  # A, B, C, etc.
        print()
        
elif choice == 4:
    symbol = input("Enter your symbol: ")
    print(f"\n{symbol} Custom Pattern:")
    for i in range(size):
        print(symbol * (i + 1))
```

---

## Nested For Loops 🏗️

### What are Nested For Loops?
**For loops inside other for loops - like Russian nesting dolls!**

```python
print("🏗️ Nested For Loop Example 🏗️")

print("Multiplication Table (1-5):")
for i in range(1, 6):
    for j in range(1, 6):
        result = i * j
        print(f"{i} x {j} = {result}", end="\t")
    print()  # New line after each row
```

### Example: Coordinate Grid
```python
print("🗺️ Coordinate Grid 🗺️")

size = int(input("Enter grid size: "))

print("Coordinate Grid:")
for x in range(size):
    for y in range(size):
        print(f"({x},{y})", end=" ")
    print()
```

---

## For Loops with Lists 📋

### Basic List Iteration
```python
fruits = ["apple", "banana", "orange", "grape"]

print("🍎 My Favorite Fruits:")
for i, fruit in enumerate(fruits):
    print(f"{i + 1}. {fruit}")
```

### List Processing
```python
numbers = [1, 2, 3, 4, 5]
squared = []

print("🔢 Squaring Numbers:")
for num in numbers:
    square = num ** 2
    squared.append(square)
    print(f"{num}² = {square}")

print(f"Squared numbers: {squared}")
```

### Finding Items in Lists
```python
scores = [85, 92, 78, 96, 88, 91]
target = 90

print("🎯 Finding High Scores:")
high_scores = []
for i, score in enumerate(scores):
    if score >= target:
        high_scores.append((i, score))
        print(f"Student {i + 1}: {score} (High score!)")

print(f"Found {len(high_scores)} high scores!")
```

---

## For Loops with Strings 🔤

### Character Analysis
```python
word = input("Enter a word: ")

print("🔤 Character Analysis:")
for i, char in enumerate(word):
    print(f"Position {i}: '{char}'")
    if char.isupper():
        print("  - Uppercase letter")
    elif char.islower():
        print("  - Lowercase letter")
    elif char.isdigit():
        print("  - Digit")
    else:
        print("  - Special character")
```

### Word Processing
```python
sentence = input("Enter a sentence: ")
words = sentence.split()

print("📝 Word Processing:")
for i, word in enumerate(words):
    print(f"Word {i + 1}: '{word}' ({len(word)} letters)")
    if word[0].isupper():
        print("  - Starts with capital letter")
    if word.endswith('ing'):
        print("  - Ends with 'ing'")
```

---

## Common Mistakes (And How to Fix Them!) ❌➡️✅

### Mistake 1: Modifying List While Iterating
```python
# ❌ Wrong - This can cause problems
numbers = [1, 2, 3, 4, 5]
for num in numbers:
    if num % 2 == 0:
        numbers.remove(num)  # Don't modify list while iterating!

# ✅ Correct - Create a new list
numbers = [1, 2, 3, 4, 5]
even_numbers = []
for num in numbers:
    if num % 2 == 0:
        even_numbers.append(num)
print("Even numbers:", even_numbers)
```

### Mistake 2: Wrong Range Usage
```python
# ❌ Wrong - This will print 0, 1, 2, 3, 4 (not 1, 2, 3, 4, 5)
for i in range(5):
    print(i + 1)  # Adding 1 inside the loop

# ✅ Correct - Use proper range
for i in range(1, 6):  # This gives 1, 2, 3, 4, 5
    print(i)
```

### Mistake 3: Forgetting to Use enumerate()
```python
# ❌ Wrong - Can't get index easily
fruits = ["apple", "banana", "orange"]
for fruit in fruits:
    print(fruit)  # No index information

# ✅ Correct - Use enumerate for index
fruits = ["apple", "banana", "orange"]
for i, fruit in enumerate(fruits):
    print(f"{i + 1}. {fruit}")
```

---

## Fun Challenges! 🎯

### Challenge 1: ASCII Art Generator
Create a program that generates ASCII art:

```python
print("🎨 ASCII Art Generator 🎨")

print("Choose a shape:")
print("1. Triangle")
print("2. Square")
print("3. Diamond")
print("4. Heart")

choice = int(input("Enter your choice (1-4): "))
size = int(input("Enter size: "))

if choice == 1:
    print("\n🔺 Triangle:")
    for i in range(size):
        print(" " * (size - i - 1) + "*" * (2 * i + 1))
        
elif choice == 2:
    print("\n⬜ Square:")
    for i in range(size):
        print("*" * size)
        
elif choice == 3:
    print("\n💎 Diamond:")
    # Top half
    for i in range(size):
        print(" " * (size - i - 1) + "*" * (2 * i + 1))
    # Bottom half
    for i in range(size - 2, -1, -1):
        print(" " * (size - i - 1) + "*" * (2 * i + 1))
        
elif choice == 4:
    print("\n❤️ Heart:")
    for i in range(size):
        spaces = " " * (size - i - 1)
        stars = "*" * (2 * i + 1)
        print(spaces + stars + " " + stars)
```

### Challenge 2: Password Strength Checker
Create a program that checks password strength:

```python
print("🔐 Password Strength Checker 🔐")

password = input("Enter a password: ")

# Check different criteria
length_score = 0
uppercase_score = 0
lowercase_score = 0
digit_score = 0
special_score = 0

# Length check
if len(password) >= 8:
    length_score = 1
    print("✅ Length: Good (8+ characters)")
else:
    print("❌ Length: Too short (need 8+ characters)")

# Character type checks
for char in password:
    if char.isupper():
        uppercase_score = 1
    elif char.islower():
        lowercase_score = 1
    elif char.isdigit():
        digit_score = 1
    elif char in "!@#$%^&*()_+-=[]{}|;:,.<>?":
        special_score = 1

if uppercase_score:
    print("✅ Uppercase: Contains uppercase letters")
else:
    print("❌ Uppercase: Missing uppercase letters")

if lowercase_score:
    print("✅ Lowercase: Contains lowercase letters")
else:
    print("❌ Lowercase: Missing lowercase letters")

if digit_score:
    print("✅ Digits: Contains numbers")
else:
    print("❌ Digits: Missing numbers")

if special_score:
    print("✅ Special: Contains special characters")
else:
    print("❌ Special: Missing special characters")

# Calculate total score
total_score = length_score + uppercase_score + lowercase_score + digit_score + special_score

print(f"\n📊 Password Strength: {total_score}/5")

if total_score == 5:
    print("🏆 Excellent! Very strong password!")
elif total_score >= 4:
    print("⭐ Good! Strong password!")
elif total_score >= 3:
    print("👍 Fair! Moderate password!")
else:
    print("⚠️ Weak! Consider strengthening your password!")
```

### Challenge 3: Data Analysis Tool
Create a program that analyzes a dataset:

```python
print("📊 Data Analysis Tool 📊")

# Get data from user
numbers = []
print("Enter numbers (type 'done' when finished):")

while True:
    user_input = input("Enter a number: ")
    if user_input.lower() == "done":
        break
    try:
        numbers.append(float(user_input))
    except ValueError:
        print("Please enter a valid number!")

if not numbers:
    print("No data to analyze!")
else:
    print(f"\n📈 Analysis of {len(numbers)} numbers:")
    
    # Basic statistics
    total = sum(numbers)
    average = total / len(numbers)
    minimum = min(numbers)
    maximum = max(numbers)
    
    print(f"Total: {total}")
    print(f"Average: {average:.2f}")
    print(f"Minimum: {minimum}")
    print(f"Maximum: {maximum}")
    
    # Count by ranges
    ranges = {"0-10": 0, "11-20": 0, "21-30": 0, "31-40": 0, "41+": 0}
    
    for num in numbers:
        if 0 <= num <= 10:
            ranges["0-10"] += 1
        elif 11 <= num <= 20:
            ranges["11-20"] += 1
        elif 21 <= num <= 30:
            ranges["21-30"] += 1
        elif 31 <= num <= 40:
            ranges["31-40"] += 1
        else:
            ranges["41+"] += 1
    
    print("\n📊 Distribution by ranges:")
    for range_name, count in ranges.items():
        percentage = (count / len(numbers)) * 100
        print(f"{range_name}: {count} numbers ({percentage:.1f}%)")
    
    # Find duplicates
    seen = set()
    duplicates = set()
    for num in numbers:
        if num in seen:
            duplicates.add(num)
        else:
            seen.add(num)
    
    if duplicates:
        print(f"\n🔄 Duplicates found: {duplicates}")
    else:
        print("\n✅ No duplicates found!")
```

---

## What's Next? 🚀

You've learned how to use for loops to iterate through data! Now you can:
- Count and repeat actions a specific number of times
- Process lists and strings efficiently
- Create complex patterns with nested loops

**In the next lesson, you'll learn:**
- How to use nested loops for complex patterns
- How to create advanced data structures
- How to make your programs even more powerful!

---

## Practice Time! 💪

**Try these exercises:**

1. **Create a program that prints a multiplication table**
2. **Make a program that counts vowels in a sentence**
3. **Build a program that finds the largest number in a list**
4. **Design a program that creates a number pyramid**

**Remember:** For loops are perfect when you know exactly how many times to repeat something!

---

## Fun Facts! 🎉

- **For loops are used** in almost every data processing program!
- **You can nest for loops** to create complex patterns!
- **For loops are more efficient** than while loops when you know the count!
- **Many algorithms use for loops** to process data step by step!

---

## Discussion Questions 💭

1. **What was the most interesting pattern you created with for loops?**
2. **How do you think for loops help make programs more efficient?**
3. **What kind of data processing could you do with for loops?**

---

## Next Up: Nested Loops! 🏗️

In the next lesson, you'll learn how to use nested loops to create complex patterns and solve advanced problems!

**Keep iterating and creating!** 🎉

