# If Statements 🤔
## Making Decisions in Your Programs

### Learning Objectives
By the end of this lesson, students will:
- Use if statements to make decisions in their programs
- Understand elif and else clauses
- Create programs that respond differently based on conditions
- Use nested if statements for complex decision making

---

## What are If Statements? 🤔

**If statements help your program make decisions, just like you do every day!**

Think of if statements as:
- **Decision makers** that choose what to do
- **Traffic lights** that direct the flow of your program
- **Smart assistants** that respond based on what they know

### Real-World Analogy: Weather Decisions
- **If it's raining** → Take an umbrella
- **If it's sunny** → Wear sunglasses
- **If it's cold** → Wear a jacket
- **Otherwise** → Check the weather app

---

## Basic If Statement Structure 📝

### Simple If
```python
if condition:
    # Do this if condition is True
    print("The condition is true!")
```

### If-Else
```python
if condition:
    # Do this if condition is True
    print("The condition is true!")
else:
    # Do this if condition is False
    print("The condition is false!")
```

### If-Elif-Else
```python
if condition1:
    # Do this if condition1 is True
    print("Condition 1 is true!")
elif condition2:
    # Do this if condition2 is True
    print("Condition 2 is true!")
else:
    # Do this if neither condition is True
    print("Neither condition is true!")
```

---

## Real-World Examples 🌟

### Example 1: Age-Based Eligibility Checker
```python
print("🏦 Age-Based Bank Account Eligibility Checker 🏦")

age = int(input("How old are you? "))

if age >= 18:
    print("✅ You are allowed to open your own independent bank account!")
elif age >= 15 and age < 18:
    print("✅ You can have a bank account, but you need guardian consent.")
else:
    print("❌ Sorry, you're too young to have a bank account.")
    print("Come back when you're older!")
```

### Example 2: Grade Calculator
```python
print("📊 Grade Calculator 📊")

score = int(input("Enter your test score (0-100): "))

if score >= 90:
    grade = "A"
    message = "Excellent work! 🌟"
elif score >= 80:
    grade = "B"
    message = "Good job! 👍"
elif score >= 70:
    grade = "C"
    message = "Not bad, keep trying! 💪"
elif score >= 60:
    grade = "D"
    message = "You need to study more! 📚"
else:
    grade = "F"
    message = "Time to hit the books! 📖"

print(f"Your grade: {grade}")
print(message)
```

### Example 3: Weather App
```python
print("🌤️ Weather App 🌤️")

temperature = int(input("What's the temperature? "))
is_raining = input("Is it raining? (yes/no): ").lower() == "yes"

print("\n🌤️ Weather Recommendations:")

if temperature > 80 and not is_raining:
    print("☀️ Perfect beach weather!")
    print("Wear sunscreen and go swimming!")
elif temperature > 70 and not is_raining:
    print("🌞 Great day for outdoor activities!")
    print("Go for a walk or bike ride!")
elif temperature > 60:
    print("🌤️ Nice day!")
    print("Perfect for a picnic!")
elif temperature > 32:
    print("🧥 Cool day!")
    print("Wear a jacket!")
else:
    print("🥶 Very cold!")
    print("Stay inside and drink hot chocolate!")

if is_raining:
    print("☔ It's raining - perfect day to read or play video games!")
```

---

## Interactive Examples 🎮

### Example 1: Game Character Creator
```python
print("🎮 Game Character Creator 🎮")

name = input("What's your character's name? ")
character_class = input("Choose class (Warrior/Mage/Archer): ").lower()

print(f"\n⚔️ Character: {name}")

if character_class == "warrior":
    health = 120
    attack = 15
    defense = 10
    print("Class: Warrior ⚔️")
    print("Special: High health and defense")
elif character_class == "mage":
    health = 80
    attack = 20
    defense = 5
    print("Class: Mage 🔮")
    print("Special: High attack, magic spells")
elif character_class == "archer":
    health = 100
    attack = 18
    defense = 8
    print("Class: Archer 🏹")
    print("Special: Balanced stats, ranged attacks")
else:
    health = 90
    attack = 12
    defense = 7
    print("Class: Adventurer 🗡️")
    print("Special: Jack of all trades")

print(f"Health: {health}")
print(f"Attack: {attack}")
print(f"Defense: {defense}")
print("Ready for adventure!")
```

### Example 2: Restaurant Order System
```python
print("🍽️ Restaurant Order System 🍽️")

print("Welcome to our restaurant!")
print("Menu:")
print("1. Pizza - $12")
print("2. Burger - $8")
print("3. Salad - $6")
print("4. Pasta - $10")

choice = int(input("Choose your meal (1-4): "))
quantity = int(input("How many would you like? "))

if choice == 1:
    item = "Pizza"
    price = 12
elif choice == 2:
    item = "Burger"
    price = 8
elif choice == 3:
    item = "Salad"
    price = 6
elif choice == 4:
    item = "Pasta"
    price = 10
else:
    print("❌ Invalid choice!")
    exit()

total = price * quantity
print(f"\n📄 Order Summary:")
print(f"Item: {item}")
print(f"Price each: ${price}")
print(f"Quantity: {quantity}")
print(f"Total: ${total}")

if total > 20:
    print("🎉 You get a free dessert!")
elif total > 15:
    print("🍪 You get a free cookie!")
else:
    print("Thank you for your order!")
```

### Example 3: Password Checker
```python
print("🔐 Password Checker 🔐")

username = input("Enter username: ")
password = input("Enter password: ")

# Simple password check (in real apps, this would be more secure)
correct_username = "admin"
correct_password = "password123"

if username == correct_username and password == correct_password:
    print("✅ Login successful!")
    print("Welcome to the system!")
    
    # Additional security check
    security_question = input("What's your favorite color? ")
    if security_question.lower() == "blue":
        print("🔒 Security verified!")
        print("You have full access!")
    else:
        print("⚠️ Security question incorrect!")
        print("Limited access granted!")
        
elif username == correct_username:
    print("❌ Wrong password!")
    print("Please try again!")
else:
    print("❌ Username not found!")
    print("Please check your username!")
```

---

## Nested If Statements 🏗️

### What are Nested If Statements?
**If statements inside other if statements - like Russian nesting dolls!**

```python
print("🎯 Nested Decision Example 🎯")

age = int(input("How old are you? "))
has_license = input("Do you have a driver's license? (yes/no): ").lower() == "yes"

if age >= 18:
    print("You're old enough to drive!")
    
    if has_license:
        print("✅ You can drive legally!")
        
        # Another nested check
        experience = int(input("How many years have you been driving? "))
        if experience >= 5:
            print("🚗 You're an experienced driver!")
        elif experience >= 2:
            print("🚙 You're getting the hang of it!")
        else:
            print("🚘 You're a new driver - be careful!")
    else:
        print("❌ You need a license to drive!")
        print("Go get your learner's permit!")
else:
    print("❌ You're too young to drive!")
    print("Wait until you're 18!")
```

---

## Complex Decision Making 🧠

### Example 1: School Admission System
```python
print("🎓 School Admission System 🎓")

gpa = float(input("Enter your GPA (0.0-4.0): "))
sat_score = int(input("Enter your SAT score: "))
extracurriculars = int(input("How many extracurricular activities? "))

print("\n📋 Admission Decision:")

if gpa >= 3.5 and sat_score >= 1200:
    print("🎉 Congratulations! You're accepted!")
    
    if extracurriculars >= 5:
        print("🌟 You qualify for the honors program!")
    elif extracurriculars >= 3:
        print("⭐ You qualify for merit scholarships!")
    else:
        print("✅ Regular admission granted!")
        
elif gpa >= 3.0 and sat_score >= 1000:
    print("✅ You're accepted on probation!")
    print("Keep your grades up!")
    
elif gpa >= 2.5:
    print("⏳ You're on the waitlist!")
    print("We'll contact you if spots open up!")
    
else:
    print("❌ Sorry, you're not accepted this year.")
    print("Consider improving your grades and reapplying!")
```

### Example 2: Smart Home System
```python
print("🏠 Smart Home System 🏠")

time_of_day = input("What time is it? (morning/afternoon/evening/night): ").lower()
temperature = int(input("What's the temperature? "))
is_occupied = input("Is anyone home? (yes/no): ").lower() == "yes"

print("\n🏠 Smart Home Actions:")

if time_of_day == "morning":
    print("🌅 Good morning!")
    if temperature < 70:
        print("🔥 Turning on the heater!")
    elif temperature > 75:
        print("❄️ Turning on the AC!")
    else:
        print("🌤️ Temperature is perfect!")
        
elif time_of_day == "afternoon":
    print("☀️ Good afternoon!")
    if is_occupied:
        print("🏠 Someone is home - keeping lights on!")
    else:
        print("💡 No one home - turning off lights!")
        
elif time_of_day == "evening":
    print("🌆 Good evening!")
    if is_occupied:
        print("🍽️ Time for dinner - dimming lights!")
        print("📺 Turning on the TV!")
    else:
        print("🌙 Evening mode - security system activated!")
        
else:  # night
    print("🌙 Good night!")
    if is_occupied:
        print("🛏️ Bedtime mode - turning off all lights!")
        print("🔒 Locking all doors!")
    else:
        print("🌃 Night mode - security system on high alert!")
```

---

## Common Mistakes (And How to Fix Them!) ❌➡️✅

### Mistake 1: Missing Colon
```python
# ❌ Wrong
if age >= 18
    print("You can vote!")

# ✅ Correct
if age >= 18:
    print("You can vote!")
```

### Mistake 2: Wrong Indentation
```python
# ❌ Wrong
if age >= 18:
print("You can vote!")  # Not indented

# ✅ Correct
if age >= 18:
    print("You can vote!")  # Properly indented
```

### Mistake 3: Using = Instead of ==
```python
# ❌ Wrong
if age = 18:  # This is assignment, not comparison!
    print("You are 18!")

# ✅ Correct
if age == 18:  # This is comparison
    print("You are 18!")
```

### Mistake 4: Missing Elif/Else
```python
# ❌ Wrong - only checks one condition
if score >= 90:
    print("A")
if score >= 80:  # This will also run if score is 95!
    print("B")

# ✅ Correct - uses elif
if score >= 90:
    print("A")
elif score >= 80:  # Only runs if first condition is false
    print("B")
```

---

## Fun Challenges! 🎯

### Challenge 1: Adventure Game
Create a text-based adventure game:

```python
print("🗺️ Adventure Game 🗺️")

print("You find yourself at a crossroads...")
print("1. Go left into the dark forest")
print("2. Go right toward the mountain")
print("3. Go straight to the village")

choice = int(input("What do you choose? (1-3): "))

if choice == 1:
    print("🌲 You enter the dark forest...")
    print("You hear strange noises!")
    
    action = input("Do you investigate? (yes/no): ").lower()
    if action == "yes":
        print("👻 You found a friendly ghost!")
        print("The ghost gives you a magic sword! ⚔️")
    else:
        print("You safely return to the crossroads.")
        
elif choice == 2:
    print("⛰️ You climb the mountain...")
    print("You find a cave!")
    
    enter = input("Do you enter the cave? (yes/no): ").lower()
    if enter == "yes":
        print("💎 You found treasure!")
        print("You're now rich! 💰")
    else:
        print("You continue climbing and find a beautiful view!")
        
elif choice == 3:
    print("🏘️ You walk to the village...")
    print("The villagers welcome you!")
    print("You find a place to rest and eat! 🍞")
    
else:
    print("❌ Invalid choice! You stand there confused...")
```

### Challenge 2: Personal Assistant
Create a smart personal assistant:

```python
print("🤖 Personal Assistant 🤖")

name = input("What's your name? ")
mood = input("How are you feeling? (happy/sad/tired/excited): ").lower()
time_of_day = input("What time is it? (morning/afternoon/evening): ").lower()

print(f"\n👋 Hello {name}!")

if mood == "happy":
    print("😊 I'm glad you're feeling happy!")
    if time_of_day == "morning":
        print("🌅 What a great way to start the day!")
    elif time_of_day == "afternoon":
        print("☀️ Perfect time to enjoy your happiness!")
    else:
        print("🌆 What a wonderful evening!")
        
elif mood == "sad":
    print("😢 I'm sorry you're feeling sad.")
    print("💙 Would you like to talk about it?")
    print("🎵 Maybe some music would help?")
    
elif mood == "tired":
    print("😴 You seem tired!")
    if time_of_day == "evening":
        print("🌙 Perfect time for bed!")
    else:
        print("☕ Maybe some coffee would help?")
        
elif mood == "excited":
    print("🎉 You're excited! That's awesome!")
    print("🚀 What are you excited about?")
    
else:
    print("🤔 I'm not sure how you're feeling, but I'm here to help!")

print("\nIs there anything else I can help you with?")
```

### Challenge 3: Weather-Based Activity Planner
Create a smart activity planner:

```python
print("🌤️ Weather-Based Activity Planner 🌤️")

temperature = int(input("What's the temperature? "))
is_raining = input("Is it raining? (yes/no): ").lower() == "yes"
is_weekend = input("Is it the weekend? (yes/no): ").lower() == "yes"
budget = int(input("What's your budget? $"))

print("\n🎯 Activity Recommendations:")

if is_raining:
    print("☔ It's raining - indoor activities:")
    if budget >= 50:
        print("🎬 Go to the movies!")
        print("🍕 Order pizza and watch Netflix!")
    elif budget >= 20:
        print("🎮 Play video games!")
        print("📚 Read a good book!")
    else:
        print("🏠 Stay home and relax!")
        print("🎵 Listen to music!")
        
elif temperature > 80:
    print("☀️ Hot weather - cool activities:")
    if budget >= 30:
        print("🏊 Go swimming!")
        print("🍦 Get ice cream!")
    else:
        print("🌳 Find shade and relax!")
        print("💧 Stay hydrated!")
        
elif temperature > 60:
    print("🌤️ Perfect weather - outdoor activities:")
    if is_weekend and budget >= 40:
        print("🚴 Go for a bike ride!")
        print("🧺 Have a picnic!")
    elif budget >= 20:
        print("🚶 Take a walk in the park!")
        print("📸 Go photography!")
    else:
        print("🌳 Enjoy nature!")
        print("🏃 Go for a run!")
        
else:
    print("🧥 Cool weather - cozy activities:")
    if budget >= 30:
        print("☕ Visit a coffee shop!")
        print("🛍️ Go shopping!")
    else:
        print("🏠 Stay cozy at home!")
        print("🍵 Make hot chocolate!")
```

---

## What's Next? 🚀

You've learned how to make decisions in your programs! Now you can:
- Create programs that respond differently based on conditions
- Use if statements to make your programs smarter
- Handle multiple scenarios with elif and else

**In the next lesson, you'll learn:**
- How to use while loops to repeat actions
- How to create programs that keep running until conditions are met
- How to make your programs more efficient!

---

## Practice Time! 💪

**Try these exercises:**

1. **Create a program that determines what grade you get based on your score**
2. **Make a program that recommends what to wear based on the weather**
3. **Build a program that determines if you can watch a movie based on your age**
4. **Design a program that gives different advice based on your mood**

**Remember:** If statements make your programs smart and responsive!

---

## Fun Facts! 🎉

- **Every decision you make** can be represented as an if statement!
- **If statements are used** in almost every program ever written!
- **You can nest if statements** as deep as you need!
- **If statements make programs** interactive and intelligent!

---

## Discussion Questions 💭

1. **What was the most interesting decision your program made?**
2. **How do you think if statements help make programs more useful?**
3. **What kind of real-world decisions could you program?**

---

## Next Up: While Loops! 🔄

In the next lesson, you'll learn how to make your programs repeat actions until conditions are met!

**Keep making smart decisions!** 🎉



