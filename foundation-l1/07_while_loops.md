# While Loops 🔄
## Repeating Actions Until Conditions Are Met

### Learning Objectives
By the end of this lesson, students will:
- Use while loops to repeat actions
- Understand when to use while loops vs other loops
- Create programs that keep running until conditions are met
- Use break and continue statements to control loop flow

---

## What are While Loops? 🤔

**While loops repeat actions as long as a condition is true!**

Think of while loops as:
- **Repeating instructions** until something changes
- **Persistent helpers** that keep trying until they succeed
- **Patient teachers** that repeat lessons until you understand

### Real-World Analogy: Brushing Your Teeth
- **While** your teeth are dirty → Keep brushing
- **When** your teeth are clean → Stop brushing
- **Repeat** this process every day!

---

## Basic While Loop Structure 📝

### Simple While Loop
```python
while condition:
    # Do this as long as condition is True
    print("The condition is still true!")
    # Make sure to change the condition eventually!
```

### While Loop with Counter
```python
counter = 0
while counter < 5:
    print("Count: " + str(counter))
    counter = counter + 1  # This changes the condition
```

---

## Real-World Examples 🌟

### Example 1: Number Guessing Game
```python
print("🎯 Number Guessing Game 🎯")

import random
secret_number = random.randint(1, 100)
guesses = 0
max_guesses = 7

print("I'm thinking of a number between 1 and 100!")
print("You have 7 guesses. Good luck!")

while guesses < max_guesses:
    guess = int(input("Enter your guess: "))
    guesses = guesses + 1
    
    if guess == secret_number:
        print("🎉 Congratulations! You guessed it!")
        print("It took you " + str(guesses) + " guesses!")
        break
    elif guess < secret_number:
        print("Too low! Try higher.")
    else:
        print("Too high! Try lower.")
    
    print("Guesses left: " + str(max_guesses - guesses))

if guesses >= max_guesses:
    print("😞 Game over! The number was " + str(secret_number))
```

### Example 2: Password Retry System
```python
print("🔐 Password Retry System 🔐")

correct_password = "password123"
max_attempts = 3
attempts = 0

print("Enter your password. You have 3 attempts.")

while attempts < max_attempts:
    password = input("Password: ")
    attempts = attempts + 1
    
    if password == correct_password:
        print("✅ Login successful!")
        print("Welcome to the system!")
        break
    else:
        remaining = max_attempts - attempts
        if remaining > 0:
            print("❌ Wrong password! " + str(remaining) + " attempts left.")
        else:
            print("❌ Account locked! Too many failed attempts.")
```

### Example 3: Shopping Cart
```python
print("🛒 Shopping Cart 🛒")

total = 0
item_count = 0

print("Add items to your cart. Type 'done' when finished.")

while True:
    item = input("Enter item name (or 'done' to finish): ")
    
    if item.lower() == "done":
        break
    
    price = float(input("Enter price: $"))
    quantity = int(input("Enter quantity: "))
    
    item_total = price * quantity
    total = total + item_total
    item_count = item_count + quantity
    
    print("Added: " + str(quantity) + "x " + item + " = $" + str(item_total))

print("\n📄 Receipt:")
print("Total items: " + str(item_count))
print("Total cost: $" + str(total))
print("Thank you for shopping!")
```

---

## Interactive Examples 🎮

### Example 1: Text Adventure Game
```python
print("🗺️ Text Adventure Game 🗺️")

health = 100
inventory = []
current_room = "forest"

print("You wake up in a mysterious forest...")
print("Type 'help' for commands.")

while health > 0:
    print(f"\n🏥 Health: {health}")
    print(f"📍 Location: {current_room}")
    print(f"🎒 Inventory: {inventory}")
    
    action = input("What do you do? ").lower()
    
    if action == "help":
        print("Commands: look, go, take, use, quit")
        
    elif action == "look":
        if current_room == "forest":
            print("🌲 You see tall trees and a path leading north.")
        elif current_room == "cave":
            print("🕳️ You're in a dark cave with glowing crystals.")
            
    elif action == "go north":
        if current_room == "forest":
            current_room = "cave"
            print("You enter a mysterious cave...")
        else:
            print("You can't go that way!")
            
    elif action == "take crystal" and current_room == "cave":
        inventory.append("crystal")
        print("✨ You found a glowing crystal!")
        
    elif action == "use crystal" and "crystal" in inventory:
        health = health + 20
        inventory.remove("crystal")
        print("💚 The crystal heals you!")
        
    elif action == "quit":
        print("Thanks for playing!")
        break
        
    else:
        print("I don't understand that command.")
        
    # Random health loss
    if health > 0:
        health = health - 5
        print("💔 You lose 5 health from the dangerous environment!")

if health <= 0:
    print("💀 Game Over! You didn't survive the adventure!")
```

### Example 2: Study Session Tracker
```python
print("📚 Study Session Tracker 📚")

total_study_time = 0
sessions = 0
subjects = []

print("Track your study sessions. Type 'done' when finished.")

while True:
    subject = input("What subject are you studying? (or 'done'): ")
    
    if subject.lower() == "done":
        break
    
    study_time = int(input("How many minutes did you study? "))
    total_study_time = total_study_time + study_time
    sessions = sessions + 1
    subjects.append(subject)
    
    print(f"✅ Studied {subject} for {study_time} minutes!")
    
    # Motivational messages
    if study_time >= 60:
        print("🌟 Excellent! You studied for over an hour!")
    elif study_time >= 30:
        print("👍 Good job! Keep it up!")
    else:
        print("💪 Every minute counts! Keep studying!")

print(f"\n📊 Study Summary:")
print(f"Total sessions: {sessions}")
print(f"Total study time: {total_study_time} minutes")
print(f"Average per session: {total_study_time // sessions} minutes")
print(f"Subjects studied: {', '.join(subjects)}")

if total_study_time >= 300:
    print("🏆 Amazing! You studied for over 5 hours!")
elif total_study_time >= 180:
    print("⭐ Great job! You studied for over 3 hours!")
else:
    print("📚 Keep studying! Every bit helps!")
```

### Example 3: Fitness Tracker
```python
print("💪 Fitness Tracker 💪")

total_calories = 0
workouts = 0
current_streak = 0
max_streak = 0

print("Track your daily workouts. Type 'done' when finished.")

while True:
    workout_type = input("What workout did you do? (or 'done'): ")
    
    if workout_type.lower() == "done":
        break
    
    duration = int(input("How many minutes? "))
    calories_burned = duration * 5  # Rough estimate
    total_calories = total_calories + calories_burned
    workouts = workouts + 1
    current_streak = current_streak + 1
    
    if current_streak > max_streak:
        max_streak = current_streak
    
    print(f"🔥 Great! You burned {calories_burned} calories!")
    
    # Encouragement based on workout
    if duration >= 60:
        print("💪 Beast mode! Over an hour of exercise!")
    elif duration >= 30:
        print("🏃 Awesome! Great workout!")
    else:
        print("👍 Good start! Every minute counts!")

print(f"\n📈 Fitness Summary:")
print(f"Total workouts: {workouts}")
print(f"Total calories burned: {total_calories}")
print(f"Current streak: {current_streak} days")
print(f"Best streak: {max_streak} days")

if current_streak >= 7:
    print("🏆 Amazing! You're on fire!")
elif current_streak >= 3:
    print("⭐ Great streak! Keep it up!")
else:
    print("💪 Start a new streak tomorrow!")
```

---

## Break and Continue Statements 🛑

### Break Statement
**Stops the loop immediately**

```python
print("🔍 Search for the Number 7 🔍")

numbers = [1, 3, 5, 7, 9, 11]
index = 0

while index < len(numbers):
    print("Checking number: " + str(numbers[index]))
    
    if numbers[index] == 7:
        print("🎉 Found the number 7!")
        break  # Stop the loop immediately
    
    index = index + 1

print("Search complete!")
```

### Continue Statement
**Skips to the next iteration**

```python
print("🔢 Print Even Numbers Only 🔢")

number = 0

while number < 10:
    number = number + 1
    
    if number % 2 != 0:  # If number is odd
        continue  # Skip to next iteration
    
    print("Even number: " + str(number))
```

---

## Common Mistakes (And How to Fix Them!) ❌➡️✅

### Mistake 1: Infinite Loop
```python
# ❌ Wrong - This will run forever!
number = 1
while number < 5:
    print("Number: " + str(number))
    # Forgot to change the number!

# ✅ Correct - Change the condition
number = 1
while number < 5:
    print("Number: " + str(number))
    number = number + 1  # This changes the condition
```

### Mistake 2: Wrong Condition
```python
# ❌ Wrong - This will never run
number = 5
while number > 10:  # 5 is never > 10
    print("This will never print!")

# ✅ Correct - Use appropriate condition
number = 5
while number < 10:  # 5 < 10 is True
    print("Number: " + str(number))
    number = number + 1
```

### Mistake 3: Missing Break in While True
```python
# ❌ Wrong - This will run forever
while True:
    user_input = input("Enter something: ")
    print("You entered: " + user_input)
    # No way to exit!

# ✅ Correct - Add a way to exit
while True:
    user_input = input("Enter something (or 'quit' to exit): ")
    if user_input.lower() == "quit":
        break
    print("You entered: " + user_input)
```

---

## Fun Challenges! 🎯

### Challenge 1: Number Pattern Generator
Create a program that generates number patterns:

```python
print("🔢 Number Pattern Generator 🔢")

print("Choose a pattern:")
print("1. Count up to a number")
print("2. Count down from a number")
print("3. Print even numbers")
print("4. Print odd numbers")

choice = int(input("Enter your choice (1-4): "))

if choice == 1:
    max_num = int(input("Count up to what number? "))
    num = 1
    while num <= max_num:
        print(num)
        num = num + 1
        
elif choice == 2:
    start_num = int(input("Count down from what number? "))
    num = start_num
    while num >= 1:
        print(num)
        num = num - 1
        
elif choice == 3:
    max_num = int(input("Print even numbers up to what number? "))
    num = 2
    while num <= max_num:
        print(num)
        num = num + 2
        
elif choice == 4:
    max_num = int(input("Print odd numbers up to what number? "))
    num = 1
    while num <= max_num:
        print(num)
        num = num + 2

print("Pattern complete!")
```

### Challenge 2: Word Guessing Game
Create a word guessing game:

```python
print("🎯 Word Guessing Game 🎯")

secret_word = "python"
guessed_letters = []
wrong_guesses = 0
max_wrong = 6

print("Guess the secret word! It has " + str(len(secret_word)) + " letters.")
print("You have 6 wrong guesses allowed.")

while wrong_guesses < max_wrong:
    # Show current progress
    display_word = ""
    for letter in secret_word:
        if letter in guessed_letters:
            display_word = display_word + letter
        else:
            display_word = display_word + "_"
    
    print("Word: " + display_word)
    print("Guessed letters: " + str(guessed_letters))
    print("Wrong guesses left: " + str(max_wrong - wrong_guesses))
    
    # Check if word is complete
    if display_word == secret_word:
        print("🎉 Congratulations! You guessed the word!")
        break
    
    # Get guess
    guess = input("Guess a letter: ").lower()
    
    if guess in guessed_letters:
        print("You already guessed that letter!")
    elif guess in secret_word:
        print("✅ Good guess!")
        guessed_letters.append(guess)
    else:
        print("❌ Wrong guess!")
        guessed_letters.append(guess)
        wrong_guesses = wrong_guesses + 1

if wrong_guesses >= max_wrong:
    print("😞 Game over! The word was: " + secret_word)
```

### Challenge 3: Personal Habit Tracker
Create a habit tracking system:

```python
print("📅 Personal Habit Tracker 📅")

habits = {}
day = 1

print("Track your daily habits. Type 'done' when finished.")

while True:
    print(f"\n📅 Day {day}")
    habit_name = input("What habit did you do? (or 'done' to finish): ")
    
    if habit_name.lower() == "done":
        break
    
    if habit_name not in habits:
        habits[habit_name] = 0
    
    habits[habit_name] = habits[habit_name] + 1
    day = day + 1
    
    print(f"✅ Great! You've done '{habit_name}' {habits[habit_name]} times!")
    
    # Show progress
    print("\n📊 Your Progress:")
    for habit, count in habits.items():
        print(f"{habit}: {count} times")

print(f"\n🏆 Final Summary (Day {day-1}):")
for habit, count in habits.items():
    print(f"{habit}: {count} times")
    if count >= 7:
        print(f"  🌟 Excellent! You did {habit} every day!")
    elif count >= 5:
        print(f"  ⭐ Great! You did {habit} most days!")
    else:
        print(f"  💪 Keep working on {habit}!")
```

---

## What's Next? 🚀

You've learned how to use while loops to repeat actions! Now you can:
- Create programs that keep running until conditions are met
- Use break and continue to control loop flow
- Build interactive games and applications

**In the next lesson, you'll learn:**
- How to use for loops for counting and iterating
- How to loop through lists and ranges
- How to make your programs more efficient!

---

## Practice Time! 💪

**Try these exercises:**

1. **Create a program that counts down from 10 to 1**
2. **Make a program that keeps asking for numbers until you enter 0**
3. **Build a program that simulates a dice rolling game**
4. **Design a program that tracks your daily water intake**

**Remember:** While loops are perfect when you don't know how many times you need to repeat something!

---

## Fun Facts! 🎉

- **While loops are used** in almost every interactive program!
- **You can nest while loops** inside other while loops!
- **While loops are perfect** for user input validation!
- **Many games use while loops** to keep running until the game ends!

---

## Discussion Questions 💭

1. **What was the most interesting while loop you created?**
2. **How do you think while loops help make programs more interactive?**
3. **What kind of real-world problems could you solve with while loops?**

---

## Next Up: For Loops! 🔢

In the next lesson, you'll learn how to use for loops for counting and iterating through data!

**Keep repeating and improving!** 🎉

