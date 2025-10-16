# Functions 🔧
## Organizing Your Code and Making It Reusable

### Learning Objectives
By the end of this lesson, students will:
- Create and use functions to organize code
- Understand function parameters and return values
- Use functions to make code reusable and modular
- Build complex programs using multiple functions

---

## What are Functions? 🤔

**Functions are reusable blocks of code that perform specific tasks!**

Think of functions as:
- **Mini-programs** that do one thing well
- **Tools in a toolbox** that you can use over and over
- **Recipes** that you can follow to get consistent results

### Real-World Analogy: Kitchen Appliances
- **Microwave** = Function that heats food
- **Blender** = Function that mixes ingredients
- **Oven** = Function that bakes food
- **Each appliance** does one job, but you can use them many times!

---

## Basic Function Structure 📝

### Simple Function
```python
def say_hello():
    print("Hello, World!")

# Call the function
say_hello()
```

### Function with Parameters
```python
def greet_person(name):
    print(f"Hello, {name}!")

# Call the function
greet_person("Alice")
greet_person("Bob")
```

### Function with Return Value
```python
def add_numbers(a, b):
    result = a + b
    return result

# Call the function and use the result
sum_result = add_numbers(5, 3)
print(f"5 + 3 = {sum_result}")
```

---

## Real-World Examples 🌟

### Example 1: Calculator Functions
```python
print("🧮 Calculator Functions 🧮")

def add(a, b):
    return a + b

def subtract(a, b):
    return a - b

def multiply(a, b):
    return a * b

def divide(a, b):
    if b != 0:
        return a / b
    else:
        return "Cannot divide by zero!"

def calculator():
    print("Calculator Menu:")
    print("1. Add")
    print("2. Subtract")
    print("3. Multiply")
    print("4. Divide")
    print("5. Exit")
    
    while True:
        choice = input("Enter your choice (1-5): ")
        
        if choice == "5":
            print("Goodbye!")
            break
        
        if choice in ["1", "2", "3", "4"]:
            try:
                num1 = float(input("Enter first number: "))
                num2 = float(input("Enter second number: "))
                
                if choice == "1":
                    result = add(num1, num2)
                    print(f"Result: {num1} + {num2} = {result}")
                elif choice == "2":
                    result = subtract(num1, num2)
                    print(f"Result: {num1} - {num2} = {result}")
                elif choice == "3":
                    result = multiply(num1, num2)
                    print(f"Result: {num1} × {num2} = {result}")
                elif choice == "4":
                    result = divide(num1, num2)
                    print(f"Result: {num1} ÷ {num2} = {result}")
                    
            except ValueError:
                print("Error: Please enter valid numbers!")
        else:
            print("Invalid choice! Please try again.")

# Run the calculator
calculator()
```

### Example 2: Student Grade System
```python
print("📚 Student Grade System Functions 📚")

def calculate_average(scores):
    if len(scores) == 0:
        return 0
    return sum(scores) / len(scores)

def get_grade(score):
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

def get_grade_description(grade):
    descriptions = {
        "A": "Excellent! Outstanding work!",
        "B": "Good job! Well done!",
        "C": "Satisfactory. Keep trying!",
        "D": "Needs improvement. Study harder!",
        "F": "Failing. Seek help immediately!"
    }
    return descriptions.get(grade, "Invalid grade!")

def process_student(name, scores):
    average = calculate_average(scores)
    grade = get_grade(average)
    description = get_grade_description(grade)
    
    print(f"\nStudent: {name}")
    print(f"Scores: {scores}")
    print(f"Average: {average:.2f}")
    print(f"Grade: {grade}")
    print(f"Description: {description}")
    
    return {"name": name, "average": average, "grade": grade}

def main():
    students = []
    
    while True:
        print("\nStudent Grade System:")
        print("1. Add student")
        print("2. View all students")
        print("3. Exit")
        
        choice = input("Enter your choice (1-3): ")
        
        if choice == "1":
            name = input("Enter student name: ")
            scores_input = input("Enter scores (comma-separated): ")
            scores = [float(score.strip()) for score in scores_input.split(",")]
            
            student = process_student(name, scores)
            students.append(student)
            
        elif choice == "2":
            if students:
                print("\nAll Students:")
                for student in students:
                    print(f"{student['name']}: {student['average']:.2f} ({student['grade']})")
            else:
                print("No students added yet.")
                
        elif choice == "3":
            print("Goodbye!")
            break
        else:
            print("Invalid choice! Please try again.")

# Run the program
main()
```

### Example 3: Weather App Functions
```python
print("🌤️ Weather App Functions 🌤️")

def get_weather_advice(weather, temperature):
    advice = ""
    
    if weather == "sunny":
        if temperature > 80:
            advice = "☀️ Hot and sunny! Wear sunscreen and stay hydrated!"
        elif temperature > 70:
            advice = "🌞 Perfect sunny day! Great for outdoor activities!"
        else:
            advice = "☀️ Sunny but cool! Wear a light jacket!"
    elif weather == "rainy":
        if temperature > 70:
            advice = "🌧️ Warm rain! Perfect for staying inside with hot chocolate!"
        else:
            advice = "🌧️ Cold rain! Stay inside and keep warm!"
    elif weather == "cloudy":
        if temperature > 75:
            advice = "☁️ Cloudy but warm! Good day for a walk!"
        else:
            advice = "☁️ Cloudy and cool! Perfect for indoor activities!"
    elif weather == "snowy":
        if temperature > 32:
            advice = "❄️ Light snow! Great for building snowmen!"
        else:
            advice = "❄️ Heavy snow! Stay inside and stay warm!"
    else:
        advice = "🤔 Unusual weather! Check local forecasts!"
    
    return advice

def get_clothing_recommendation(temperature):
    if temperature > 80:
        return "👕 Light clothing, shorts, sandals"
    elif temperature > 70:
        return "👔 Light shirt, pants, comfortable shoes"
    elif temperature > 60:
        return "🧥 Light jacket, long pants"
    elif temperature > 50:
        return "🧥 Jacket, long pants, closed shoes"
    else:
        return "🧥 Heavy jacket, warm clothes, boots"

def get_activity_suggestion(weather, temperature):
    if weather == "sunny" and temperature > 70:
        return "🏖️ Beach, hiking, outdoor sports"
    elif weather == "rainy":
        return "🏠 Indoor activities, reading, movies"
    elif weather == "snowy":
        return "⛷️ Skiing, snowboarding, building snowmen"
    else:
        return "🚶 Walking, shopping, indoor activities"

def weather_app():
    while True:
        print("\n🌤️ Weather App:")
        print("1. Get weather advice")
        print("2. Get clothing recommendation")
        print("3. Get activity suggestion")
        print("4. Exit")
        
        choice = input("Enter your choice (1-4): ")
        
        if choice == "1":
            weather = input("What's the weather? (sunny/rainy/cloudy/snowy): ").lower()
            temperature = int(input("What's the temperature? "))
            
            advice = get_weather_advice(weather, temperature)
            print(f"\nWeather Advice: {advice}")
            
        elif choice == "2":
            temperature = int(input("What's the temperature? "))
            
            clothing = get_clothing_recommendation(temperature)
            print(f"\nClothing Recommendation: {clothing}")
            
        elif choice == "3":
            weather = input("What's the weather? (sunny/rainy/cloudy/snowy): ").lower()
            temperature = int(input("What's the temperature? "))
            
            activity = get_activity_suggestion(weather, temperature)
            print(f"\nActivity Suggestion: {activity}")
            
        elif choice == "4":
            print("Goodbye!")
            break
        else:
            print("Invalid choice! Please try again.")

# Run the weather app
weather_app()
```

---

## Interactive Examples 🎮

### Example 1: Game Functions
```python
print("🎮 Game Functions 🎮")

import random

def roll_dice():
    return random.randint(1, 6)

def calculate_damage(attack, defense):
    damage = attack - defense
    return max(0, damage)  # Damage can't be negative

def check_critical_hit(attack_roll):
    return attack_roll == 20  # Critical hit on 20

def battle_round(player_attack, player_defense, enemy_attack, enemy_defense):
    print("⚔️ Battle Round!")
    
    # Player attacks
    player_roll = roll_dice()
    print(f"Player rolls: {player_roll}")
    
    if check_critical_hit(player_roll):
        print("🎯 Critical hit!")
        player_damage = calculate_damage(player_attack * 2, enemy_defense)
    else:
        player_damage = calculate_damage(player_attack, enemy_defense)
    
    print(f"Player deals {player_damage} damage!")
    
    # Enemy attacks
    enemy_roll = roll_dice()
    print(f"Enemy rolls: {enemy_roll}")
    
    if check_critical_hit(enemy_roll):
        print("🎯 Critical hit!")
        enemy_damage = calculate_damage(enemy_attack * 2, player_defense)
    else:
        enemy_damage = calculate_damage(enemy_attack, player_defense)
    
    print(f"Enemy deals {enemy_damage} damage!")
    
    return player_damage, enemy_damage

def play_battle_game():
    player_health = 100
    enemy_health = 100
    round_count = 0
    
    print("Welcome to the Battle Game!")
    print("You have 100 health. Defeat the enemy!")
    
    while player_health > 0 and enemy_health > 0:
        round_count += 1
        print(f"\n--- Round {round_count} ---")
        print(f"Player Health: {player_health}")
        print(f"Enemy Health: {enemy_health}")
        
        player_attack = int(input("Enter your attack power (1-20): "))
        player_defense = int(input("Enter your defense (1-20): "))
        
        enemy_attack = random.randint(5, 15)
        enemy_defense = random.randint(3, 10)
        
        player_damage, enemy_damage = battle_round(
            player_attack, player_defense, enemy_attack, enemy_defense
        )
        
        enemy_health -= player_damage
        player_health -= enemy_damage
        
        if enemy_health <= 0:
            print("🎉 You won the battle!")
            break
        elif player_health <= 0:
            print("💀 You lost the battle!")
            break

# Play the game
play_battle_game()
```

### Example 2: Library Management Functions
```python
print("📚 Library Management Functions 📚")

def add_book(library, title, author, isbn):
    book = {
        "title": title,
        "author": author,
        "isbn": isbn,
        "available": True
    }
    library.append(book)
    return f"Added book: {title} by {author}"

def search_books(library, search_term):
    found_books = []
    for book in library:
        if (search_term.lower() in book["title"].lower() or 
            search_term.lower() in book["author"].lower()):
            found_books.append(book)
    return found_books

def borrow_book(library, title):
    for book in library:
        if book["title"].lower() == title.lower() and book["available"]:
            book["available"] = False
            return f"Borrowed: {book['title']}"
    return "Book not found or already borrowed"

def return_book(library, title):
    for book in library:
        if book["title"].lower() == title.lower() and not book["available"]:
            book["available"] = True
            return f"Returned: {book['title']}"
    return "Book not found or already returned"

def display_books(library):
    if not library:
        print("No books in library.")
        return
    
    print("\n📚 Library Books:")
    for i, book in enumerate(library, 1):
        status = "Available" if book["available"] else "Borrowed"
        print(f"{i}. {book['title']} by {book['author']} - {status}")

def library_management():
    library = []
    
    while True:
        print("\n📚 Library Management System:")
        print("1. Add Book")
        print("2. Search Books")
        print("3. Borrow Book")
        print("4. Return Book")
        print("5. Display All Books")
        print("6. Exit")
        
        choice = input("Enter your choice (1-6): ")
        
        if choice == "1":
            title = input("Enter book title: ")
            author = input("Enter author: ")
            isbn = input("Enter ISBN: ")
            result = add_book(library, title, author, isbn)
            print(result)
            
        elif choice == "2":
            search_term = input("Enter search term: ")
            found_books = search_books(library, search_term)
            if found_books:
                print(f"\nFound {len(found_books)} book(s):")
                for book in found_books:
                    status = "Available" if book["available"] else "Borrowed"
                    print(f"- {book['title']} by {book['author']} - {status}")
            else:
                print("No books found.")
                
        elif choice == "3":
            title = input("Enter book title to borrow: ")
            result = borrow_book(library, title)
            print(result)
            
        elif choice == "4":
            title = input("Enter book title to return: ")
            result = return_book(library, title)
            print(result)
            
        elif choice == "5":
            display_books(library)
            
        elif choice == "6":
            print("Goodbye!")
            break
        else:
            print("Invalid choice! Please try again.")

# Run the library management system
library_management()
```

### Example 3: Math Helper Functions
```python
print("🧮 Math Helper Functions 🧮")

def is_prime(n):
    if n < 2:
        return False
    for i in range(2, int(n ** 0.5) + 1):
        if n % i == 0:
            return False
    return True

def factorial(n):
    if n < 0:
        return "Factorial not defined for negative numbers"
    if n == 0 or n == 1:
        return 1
    result = 1
    for i in range(2, n + 1):
        result *= i
    return result

def fibonacci(n):
    if n <= 0:
        return "Fibonacci not defined for non-positive numbers"
    if n == 1 or n == 2:
        return 1
    
    a, b = 1, 1
    for i in range(3, n + 1):
        a, b = b, a + b
    return b

def calculate_area(shape, *args):
    if shape == "rectangle":
        length, width = args
        return length * width
    elif shape == "circle":
        radius = args[0]
        return 3.14159 * radius ** 2
    elif shape == "triangle":
        base, height = args
        return 0.5 * base * height
    else:
        return "Unknown shape"

def math_helper():
    while True:
        print("\n🧮 Math Helper:")
        print("1. Check if number is prime")
        print("2. Calculate factorial")
        print("3. Calculate Fibonacci number")
        print("4. Calculate area")
        print("5. Exit")
        
        choice = input("Enter your choice (1-5): ")
        
        if choice == "1":
            try:
                n = int(input("Enter a number: "))
                if is_prime(n):
                    print(f"{n} is prime!")
                else:
                    print(f"{n} is not prime.")
            except ValueError:
                print("Please enter a valid number!")
                
        elif choice == "2":
            try:
                n = int(input("Enter a number: "))
                result = factorial(n)
                print(f"{n}! = {result}")
            except ValueError:
                print("Please enter a valid number!")
                
        elif choice == "3":
            try:
                n = int(input("Enter a number: "))
                result = fibonacci(n)
                print(f"Fibonacci({n}) = {result}")
            except ValueError:
                print("Please enter a valid number!")
                
        elif choice == "4":
            print("Choose shape:")
            print("1. Rectangle")
            print("2. Circle")
            print("3. Triangle")
            
            shape_choice = input("Enter your choice (1-3): ")
            
            if shape_choice == "1":
                try:
                    length = float(input("Enter length: "))
                    width = float(input("Enter width: "))
                    area = calculate_area("rectangle", length, width)
                    print(f"Rectangle area: {area}")
                except ValueError:
                    print("Please enter valid numbers!")
                    
            elif shape_choice == "2":
                try:
                    radius = float(input("Enter radius: "))
                    area = calculate_area("circle", radius)
                    print(f"Circle area: {area}")
                except ValueError:
                    print("Please enter a valid number!")
                    
            elif shape_choice == "3":
                try:
                    base = float(input("Enter base: "))
                    height = float(input("Enter height: "))
                    area = calculate_area("triangle", base, height)
                    print(f"Triangle area: {area}")
                except ValueError:
                    print("Please enter valid numbers!")
            else:
                print("Invalid choice!")
                
        elif choice == "5":
            print("Goodbye!")
            break
        else:
            print("Invalid choice! Please try again.")

# Run the math helper
math_helper()
```

---

## Advanced Function Concepts 🚀

### Default Parameters
```python
def greet_person(name, greeting="Hello"):
    print(f"{greeting}, {name}!")

greet_person("Alice")  # Uses default greeting
greet_person("Bob", "Hi")  # Uses custom greeting
```

### Variable Number of Arguments
```python
def add_multiple(*numbers):
    total = 0
    for num in numbers:
        total += num
    return total

result = add_multiple(1, 2, 3, 4, 5)
print(f"Sum: {result}")
```

### Keyword Arguments
```python
def create_person(name, age, city="Unknown", country="Unknown"):
    return {
        "name": name,
        "age": age,
        "city": city,
        "country": country
    }

person1 = create_person("Alice", 25)
person2 = create_person("Bob", 30, city="New York")
person3 = create_person("Charlie", 35, city="London", country="UK")
```

---

## Common Mistakes (And How to Fix Them!) ❌➡️✅

### Mistake 1: Forgetting to Call the Function
```python
# ❌ Wrong - Function defined but not called
def say_hello():
    print("Hello, World!")

# ✅ Correct - Call the function
def say_hello():
    print("Hello, World!")

say_hello()  # Don't forget to call it!
```

### Mistake 2: Not Using Return Values
```python
# ❌ Wrong - Not using the return value
def add_numbers(a, b):
    return a + b

add_numbers(5, 3)  # Return value is ignored

# ✅ Correct - Use the return value
def add_numbers(a, b):
    return a + b

result = add_numbers(5, 3)
print(f"Result: {result}")
```

### Mistake 3: Wrong Parameter Order
```python
# ❌ Wrong - Parameters in wrong order
def divide(a, b):
    return a / b

result = divide(3, 5)  # This gives 0.6, not 1.67

# ✅ Correct - Parameters in right order
def divide(a, b):
    return a / b

result = divide(5, 3)  # This gives 1.67
```

---

## Fun Challenges! 🎯

### Challenge 1: Text Adventure Game Functions
Create a text adventure game using functions:

```python
print("🗺️ Text Adventure Game Functions 🗺️")

def show_status(health, inventory, location):
    print(f"\n🏥 Health: {health}")
    print(f"🎒 Inventory: {inventory}")
    print(f"📍 Location: {location}")

def move_to(location):
    print(f"You move to {location}")
    return location

def take_item(inventory, item):
    inventory.append(item)
    print(f"You picked up {item}")
    return inventory

def use_item(inventory, item):
    if item in inventory:
        inventory.remove(item)
        print(f"You used {item}")
        return inventory, True
    else:
        print(f"You don't have {item}")
        return inventory, False

def explore_forest(health, inventory):
    print("🌲 You explore the forest...")
    print("You find a healing potion!")
    inventory = take_item(inventory, "healing potion")
    return health, inventory

def explore_cave(health, inventory):
    print("🕳️ You explore the cave...")
    print("A bat attacks you!")
    health -= 20
    print(f"You lose 20 health! Health: {health}")
    return health, inventory

def use_healing_potion(health, inventory):
    inventory, used = use_item(inventory, "healing potion")
    if used:
        health = min(100, health + 30)
        print(f"You heal 30 health! Health: {health}")
    return health, inventory

def play_adventure():
    health = 100
    inventory = []
    location = "forest"
    
    print("Welcome to the Adventure Game!")
    print("You find yourself in a mysterious forest...")
    
    while health > 0:
        show_status(health, inventory, location)
        
        print("\nWhat do you do?")
        print("1. Explore current location")
        print("2. Move to forest")
        print("3. Move to cave")
        print("4. Use healing potion")
        print("5. Quit")
        
        choice = input("Enter your choice (1-5): ")
        
        if choice == "1":
            if location == "forest":
                health, inventory = explore_forest(health, inventory)
            elif location == "cave":
                health, inventory = explore_cave(health, inventory)
                
        elif choice == "2":
            location = move_to("forest")
            
        elif choice == "3":
            location = move_to("cave")
            
        elif choice == "4":
            health, inventory = use_healing_potion(health, inventory)
            
        elif choice == "5":
            print("Thanks for playing!")
            break
        else:
            print("Invalid choice!")
        
        if health <= 0:
            print("💀 Game Over! You died!")
            break

# Play the game
play_adventure()
```

### Challenge 2: Quiz System Functions
Create a quiz system using functions:

```python
print("📝 Quiz System Functions 📝")

def load_questions():
    return [
        {
            "question": "What is the capital of France?",
            "options": ["London", "Paris", "Berlin", "Madrid"],
            "correct": 1
        },
        {
            "question": "What is 2 + 2?",
            "options": ["3", "4", "5", "6"],
            "correct": 1
        },
        {
            "question": "What is the largest planet in our solar system?",
            "options": ["Earth", "Jupiter", "Saturn", "Neptune"],
            "correct": 1
        },
        {
            "question": "What is the chemical symbol for water?",
            "options": ["H2O", "CO2", "NaCl", "O2"],
            "correct": 0
        },
        {
            "question": "Who painted the Mona Lisa?",
            "options": ["Van Gogh", "Picasso", "Da Vinci", "Monet"],
            "correct": 2
        }
    ]

def display_question(question, question_num):
    print(f"\nQuestion {question_num}: {question['question']}")
    for i, option in enumerate(question['options']):
        print(f"{i + 1}. {option}")

def get_user_answer():
    while True:
        try:
            answer = int(input("Enter your answer (1-4): "))
            if 1 <= answer <= 4:
                return answer
            else:
                print("Please enter a number between 1 and 4!")
        except ValueError:
            print("Please enter a valid number!")

def check_answer(question, user_answer):
    correct_answer = question['correct'] + 1
    if user_answer == correct_answer:
        print("✅ Correct!")
        return True
    else:
        print(f"❌ Wrong! The correct answer is: {question['options'][question['correct']]}")
        return False

def calculate_score(correct_answers, total_questions):
    percentage = (correct_answers / total_questions) * 100
    return percentage

def display_results(score, total_questions):
    percentage = calculate_score(score, total_questions)
    print(f"\n📊 Quiz Results:")
    print(f"Score: {score}/{total_questions}")
    print(f"Percentage: {percentage:.1f}%")
    
    if percentage >= 90:
        print("🏆 Excellent! You're a quiz master!")
    elif percentage >= 80:
        print("⭐ Great job! You did very well!")
    elif percentage >= 70:
        print("👍 Good work! You passed!")
    else:
        print("💪 Keep studying! You'll do better next time!")

def run_quiz():
    questions = load_questions()
    score = 0
    
    print("Welcome to the Quiz System!")
    print("Answer the questions to test your knowledge.")
    
    for i, question in enumerate(questions, 1):
        display_question(question, i)
        user_answer = get_user_answer()
        
        if check_answer(question, user_answer):
            score += 1
    
    display_results(score, len(questions))

# Run the quiz
run_quiz()
```

### Challenge 3: Bank Account Functions
Create a bank account system using functions:

```python
print("🏦 Bank Account Functions 🏦")

def create_account(account_number, initial_balance=0):
    return {
        "account_number": account_number,
        "balance": initial_balance,
        "transactions": []
    }

def deposit(account, amount):
    if amount > 0:
        account["balance"] += amount
        account["transactions"].append(f"Deposit: +${amount}")
        return f"Deposited ${amount}. New balance: ${account['balance']}"
    else:
        return "Deposit amount must be positive!"

def withdraw(account, amount):
    if amount > 0:
        if amount <= account["balance"]:
            account["balance"] -= amount
            account["transactions"].append(f"Withdrawal: -${amount}")
            return f"Withdrew ${amount}. New balance: ${account['balance']}"
        else:
            return "Insufficient funds!"
    else:
        return "Withdrawal amount must be positive!"

def get_balance(account):
    return account["balance"]

def get_transactions(account):
    return account["transactions"]

def display_account_info(account):
    print(f"\n🏦 Account Information:")
    print(f"Account Number: {account['account_number']}")
    print(f"Balance: ${account['balance']}")
    print(f"Transactions: {len(account['transactions'])}")

def bank_system():
    accounts = {}
    
    while True:
        print("\n🏦 Bank System:")
        print("1. Create Account")
        print("2. Deposit")
        print("3. Withdraw")
        print("4. Check Balance")
        print("5. View Transactions")
        print("6. Exit")
        
        choice = input("Enter your choice (1-6): ")
        
        if choice == "1":
            account_number = input("Enter account number: ")
            if account_number in accounts:
                print("Account already exists!")
            else:
                initial_balance = float(input("Enter initial balance: $"))
                accounts[account_number] = create_account(account_number, initial_balance)
                print(f"Account {account_number} created with balance ${initial_balance}")
                
        elif choice == "2":
            account_number = input("Enter account number: ")
            if account_number in accounts:
                amount = float(input("Enter deposit amount: $"))
                result = deposit(accounts[account_number], amount)
                print(result)
            else:
                print("Account not found!")
                
        elif choice == "3":
            account_number = input("Enter account number: ")
            if account_number in accounts:
                amount = float(input("Enter withdrawal amount: $"))
                result = withdraw(accounts[account_number], amount)
                print(result)
            else:
                print("Account not found!")
                
        elif choice == "4":
            account_number = input("Enter account number: ")
            if account_number in accounts:
                balance = get_balance(accounts[account_number])
                print(f"Balance: ${balance}")
            else:
                print("Account not found!")
                
        elif choice == "5":
            account_number = input("Enter account number: ")
            if account_number in accounts:
                transactions = get_transactions(accounts[account_number])
                if transactions:
                    print(f"\nTransactions for account {account_number}:")
                    for i, transaction in enumerate(transactions, 1):
                        print(f"{i}. {transaction}")
                else:
                    print("No transactions yet.")
            else:
                print("Account not found!")
                
        elif choice == "6":
            print("Goodbye!")
            break
        else:
            print("Invalid choice! Please try again.")

# Run the bank system
bank_system()
```

---

## What's Next? 🚀

You've learned how to create and use functions! Now you can:
- Organize your code into reusable blocks
- Make your programs more modular and maintainable
- Build complex programs step by step

**In the next lesson, you'll learn:**
- How to create capstone projects that combine all concepts
- How to build real-world applications
- How to continue your programming journey!

---

## Practice Time! 💪

**Try these exercises:**

1. **Create a function that calculates the area of different shapes**
2. **Make a function that validates email addresses**
3. **Build a function that generates random passwords**
4. **Design a function that sorts a list of numbers**

**Remember:** Functions make your code more organized and reusable!

---

## Fun Facts! 🎉

- **Functions are the building blocks** of all programming!
- **You can call functions** from other functions!
- **Functions make code** easier to test and debug!
- **Every programming language** uses functions!

---

## Discussion Questions 💭

1. **What was the most useful function you created?**
2. **How do you think functions help organize code?**
3. **What kind of real-world problems could you solve with functions?**

---

## Next Up: Capstone Projects! 🏆

In the next lesson, you'll learn how to create capstone projects that combine all the concepts you've learned!

**Keep building and creating!** 🎉

