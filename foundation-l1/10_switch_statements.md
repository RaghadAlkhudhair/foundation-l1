# Switch Statements 🔀
## Multiple Choices and Better Organization

### Learning Objectives
By the end of this lesson, students will:
- Use if-elif-else chains for multiple choices
- Understand when to use switch-like patterns
- Create menu-driven programs
- Organize complex decision-making logic

---

## What are Switch Statements? 🤔

**Switch statements help you handle multiple choices in an organized way!**

Think of switch statements as:
- **Menu systems** that offer different options
- **Traffic directors** that route to different paths
- **Smart organizers** that group related decisions

### Real-World Analogy: Restaurant Menu
- **If** you want pizza → Go to pizza section
- **If** you want burgers → Go to burger section
- **If** you want salads → Go to salad section
- **Otherwise** → Ask the waiter for help

---

## Python's Switch Alternative: If-Elif-Else Chains 📝

### Basic Structure
```python
choice = input("Enter your choice: ")

if choice == "1":
    print("You chose option 1!")
elif choice == "2":
    print("You chose option 2!")
elif choice == "3":
    print("You chose option 3!")
else:
    print("Invalid choice!")
```

### With Numbers
```python
choice = int(input("Enter a number (1-5): "))

if choice == 1:
    print("One")
elif choice == 2:
    print("Two")
elif choice == 3:
    print("Three")
elif choice == 4:
    print("Four")
elif choice == 5:
    print("Five")
else:
    print("Number out of range!")
```

---

## Real-World Examples 🌟

### Example 1: Calculator Menu
```python
print("🧮 Calculator Menu 🧮")

while True:
    print("\nChoose an operation:")
    print("1. Add")
    print("2. Subtract")
    print("3. Multiply")
    print("4. Divide")
    print("5. Exit")
    
    choice = input("Enter your choice (1-5): ")
    
    if choice == "1":
        num1 = float(input("Enter first number: "))
        num2 = float(input("Enter second number: "))
        result = num1 + num2
        print(f"Result: {num1} + {num2} = {result}")
        
    elif choice == "2":
        num1 = float(input("Enter first number: "))
        num2 = float(input("Enter second number: "))
        result = num1 - num2
        print(f"Result: {num1} - {num2} = {result}")
        
    elif choice == "3":
        num1 = float(input("Enter first number: "))
        num2 = float(input("Enter second number: "))
        result = num1 * num2
        print(f"Result: {num1} × {num2} = {result}")
        
    elif choice == "4":
        num1 = float(input("Enter first number: "))
        num2 = float(input("Enter second number: "))
        if num2 != 0:
            result = num1 / num2
            print(f"Result: {num1} ÷ {num2} = {result}")
        else:
            print("Error: Cannot divide by zero!")
            
    elif choice == "5":
        print("Goodbye!")
        break
        
    else:
        print("Invalid choice! Please try again.")
```

### Example 2: Student Grade System
```python
print("📚 Student Grade System 📚")

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
    if grade == "A":
        return "Excellent! Outstanding work!"
    elif grade == "B":
        return "Good job! Well done!"
    elif grade == "C":
        return "Satisfactory. Keep trying!"
    elif grade == "D":
        return "Needs improvement. Study harder!"
    elif grade == "F":
        return "Failing. Seek help immediately!"
    else:
        return "Invalid grade!"

while True:
    print("\nStudent Grade System:")
    print("1. Enter student score")
    print("2. View grade scale")
    print("3. Exit")
    
    choice = input("Enter your choice (1-3): ")
    
    if choice == "1":
        name = input("Enter student name: ")
        score = float(input("Enter score (0-100): "))
        
        if 0 <= score <= 100:
            grade = get_grade(score)
            description = get_grade_description(grade)
            
            print(f"\nStudent: {name}")
            print(f"Score: {score}")
            print(f"Grade: {grade}")
            print(f"Description: {description}")
        else:
            print("Invalid score! Please enter a score between 0 and 100.")
            
    elif choice == "2":
        print("\nGrade Scale:")
        print("A: 90-100 (Excellent)")
        print("B: 80-89 (Good)")
        print("C: 70-79 (Satisfactory)")
        print("D: 60-69 (Needs Improvement)")
        print("F: 0-59 (Failing)")
        
    elif choice == "3":
        print("Goodbye!")
        break
        
    else:
        print("Invalid choice! Please try again.")
```

### Example 3: Weather App Menu
```python
print("🌤️ Weather App Menu 🌤️")

def get_weather_advice(weather, temperature):
    if weather == "sunny":
        if temperature > 80:
            return "☀️ Hot and sunny! Wear sunscreen and stay hydrated!"
        elif temperature > 70:
            return "🌞 Perfect sunny day! Great for outdoor activities!"
        else:
            return "☀️ Sunny but cool! Wear a light jacket!"
            
    elif weather == "rainy":
        if temperature > 70:
            return "🌧️ Warm rain! Perfect for staying inside with hot chocolate!"
        else:
            return "🌧️ Cold rain! Stay inside and keep warm!"
            
    elif weather == "cloudy":
        if temperature > 75:
            return "☁️ Cloudy but warm! Good day for a walk!"
        else:
            return "☁️ Cloudy and cool! Perfect for indoor activities!"
            
    elif weather == "snowy":
        if temperature > 32:
            return "❄️ Light snow! Great for building snowmen!"
        else:
            return "❄️ Heavy snow! Stay inside and stay warm!"
            
    else:
        return "🤔 Unusual weather! Check local forecasts!"

while True:
    print("\nWeather App:")
    print("1. Get weather advice")
    print("2. View weather types")
    print("3. Temperature guide")
    print("4. Exit")
    
    choice = input("Enter your choice (1-4): ")
    
    if choice == "1":
        weather = input("What's the weather? (sunny/rainy/cloudy/snowy): ").lower()
        temperature = int(input("What's the temperature? "))
        
        advice = get_weather_advice(weather, temperature)
        print(f"\nWeather Advice: {advice}")
        
    elif choice == "2":
        print("\nWeather Types:")
        print("☀️ Sunny - Clear skies with sunshine")
        print("🌧️ Rainy - Precipitation falling from clouds")
        print("☁️ Cloudy - Sky covered with clouds")
        print("❄️ Snowy - Frozen precipitation falling")
        
    elif choice == "3":
        print("\nTemperature Guide:")
        print("🥵 80°F+ - Hot weather")
        print("🌞 70-79°F - Warm weather")
        print("🌤️ 60-69°F - Mild weather")
        print("🧥 50-59°F - Cool weather")
        print("🥶 Below 50°F - Cold weather")
        
    elif choice == "4":
        print("Goodbye!")
        break
        
    else:
        print("Invalid choice! Please try again.")
```

---

## Interactive Examples 🎮

### Example 1: Game Menu System
```python
print("🎮 Game Menu System 🎮")

def play_guessing_game():
    import random
    number = random.randint(1, 100)
    guesses = 0
    max_guesses = 7
    
    print("I'm thinking of a number between 1 and 100!")
    print("You have 7 guesses. Good luck!")
    
    while guesses < max_guesses:
        guess = int(input("Enter your guess: "))
        guesses += 1
        
        if guess == number:
            print(f"🎉 Congratulations! You guessed it in {guesses} tries!")
            return
        elif guess < number:
            print("Too low! Try higher.")
        else:
            print("Too high! Try lower.")
    
    print(f"😞 Game over! The number was {number}")

def play_math_quiz():
    import random
    score = 0
    questions = 5
    
    print("Let's test your math skills!")
    
    for i in range(questions):
        num1 = random.randint(1, 10)
        num2 = random.randint(1, 10)
        operation = random.choice(['+', '-', '*'])
        
        if operation == '+':
            answer = num1 + num2
        elif operation == '-':
            answer = num1 - num2
        else:
            answer = num1 * num2
        
        user_answer = int(input(f"What is {num1} {operation} {num2}? "))
        
        if user_answer == answer:
            print("✅ Correct!")
            score += 1
        else:
            print(f"❌ Wrong! The answer is {answer}")
    
    print(f"\nQuiz complete! You got {score}/{questions} correct!")
    if score == questions:
        print("🏆 Perfect score! You're a math genius!")
    elif score >= questions * 0.8:
        print("⭐ Great job! You're doing well!")
    else:
        print("💪 Keep practicing! You'll get better!")

def play_word_game():
    words = ["python", "programming", "computer", "algorithm", "function"]
    word = random.choice(words)
    guessed_letters = []
    wrong_guesses = 0
    max_wrong = 6
    
    print("Guess the word! I'll give you hints.")
    print("You have 6 wrong guesses allowed.")
    
    while wrong_guesses < max_wrong:
        display = ""
        for letter in word:
            if letter in guessed_letters:
                display += letter
            else:
                display += "_"
        
        print(f"Word: {display}")
        print(f"Guessed letters: {guessed_letters}")
        print(f"Wrong guesses left: {max_wrong - wrong_guesses}")
        
        if display == word:
            print("🎉 Congratulations! You guessed the word!")
            return
        
        guess = input("Guess a letter: ").lower()
        
        if guess in guessed_letters:
            print("You already guessed that letter!")
        elif guess in word:
            print("✅ Good guess!")
            guessed_letters.append(guess)
        else:
            print("❌ Wrong guess!")
            guessed_letters.append(guess)
            wrong_guesses += 1
    
    print(f"😞 Game over! The word was: {word}")

while True:
    print("\n🎮 Game Menu:")
    print("1. Number Guessing Game")
    print("2. Math Quiz")
    print("3. Word Guessing Game")
    print("4. Exit")
    
    choice = input("Enter your choice (1-4): ")
    
    if choice == "1":
        play_guessing_game()
    elif choice == "2":
        play_math_quiz()
    elif choice == "3":
        play_word_game()
    elif choice == "4":
        print("Thanks for playing! Goodbye!")
        break
    else:
        print("Invalid choice! Please try again.")
```

### Example 2: Personal Finance Manager
```python
print("💰 Personal Finance Manager 💰")

balance = 1000.0
transactions = []

def add_transaction(amount, description, transaction_type):
    global balance
    if transaction_type == "income":
        balance += amount
        transactions.append(f"Income: +${amount} - {description}")
    else:
        balance -= amount
        transactions.append(f"Expense: -${amount} - {description}")

def view_balance():
    print(f"\n💰 Current Balance: ${balance:.2f}")

def view_transactions():
    if not transactions:
        print("\n📄 No transactions yet.")
    else:
        print("\n📄 Transaction History:")
        for i, transaction in enumerate(transactions, 1):
            print(f"{i}. {transaction}")

def add_income():
    amount = float(input("Enter income amount: $"))
    description = input("Enter description: ")
    add_transaction(amount, description, "income")
    print(f"✅ Added income: +${amount}")

def add_expense():
    amount = float(input("Enter expense amount: $"))
    description = input("Enter description: ")
    add_transaction(amount, description, "expense")
    print(f"✅ Added expense: -${amount}")

def get_financial_advice():
    if balance > 2000:
        print("🏆 Excellent! You're doing great with your finances!")
        print("Consider investing some money for the future.")
    elif balance > 1000:
        print("👍 Good job! You're managing your money well.")
        print("Keep saving and avoid unnecessary expenses.")
    elif balance > 500:
        print("⚠️ Be careful with your spending.")
        print("Try to save more and reduce expenses.")
    else:
        print("🚨 Warning! Your balance is low.")
        print("Focus on increasing income and reducing expenses.")

while True:
    print("\n💰 Personal Finance Manager:")
    print("1. View Balance")
    print("2. Add Income")
    print("3. Add Expense")
    print("4. View Transactions")
    print("5. Financial Advice")
    print("6. Exit")
    
    choice = input("Enter your choice (1-6): ")
    
    if choice == "1":
        view_balance()
    elif choice == "2":
        add_income()
    elif choice == "3":
        add_expense()
    elif choice == "4":
        view_transactions()
    elif choice == "5":
        get_financial_advice()
    elif choice == "6":
        print("Goodbye! Keep managing your finances wisely!")
        break
    else:
        print("Invalid choice! Please try again.")
```

### Example 3: Library Management System
```python
print("📚 Library Management System 📚")

books = []
borrowed_books = []

def add_book():
    title = input("Enter book title: ")
    author = input("Enter author: ")
    isbn = input("Enter ISBN: ")
    
    book = {
        "title": title,
        "author": author,
        "isbn": isbn,
        "available": True
    }
    
    books.append(book)
    print(f"✅ Added book: {title} by {author}")

def search_books():
    search_term = input("Enter search term (title or author): ").lower()
    found_books = []
    
    for book in books:
        if (search_term in book["title"].lower() or 
            search_term in book["author"].lower()):
            found_books.append(book)
    
    if found_books:
        print(f"\n📖 Found {len(found_books)} book(s):")
        for i, book in enumerate(found_books, 1):
            status = "Available" if book["available"] else "Borrowed"
            print(f"{i}. {book['title']} by {book['author']} - {status}")
    else:
        print("No books found matching your search.")

def borrow_book():
    if not books:
        print("No books available in the library.")
        return
    
    print("\nAvailable books:")
    available_books = [book for book in books if book["available"]]
    
    if not available_books:
        print("No books are currently available.")
        return
    
    for i, book in enumerate(available_books, 1):
        print(f"{i}. {book['title']} by {book['author']}")
    
    try:
        choice = int(input("Enter book number to borrow: ")) - 1
        if 0 <= choice < len(available_books):
            book = available_books[choice]
            book["available"] = False
            borrowed_books.append(book)
            print(f"✅ Borrowed: {book['title']}")
        else:
            print("Invalid book number!")
    except ValueError:
        print("Please enter a valid number!")

def return_book():
    if not borrowed_books:
        print("No books are currently borrowed.")
        return
    
    print("\nBorrowed books:")
    for i, book in enumerate(borrowed_books, 1):
        print(f"{i}. {book['title']} by {book['author']}")
    
    try:
        choice = int(input("Enter book number to return: ")) - 1
        if 0 <= choice < len(borrowed_books):
            book = borrowed_books[choice]
            book["available"] = True
            borrowed_books.remove(book)
            print(f"✅ Returned: {book['title']}")
        else:
            print("Invalid book number!")
    except ValueError:
        print("Please enter a valid number!")

def view_library_status():
    total_books = len(books)
    available_books = len([book for book in books if book["available"]])
    borrowed_books_count = len(borrowed_books)
    
    print(f"\n📊 Library Status:")
    print(f"Total books: {total_books}")
    print(f"Available: {available_books}")
    print(f"Borrowed: {borrowed_books_count}")

while True:
    print("\n📚 Library Management System:")
    print("1. Add Book")
    print("2. Search Books")
    print("3. Borrow Book")
    print("4. Return Book")
    print("5. View Library Status")
    print("6. Exit")
    
    choice = input("Enter your choice (1-6): ")
    
    if choice == "1":
        add_book()
    elif choice == "2":
        search_books()
    elif choice == "3":
        borrow_book()
    elif choice == "4":
        return_book()
    elif choice == "5":
        view_library_status()
    elif choice == "6":
        print("Goodbye! Thanks for using the library system!")
        break
    else:
        print("Invalid choice! Please try again.")
```

---

## Advanced Switch Patterns 🎯

### Example 1: State Machine
```python
print("🔄 State Machine Example 🔄")

class TrafficLight:
    def __init__(self):
        self.state = "red"
        self.timer = 0
    
    def change_state(self):
        if self.state == "red":
            self.state = "green"
            self.timer = 30
            return "🟢 Light changed to GREEN for 30 seconds"
        elif self.state == "green":
            self.state = "yellow"
            self.timer = 5
            return "🟡 Light changed to YELLOW for 5 seconds"
        elif self.state == "yellow":
            self.state = "red"
            self.timer = 20
            return "🔴 Light changed to RED for 20 seconds"
    
    def get_status(self):
        if self.state == "red":
            return "🔴 RED - Stop!"
        elif self.state == "green":
            return "🟢 GREEN - Go!"
        elif self.state == "yellow":
            return "🟡 YELLOW - Slow down!"
    
    def tick(self):
        if self.timer > 0:
            self.timer -= 1
            if self.timer == 0:
                return self.change_state()
        return None

# Create traffic light
light = TrafficLight()

while True:
    print(f"\n🚦 Traffic Light Status: {light.get_status()}")
    print(f"⏰ Timer: {light.timer} seconds")
    
    print("\nOptions:")
    print("1. Wait (tick timer)")
    print("2. Force change")
    print("3. Exit")
    
    choice = input("Enter your choice (1-3): ")
    
    if choice == "1":
        result = light.tick()
        if result:
            print(result)
    elif choice == "2":
        result = light.change_state()
        print(result)
    elif choice == "3":
        print("Goodbye!")
        break
    else:
        print("Invalid choice! Please try again.")
```

### Example 2: Command Pattern
```python
print("🎮 Command Pattern Example 🎮")

class GameCharacter:
    def __init__(self, name):
        self.name = name
        self.health = 100
        self.energy = 100
        self.position = [0, 0]
    
    def move(self, direction):
        if direction == "north":
            self.position[1] += 1
            return f"{self.name} moved north to position {self.position}"
        elif direction == "south":
            self.position[1] -= 1
            return f"{self.name} moved south to position {self.position}"
        elif direction == "east":
            self.position[0] += 1
            return f"{self.name} moved east to position {self.position}"
        elif direction == "west":
            self.position[0] -= 1
            return f"{self.name} moved west to position {self.position}"
        else:
            return "Invalid direction!"
    
    def attack(self):
        if self.energy >= 10:
            self.energy -= 10
            return f"{self.name} attacks! Energy: {self.energy}"
        else:
            return f"{self.name} is too tired to attack! Energy: {self.energy}"
    
    def rest(self):
        self.energy = min(100, self.energy + 20)
        return f"{self.name} rests. Energy: {self.energy}"
    
    def get_status(self):
        return f"{self.name} - Health: {self.health}, Energy: {self.energy}, Position: {self.position}"

# Create character
character = GameCharacter("Hero")

while True:
    print(f"\n{character.get_status()}")
    print("\nCommands:")
    print("1. Move north")
    print("2. Move south")
    print("3. Move east")
    print("4. Move west")
    print("5. Attack")
    print("6. Rest")
    print("7. Exit")
    
    choice = input("Enter your choice (1-7): ")
    
    if choice == "1":
        print(character.move("north"))
    elif choice == "2":
        print(character.move("south"))
    elif choice == "3":
        print(character.move("east"))
    elif choice == "4":
        print(character.move("west"))
    elif choice == "5":
        print(character.attack())
    elif choice == "6":
        print(character.rest())
    elif choice == "7":
        print("Goodbye!")
        break
    else:
        print("Invalid choice! Please try again.")
```

---

## Common Mistakes (And How to Fix Them!) ❌➡️✅

### Mistake 1: Missing Break Statements
```python
# ❌ Wrong - This will execute all cases
choice = "1"
if choice == "1":
    print("Option 1")
    # Missing break - will continue to next case
if choice == "2":
    print("Option 2")

# ✅ Correct - Use elif for mutual exclusion
choice = "1"
if choice == "1":
    print("Option 1")
elif choice == "2":
    print("Option 2")
```

### Mistake 2: Not Handling Invalid Input
```python
# ❌ Wrong - No validation
choice = input("Enter choice: ")
if choice == "1":
    print("Option 1")
elif choice == "2":
    print("Option 2")
# What if user enters "3"?

# ✅ Correct - Handle all cases
choice = input("Enter choice: ")
if choice == "1":
    print("Option 1")
elif choice == "2":
    print("Option 2")
else:
    print("Invalid choice!")
```

### Mistake 3: Deeply Nested If Statements
```python
# ❌ Wrong - Too nested
if condition1:
    if condition2:
        if condition3:
            if condition4:
                print("Very nested!")
            else:
                print("Not condition4")
        else:
            print("Not condition3")
    else:
        print("Not condition2")
else:
    print("Not condition1")

# ✅ Correct - Use elif chains
if condition1 and condition2 and condition3 and condition4:
    print("All conditions met!")
elif condition1 and condition2 and condition3:
    print("First three conditions met!")
elif condition1 and condition2:
    print("First two conditions met!")
elif condition1:
    print("First condition met!")
else:
    print("No conditions met!")
```

---

## Fun Challenges! 🎯

### Challenge 1: Text Adventure Game
Create a text-based adventure game with multiple choices:

```python
print("🗺️ Text Adventure Game 🗺️")

class AdventureGame:
    def __init__(self):
        self.health = 100
        self.inventory = []
        self.location = "forest"
        self.game_over = False
    
    def show_status(self):
        print(f"\n🏥 Health: {self.health}")
        print(f"📍 Location: {self.location}")
        print(f"🎒 Inventory: {self.inventory}")
    
    def handle_choice(self, choice):
        if self.location == "forest":
            if choice == "1":
                print("🌲 You explore deeper into the forest...")
                self.location = "cave"
            elif choice == "2":
                print("🍄 You find some mushrooms!")
                self.inventory.append("mushrooms")
            elif choice == "3":
                print("💧 You drink from a stream and feel refreshed!")
                self.health = min(100, self.health + 20)
            else:
                print("Invalid choice!")
                
        elif self.location == "cave":
            if choice == "1":
                print("💎 You find a treasure chest!")
                self.inventory.append("treasure")
            elif choice == "2":
                print("🦇 A bat attacks you!")
                self.health -= 20
                if self.health <= 0:
                    print("💀 Game Over! You died!")
                    self.game_over = True
            elif choice == "3":
                print("🚪 You return to the forest.")
                self.location = "forest"
            else:
                print("Invalid choice!")
    
    def play(self):
        print("Welcome to the Adventure Game!")
        print("You find yourself in a mysterious forest...")
        
        while not self.game_over:
            self.show_status()
            
            if self.location == "forest":
                print("\nWhat do you do?")
                print("1. Go deeper into the forest")
                print("2. Search for food")
                print("3. Drink from stream")
                print("4. Quit")
                
            elif self.location == "cave":
                print("\nWhat do you do?")
                print("1. Search for treasure")
                print("2. Explore deeper")
                print("3. Return to forest")
                print("4. Quit")
            
            choice = input("Enter your choice (1-4): ")
            
            if choice == "4":
                print("Thanks for playing!")
                break
            
            self.handle_choice(choice)
            
            if self.health <= 0:
                self.game_over = True

# Start the game
game = AdventureGame()
game.play()
```

### Challenge 2: Quiz System
Create a comprehensive quiz system:

```python
print("📝 Quiz System 📝")

class QuizSystem:
    def __init__(self):
        self.questions = [
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
        self.score = 0
        self.current_question = 0
    
    def display_question(self):
        if self.current_question >= len(self.questions):
            return False
        
        q = self.questions[self.current_question]
        print(f"\nQuestion {self.current_question + 1}: {q['question']}")
        
        for i, option in enumerate(q['options']):
            print(f"{i + 1}. {option}")
        
        return True
    
    def check_answer(self, answer):
        if self.current_question >= len(self.questions):
            return False
        
        q = self.questions[self.current_question]
        if answer == q['correct'] + 1:
            print("✅ Correct!")
            self.score += 1
        else:
            print(f"❌ Wrong! The correct answer is: {q['options'][q['correct']]}")
        
        self.current_question += 1
        return True
    
    def show_results(self):
        percentage = (self.score / len(self.questions)) * 100
        print(f"\n📊 Quiz Results:")
        print(f"Score: {self.score}/{len(self.questions)}")
        print(f"Percentage: {percentage:.1f}%")
        
        if percentage >= 90:
            print("🏆 Excellent! You're a quiz master!")
        elif percentage >= 80:
            print("⭐ Great job! You did very well!")
        elif percentage >= 70:
            print("👍 Good work! You passed!")
        else:
            print("💪 Keep studying! You'll do better next time!")
    
    def run_quiz(self):
        print("Welcome to the Quiz System!")
        print("Answer the questions to test your knowledge.")
        
        while self.display_question():
            try:
                answer = int(input("Enter your answer (1-4): "))
                if 1 <= answer <= 4:
                    self.check_answer(answer)
                else:
                    print("Please enter a number between 1 and 4!")
            except ValueError:
                print("Please enter a valid number!")
        
        self.show_results()

# Start the quiz
quiz = QuizSystem()
quiz.run_quiz()
```

### Challenge 3: Menu-Driven Calculator
Create an advanced calculator with multiple functions:

```python
print("🧮 Advanced Calculator 🧮")

class AdvancedCalculator:
    def __init__(self):
        self.history = []
    
    def add_to_history(self, operation, result):
        self.history.append(f"{operation} = {result}")
    
    def basic_operations(self):
        print("\nBasic Operations:")
        print("1. Addition")
        print("2. Subtraction")
        print("3. Multiplication")
        print("4. Division")
        print("5. Power")
        print("6. Square root")
        
        choice = input("Enter your choice (1-6): ")
        
        if choice == "1":
            a = float(input("Enter first number: "))
            b = float(input("Enter second number: "))
            result = a + b
            print(f"Result: {a} + {b} = {result}")
            self.add_to_history(f"{a} + {b}", result)
            
        elif choice == "2":
            a = float(input("Enter first number: "))
            b = float(input("Enter second number: "))
            result = a - b
            print(f"Result: {a} - {b} = {result}")
            self.add_to_history(f"{a} - {b}", result)
            
        elif choice == "3":
            a = float(input("Enter first number: "))
            b = float(input("Enter second number: "))
            result = a * b
            print(f"Result: {a} × {b} = {result}")
            self.add_to_history(f"{a} × {b}", result)
            
        elif choice == "4":
            a = float(input("Enter first number: "))
            b = float(input("Enter second number: "))
            if b != 0:
                result = a / b
                print(f"Result: {a} ÷ {b} = {result}")
                self.add_to_history(f"{a} ÷ {b}", result)
            else:
                print("Error: Cannot divide by zero!")
                
        elif choice == "5":
            a = float(input("Enter base: "))
            b = float(input("Enter exponent: "))
            result = a ** b
            print(f"Result: {a}^{b} = {result}")
            self.add_to_history(f"{a}^{b}", result)
            
        elif choice == "6":
            a = float(input("Enter number: "))
            if a >= 0:
                result = a ** 0.5
                print(f"Result: √{a} = {result}")
                self.add_to_history(f"√{a}", result)
            else:
                print("Error: Cannot take square root of negative number!")
        else:
            print("Invalid choice!")
    
    def advanced_operations(self):
        print("\nAdvanced Operations:")
        print("1. Factorial")
        print("2. Percentage")
        print("3. Trigonometric functions")
        print("4. Logarithm")
        
        choice = input("Enter your choice (1-4): ")
        
        if choice == "1":
            n = int(input("Enter number: "))
            if n >= 0:
                result = 1
                for i in range(1, n + 1):
                    result *= i
                print(f"Result: {n}! = {result}")
                self.add_to_history(f"{n}!", result)
            else:
                print("Error: Factorial is not defined for negative numbers!")
                
        elif choice == "2":
            value = float(input("Enter value: "))
            percentage = float(input("Enter percentage: "))
            result = (value * percentage) / 100
            print(f"Result: {percentage}% of {value} = {result}")
            self.add_to_history(f"{percentage}% of {value}", result)
            
        elif choice == "3":
            print("Trigonometric functions:")
            print("1. Sine")
            print("2. Cosine")
            print("3. Tangent")
            
            trig_choice = input("Enter your choice (1-3): ")
            angle = float(input("Enter angle in degrees: "))
            
            import math
            if trig_choice == "1":
                result = math.sin(math.radians(angle))
                print(f"Result: sin({angle}°) = {result}")
                self.add_to_history(f"sin({angle}°)", result)
            elif trig_choice == "2":
                result = math.cos(math.radians(angle))
                print(f"Result: cos({angle}°) = {result}")
                self.add_to_history(f"cos({angle}°)", result)
            elif trig_choice == "3":
                result = math.tan(math.radians(angle))
                print(f"Result: tan({angle}°) = {result}")
                self.add_to_history(f"tan({angle}°)", result)
            else:
                print("Invalid choice!")
                
        elif choice == "4":
            import math
            a = float(input("Enter number: "))
            base = float(input("Enter base: "))
            if a > 0 and base > 0 and base != 1:
                result = math.log(a, base)
                print(f"Result: log_{base}({a}) = {result}")
                self.add_to_history(f"log_{base}({a})", result)
            else:
                print("Error: Invalid input for logarithm!")
        else:
            print("Invalid choice!")
    
    def show_history(self):
        if not self.history:
            print("No calculations in history.")
        else:
            print("\nCalculation History:")
            for i, calc in enumerate(self.history, 1):
                print(f"{i}. {calc}")
    
    def run(self):
        while True:
            print("\n🧮 Advanced Calculator:")
            print("1. Basic Operations")
            print("2. Advanced Operations")
            print("3. Show History")
            print("4. Clear History")
            print("5. Exit")
            
            choice = input("Enter your choice (1-5): ")
            
            if choice == "1":
                self.basic_operations()
            elif choice == "2":
                self.advanced_operations()
            elif choice == "3":
                self.show_history()
            elif choice == "4":
                self.history = []
                print("History cleared!")
            elif choice == "5":
                print("Goodbye!")
                break
            else:
                print("Invalid choice! Please try again.")

# Start the calculator
calc = AdvancedCalculator()
calc.run()
```

---

## What's Next? 🚀

You've learned how to use switch-like patterns to organize multiple choices! Now you can:
- Create menu-driven programs
- Handle complex decision-making logic
- Organize your code better

**In the next lesson, you'll learn:**
- How to debug your programs and find errors
- How to use debugging tools and techniques
- How to make your programs more reliable!

---

## Practice Time! 💪

**Try these exercises:**

1. **Create a program that simulates a vending machine**
2. **Make a program that manages a student database**
3. **Build a program that simulates a bank ATM**
4. **Design a program that creates a simple game menu**

**Remember:** Switch-like patterns help organize complex decision-making and make your programs more user-friendly!

---

## Fun Facts! 🎉

- **Switch statements are used** in almost every interactive program!
- **You can nest switch statements** for complex decision trees!
- **Switch statements make programs** more organized and easier to read!
- **Many programming languages** have built-in switch statements!

---

## Discussion Questions 💭

1. **What was the most complex menu system you created?**
2. **How do you think switch-like patterns help organize code?**
3. **What kind of real-world problems could you solve with switch patterns?**

---

## Next Up: Debugging! 🐛

In the next lesson, you'll learn how to debug your programs and find errors!

**Keep organizing and improving!** 🎉

