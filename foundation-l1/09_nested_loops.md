# Nested Loops 🏗️
## Creating Complex Patterns and Solving Advanced Problems

### Learning Objectives
By the end of this lesson, students will:
- Use nested loops to create complex patterns
- Understand how nested loops work with different data structures
- Create advanced visual patterns and data processing
- Use nested loops to solve real-world problems

---

## What are Nested Loops? 🤔

**Nested loops are loops inside other loops - like Russian nesting dolls!**

Think of nested loops as:
- **Pattern makers** that create complex designs
- **Data processors** that work with multiple dimensions
- **Grid builders** that create tables and matrices

### Real-World Analogy: Classroom Seating
- **For each** row in the classroom → **For each** seat in the row → Assign a student
- **For each** day of the week → **For each** hour of the day → Schedule a class
- **For each** student → **For each** subject → Calculate their grade

---

## Basic Nested Loop Structure 📝

### Simple Nested For Loops
```python
for i in range(3):  # Outer loop
    for j in range(3):  # Inner loop
        print(f"({i}, {j})", end=" ")
    print()  # New line after each row
```

### Nested While Loops
```python
i = 0
while i < 3:  # Outer loop
    j = 0
    while j < 3:  # Inner loop
        print(f"({i}, {j})", end=" ")
        j = j + 1
    print()  # New line after each row
    i = i + 1
```

---

## Pattern Creation Examples 🎨

### Example 1: Number Patterns
```python
print("🔢 Number Pattern Generator 🔢")

size = int(input("Enter pattern size: "))

print("\n1. Right Triangle:")
for i in range(size):
    for j in range(i + 1):
        print(j + 1, end=" ")
    print()

print("\n2. Inverted Triangle:")
for i in range(size, 0, -1):
    for j in range(i):
        print(j + 1, end=" ")
    print()

print("\n3. Number Square:")
for i in range(size):
    for j in range(size):
        print((i * size) + j + 1, end=" ")
    print()
```

### Example 2: Star Patterns
```python
print("⭐ Star Pattern Generator ⭐")

size = int(input("Enter pattern size: "))

print("\n1. Right Triangle:")
for i in range(size):
    for j in range(i + 1):
        print("*", end=" ")
    print()

print("\n2. Inverted Triangle:")
for i in range(size, 0, -1):
    for j in range(i):
        print("*", end=" ")
    print()

print("\n3. Diamond:")
# Top half
for i in range(size):
    for j in range(size - i - 1):
        print(" ", end=" ")
    for j in range(2 * i + 1):
        print("*", end=" ")
    print()
# Bottom half
for i in range(size - 2, -1, -1):
    for j in range(size - i - 1):
        print(" ", end=" ")
    for j in range(2 * i + 1):
        print("*", end=" ")
    print()
```

### Example 3: Alphabet Patterns
```python
print("🔤 Alphabet Pattern Generator 🔤")

size = int(input("Enter pattern size: "))

print("\n1. Alphabet Triangle:")
for i in range(size):
    for j in range(i + 1):
        print(chr(65 + j), end=" ")
    print()

print("\n2. Alphabet Square:")
for i in range(size):
    for j in range(size):
        print(chr(65 + (i + j) % 26), end=" ")
    print()

print("\n3. Alphabet Diamond:")
# Top half
for i in range(size):
    for j in range(size - i - 1):
        print(" ", end=" ")
    for j in range(2 * i + 1):
        print(chr(65 + j % 26), end=" ")
    print()
# Bottom half
for i in range(size - 2, -1, -1):
    for j in range(size - i - 1):
        print(" ", end=" ")
    for j in range(2 * i + 1):
        print(chr(65 + j % 26), end=" ")
    print()
```

---

## Real-World Examples 🌟

### Example 1: Multiplication Table Generator
```python
print("📊 Advanced Multiplication Table Generator 📊")

size = int(input("Enter table size: "))

print("\nMultiplication Table:")
print("   ", end="")
for j in range(1, size + 1):
    print(f"{j:4}", end="")
print()

for i in range(1, size + 1):
    print(f"{i:2}:", end="")
    for j in range(1, size + 1):
        result = i * j
        print(f"{result:4}", end="")
    print()
```

### Example 2: Grade Book System
```python
print("📚 Grade Book System 📚")

students = ["Alice", "Bob", "Charlie", "Diana"]
subjects = ["Math", "Science", "English", "History"]
grades = []

# Initialize grades with random values
import random
for i in range(len(students)):
    student_grades = []
    for j in range(len(subjects)):
        student_grades.append(random.randint(60, 100))
    grades.append(student_grades)

# Display grade book
print("\nGrade Book:")
print("Student".ljust(10), end="")
for subject in subjects:
    print(f"{subject:8}", end="")
print("Average")

for i in range(len(students)):
    print(students[i].ljust(10), end="")
    total = 0
    for j in range(len(subjects)):
        print(f"{grades[i][j]:8}", end="")
        total += grades[i][j]
    average = total / len(subjects)
    print(f"{average:6.1f}")

# Calculate subject averages
print("\nSubject Averages:")
for j in range(len(subjects)):
    total = 0
    for i in range(len(students)):
        total += grades[i][j]
    average = total / len(students)
    print(f"{subjects[j]}: {average:.1f}")
```

### Example 3: Calendar Generator
```python
print("📅 Calendar Generator 📅")

month = input("Enter month name: ")
year = int(input("Enter year: "))
days_in_month = int(input("Enter days in month: "))
start_day = int(input("Enter starting day (0=Sunday, 1=Monday, etc.): "))

print(f"\n{month} {year}")
print("Su Mo Tu We Th Fr Sa")

# Print empty spaces for days before the first day
for i in range(start_day):
    print("   ", end="")

# Print the days
day = 1
while day <= days_in_month:
    for j in range(start_day, 7):
        if day <= days_in_month:
            print(f"{day:2} ", end="")
            day += 1
        else:
            break
    print()  # New line after each week
    start_day = 0  # Reset for subsequent weeks
```

---

## Interactive Examples 🎮

### Example 1: Tic-Tac-Toe Game
```python
print("🎮 Tic-Tac-Toe Game 🎮")

# Initialize the board
board = [[" " for _ in range(3)] for _ in range(3)]
current_player = "X"

def print_board():
    print("\nCurrent Board:")
    for i in range(3):
        for j in range(3):
            print(f" {board[i][j]} ", end="")
            if j < 2:
                print("|", end="")
        print()
        if i < 2:
            print("-----------")

def check_winner():
    # Check rows
    for i in range(3):
        if board[i][0] == board[i][1] == board[i][2] != " ":
            return board[i][0]
    
    # Check columns
    for j in range(3):
        if board[0][j] == board[1][j] == board[2][j] != " ":
            return board[0][j]
    
    # Check diagonals
    if board[0][0] == board[1][1] == board[2][2] != " ":
        return board[0][0]
    if board[0][2] == board[1][1] == board[2][0] != " ":
        return board[0][2]
    
    return None

def is_board_full():
    for i in range(3):
        for j in range(3):
            if board[i][j] == " ":
                return False
    return True

print("Welcome to Tic-Tac-Toe!")
print("Players take turns. Enter row and column (0-2).")

while True:
    print_board()
    
    if current_player == "X":
        print("Player X's turn")
    else:
        print("Player O's turn")
    
    row = int(input("Enter row (0-2): "))
    col = int(input("Enter column (0-2): "))
    
    if board[row][col] == " ":
        board[row][col] = current_player
        
        winner = check_winner()
        if winner:
            print_board()
            print(f"🎉 Player {winner} wins!")
            break
        
        if is_board_full():
            print_board()
            print("🤝 It's a tie!")
            break
        
        current_player = "O" if current_player == "X" else "X"
    else:
        print("That spot is already taken! Try again.")
```

### Example 2: Matrix Calculator
```python
print("🧮 Matrix Calculator 🧮")

def create_matrix(rows, cols, name):
    print(f"\nEnter values for {name}:")
    matrix = []
    for i in range(rows):
        row = []
        for j in range(cols):
            value = float(input(f"Enter {name}[{i}][{j}]: "))
            row.append(value)
        matrix.append(row)
    return matrix

def print_matrix(matrix, name):
    print(f"\n{name}:")
    for i in range(len(matrix)):
        for j in range(len(matrix[i])):
            print(f"{matrix[i][j]:8.2f}", end="")
        print()

def add_matrices(matrix1, matrix2):
    result = []
    for i in range(len(matrix1)):
        row = []
        for j in range(len(matrix1[i])):
            row.append(matrix1[i][j] + matrix2[i][j])
        result.append(row)
    return result

def multiply_matrices(matrix1, matrix2):
    result = []
    for i in range(len(matrix1)):
        row = []
        for j in range(len(matrix2[0])):
            sum_val = 0
            for k in range(len(matrix2)):
                sum_val += matrix1[i][k] * matrix2[k][j]
            row.append(sum_val)
        result.append(row)
    return result

# Get matrix dimensions
rows1 = int(input("Enter number of rows for first matrix: "))
cols1 = int(input("Enter number of columns for first matrix: "))

# Create first matrix
matrix1 = create_matrix(rows1, cols1, "Matrix 1")
print_matrix(matrix1, "Matrix 1")

# Create second matrix
matrix2 = create_matrix(rows1, cols1, "Matrix 2")
print_matrix(matrix2, "Matrix 2")

# Add matrices
if rows1 == cols1:
    sum_matrix = add_matrices(matrix1, matrix2)
    print_matrix(sum_matrix, "Sum of Matrices")
else:
    print("Cannot add matrices of different dimensions!")

# Multiply matrices (if possible)
if cols1 == rows1:
    product_matrix = multiply_matrices(matrix1, matrix2)
    print_matrix(product_matrix, "Product of Matrices")
else:
    print("Cannot multiply these matrices!")
```

### Example 3: Data Analysis Dashboard
```python
print("📊 Data Analysis Dashboard 📊")

# Sample data: sales by month and product
months = ["Jan", "Feb", "Mar", "Apr", "May", "Jun"]
products = ["Laptop", "Phone", "Tablet", "Headphones"]
sales_data = [
    [120, 200, 80, 150],   # January
    [110, 180, 90, 140],   # February
    [130, 220, 85, 160],   # March
    [125, 190, 95, 155],   # April
    [140, 210, 100, 170],  # May
    [135, 200, 88, 165]    # June
]

# Display sales table
print("\nSales Data by Month and Product:")
print("Month".ljust(8), end="")
for product in products:
    print(f"{product:12}", end="")
print("Total")

total_sales = 0
for i in range(len(months)):
    print(months[i].ljust(8), end="")
    month_total = 0
    for j in range(len(products)):
        print(f"{sales_data[i][j]:12}", end="")
        month_total += sales_data[i][j]
    print(f"{month_total:8}")
    total_sales += month_total

# Calculate product totals
print("\nProduct Totals:")
for j in range(len(products)):
    product_total = 0
    for i in range(len(months)):
        product_total += sales_data[i][j]
    print(f"{products[j]}: {product_total} units")

# Find best and worst months
month_totals = []
for i in range(len(months)):
    month_total = sum(sales_data[i])
    month_totals.append(month_total)

best_month_idx = month_totals.index(max(month_totals))
worst_month_idx = month_totals.index(min(month_totals))

print(f"\nBest month: {months[best_month_idx]} ({month_totals[best_month_idx]} units)")
print(f"Worst month: {months[worst_month_idx]} ({month_totals[worst_month_idx]} units)")

# Find best and worst products
product_totals = []
for j in range(len(products)):
    product_total = sum(sales_data[i][j] for i in range(len(months)))
    product_totals.append(product_total)

best_product_idx = product_totals.index(max(product_totals))
worst_product_idx = product_totals.index(min(product_totals))

print(f"Best product: {products[best_product_idx]} ({product_totals[best_product_idx]} units)")
print(f"Worst product: {products[worst_product_idx]} ({product_totals[worst_product_idx]} units)")
```

---

## Advanced Pattern Examples 🎨

### Example 1: Pascal's Triangle
```python
print("🔺 Pascal's Triangle Generator 🔺")

rows = int(input("Enter number of rows: "))

print("\nPascal's Triangle:")
for i in range(rows):
    # Print spaces for alignment
    for j in range(rows - i - 1):
        print(" ", end="")
    
    # Calculate and print values
    for j in range(i + 1):
        # Calculate binomial coefficient
        value = 1
        for k in range(j):
            value = value * (i - k) // (k + 1)
        print(f"{value:3}", end=" ")
    print()
```

### Example 2: Spiral Pattern
```python
print("🌀 Spiral Pattern Generator 🌀")

size = int(input("Enter spiral size: "))

# Create a 2D array
spiral = [[0 for _ in range(size)] for _ in range(size)]

# Fill the spiral
num = 1
top, bottom = 0, size - 1
left, right = 0, size - 1

while top <= bottom and left <= right:
    # Fill top row
    for j in range(left, right + 1):
        spiral[top][j] = num
        num += 1
    top += 1
    
    # Fill right column
    for i in range(top, bottom + 1):
        spiral[i][right] = num
        num += 1
    right -= 1
    
    # Fill bottom row
    if top <= bottom:
        for j in range(right, left - 1, -1):
            spiral[bottom][j] = num
            num += 1
        bottom -= 1
    
    # Fill left column
    if left <= right:
        for i in range(bottom, top - 1, -1):
            spiral[i][left] = num
            num += 1
        left += 1

# Print the spiral
print("\nSpiral Pattern:")
for i in range(size):
    for j in range(size):
        print(f"{spiral[i][j]:3}", end=" ")
    print()
```

### Example 3: Magic Square
```python
print("✨ Magic Square Generator ✨")

size = int(input("Enter magic square size (odd number): "))

if size % 2 == 0:
    print("Please enter an odd number!")
else:
    # Initialize magic square
    magic_square = [[0 for _ in range(size)] for _ in range(size)]
    
    # Position of 1
    i, j = 0, size // 2
    
    # Fill the magic square
    for num in range(1, size * size + 1):
        magic_square[i][j] = num
        
        # Calculate next position
        new_i, new_j = i - 1, j + 1
        
        # Handle wrapping
        if new_i < 0:
            new_i = size - 1
        if new_j >= size:
            new_j = 0
        
        # If the new position is occupied, move down
        if magic_square[new_i][new_j] != 0:
            new_i, new_j = i + 1, j
            if new_i >= size:
                new_i = 0
        
        i, j = new_i, new_j
    
    # Print the magic square
    print(f"\nMagic Square of size {size}:")
    for i in range(size):
        for j in range(size):
            print(f"{magic_square[i][j]:3}", end=" ")
        print()
    
    # Verify magic properties
    magic_constant = size * (size * size + 1) // 2
    print(f"\nMagic constant: {magic_constant}")
    
    # Check row sums
    print("Row sums:")
    for i in range(size):
        row_sum = sum(magic_square[i])
        print(f"Row {i + 1}: {row_sum}")
    
    # Check column sums
    print("Column sums:")
    for j in range(size):
        col_sum = sum(magic_square[i][j] for i in range(size))
        print(f"Column {j + 1}: {col_sum}")
```

---

## Common Mistakes (And How to Fix Them!) ❌➡️✅

### Mistake 1: Wrong Loop Variable Usage
```python
# ❌ Wrong - Using same variable in nested loops
for i in range(3):
    for i in range(3):  # This overwrites the outer loop variable!
        print(f"({i}, {i})")

# ✅ Correct - Use different variables
for i in range(3):
    for j in range(3):
        print(f"({i}, {j})")
```

### Mistake 2: Incorrect Indentation
```python
# ❌ Wrong - Inner loop not properly indented
for i in range(3):
for j in range(3):  # This should be indented!
    print(f"({i}, {j})")

# ✅ Correct - Proper indentation
for i in range(3):
    for j in range(3):
        print(f"({i}, {j})")
```

### Mistake 3: Infinite Nested Loops
```python
# ❌ Wrong - This will run forever!
i = 0
while i < 3:
    j = 0
    while j < 3:
        print(f"({i}, {j})")
        # Forgot to increment j!

# ✅ Correct - Increment both variables
i = 0
while i < 3:
    j = 0
    while j < 3:
        print(f"({i}, {j})")
        j += 1
    i += 1
```

---

## Fun Challenges! 🎯

### Challenge 1: ASCII Art Generator
Create a program that generates ASCII art:

```python
print("🎨 ASCII Art Generator 🎨")

print("Choose a pattern:")
print("1. Tree")
print("2. Butterfly")
print("3. Heart")
print("4. Star")

choice = int(input("Enter your choice (1-4): "))
size = int(input("Enter size: "))

if choice == 1:
    print("\n🎄 Tree:")
    # Tree body
    for i in range(size):
        for j in range(size - i - 1):
            print(" ", end="")
        for j in range(2 * i + 1):
            print("*", end="")
        print()
    # Tree trunk
    for i in range(2):
        for j in range(size - 1):
            print(" ", end="")
        print("|||")
        
elif choice == 2:
    print("\n🦋 Butterfly:")
    # Top half
    for i in range(size):
        for j in range(i + 1):
            print("*", end="")
        for j in range(2 * (size - i - 1)):
            print(" ", end="")
        for j in range(i + 1):
            print("*", end="")
        print()
    # Bottom half
    for i in range(size - 1, -1, -1):
        for j in range(i + 1):
            print("*", end="")
        for j in range(2 * (size - i - 1)):
            print(" ", end="")
        for j in range(i + 1):
            print("*", end="")
        print()
        
elif choice == 3:
    print("\n❤️ Heart:")
    for i in range(size):
        for j in range(size - i - 1):
            print(" ", end="")
        for j in range(2 * i + 1):
            print("*", end="")
        for j in range(2 * (size - i - 1)):
            print(" ", end="")
        for j in range(2 * i + 1):
            print("*", end="")
        print()
    # Bottom part
    for i in range(2 * size):
        for j in range(i):
            print(" ", end="")
        for j in range(4 * size - 2 * i - 1):
            print("*", end="")
        print()
        
elif choice == 4:
    print("\n⭐ Star:")
    # Top part
    for i in range(size):
        for j in range(size - i - 1):
            print(" ", end="")
        for j in range(2 * i + 1):
            print("*", end="")
        print()
    # Bottom part
    for i in range(size - 2, -1, -1):
        for j in range(size - i - 1):
            print(" ", end="")
        for j in range(2 * i + 1):
            print("*", end="")
        print()
```

### Challenge 2: Sudoku Solver
Create a simple Sudoku solver:

```python
print("🧩 Sudoku Solver 🧩")

def print_sudoku(grid):
    for i in range(9):
        if i % 3 == 0 and i != 0:
            print("-" * 21)
        for j in range(9):
            if j % 3 == 0 and j != 0:
                print("|", end=" ")
            print(grid[i][j], end=" ")
        print()

def is_valid(grid, row, col, num):
    # Check row
    for j in range(9):
        if grid[row][j] == num:
            return False
    
    # Check column
    for i in range(9):
        if grid[i][col] == num:
            return False
    
    # Check 3x3 box
    start_row = (row // 3) * 3
    start_col = (col // 3) * 3
    for i in range(3):
        for j in range(3):
            if grid[start_row + i][start_col + j] == num:
                return False
    
    return True

def solve_sudoku(grid):
    for i in range(9):
        for j in range(9):
            if grid[i][j] == 0:
                for num in range(1, 10):
                    if is_valid(grid, i, j, num):
                        grid[i][j] = num
                        if solve_sudoku(grid):
                            return True
                        grid[i][j] = 0
                return False
    return True

# Sample Sudoku puzzle (0 represents empty cells)
sudoku_grid = [
    [5, 3, 0, 0, 7, 0, 0, 0, 0],
    [6, 0, 0, 1, 9, 5, 0, 0, 0],
    [0, 9, 8, 0, 0, 0, 0, 6, 0],
    [8, 0, 0, 0, 6, 0, 0, 0, 3],
    [4, 0, 0, 8, 0, 3, 0, 0, 1],
    [7, 0, 0, 0, 2, 0, 0, 0, 6],
    [0, 6, 0, 0, 0, 0, 2, 8, 0],
    [0, 0, 0, 4, 1, 9, 0, 0, 5],
    [0, 0, 0, 0, 8, 0, 0, 7, 9]
]

print("Original Sudoku:")
print_sudoku(sudoku_grid)

if solve_sudoku(sudoku_grid):
    print("\nSolved Sudoku:")
    print_sudoku(sudoku_grid)
else:
    print("No solution exists!")
```

### Challenge 3: Game of Life
Create a simple version of Conway's Game of Life:

```python
print("🎮 Conway's Game of Life 🎮")

import random
import time

def create_grid(size):
    return [[random.choice([0, 1]) for _ in range(size)] for _ in range(size)]

def print_grid(grid):
    for row in grid:
        for cell in row:
            print("■" if cell else "□", end=" ")
        print()

def count_neighbors(grid, row, col):
    count = 0
    for i in range(-1, 2):
        for j in range(-1, 2):
            if i == 0 and j == 0:
                continue
            new_row, new_col = row + i, col + j
            if (0 <= new_row < len(grid) and 
                0 <= new_col < len(grid[0]) and 
                grid[new_row][new_col]):
                count += 1
    return count

def next_generation(grid):
    new_grid = [[0 for _ in range(len(grid[0]))] for _ in range(len(grid))]
    
    for i in range(len(grid)):
        for j in range(len(grid[0])):
            neighbors = count_neighbors(grid, i, j)
            
            if grid[i][j] == 1:  # Living cell
                if neighbors in [2, 3]:
                    new_grid[i][j] = 1
            else:  # Dead cell
                if neighbors == 3:
                    new_grid[i][j] = 1
    
    return new_grid

# Initialize the game
size = int(input("Enter grid size: "))
generations = int(input("Enter number of generations: "))

grid = create_grid(size)

print("Initial generation:")
print_grid(grid)

for gen in range(generations):
    time.sleep(1)  # Pause for visualization
    print(f"\nGeneration {gen + 1}:")
    grid = next_generation(grid)
    print_grid(grid)
```

---

## What's Next? 🚀

You've learned how to use nested loops to create complex patterns! Now you can:
- Create advanced visual patterns and designs
- Process multi-dimensional data efficiently
- Solve complex problems with nested iterations

**In the next lesson, you'll learn:**
- How to use switch statements for multiple choices
- How to make your programs more organized
- How to handle complex decision-making!

---

## Practice Time! 💪

**Try these exercises:**

1. **Create a program that generates a chess board pattern**
2. **Make a program that creates a multiplication table with formatting**
3. **Build a program that generates a spiral number pattern**
4. **Design a program that creates a calendar for any month**

**Remember:** Nested loops are powerful tools for creating complex patterns and processing multi-dimensional data!

---

## Fun Facts! 🎉

- **Nested loops are used** in graphics programming and game development!
- **You can nest loops** as deep as you need (though 3+ levels get complex)!
- **Nested loops are essential** for working with 2D arrays and matrices!
- **Many algorithms use nested loops** to solve complex problems!

---

## Discussion Questions 💭

1. **What was the most complex pattern you created with nested loops?**
2. **How do you think nested loops help solve real-world problems?**
3. **What kind of visual patterns would you like to create?**

---

## Next Up: Switch Statements! 🔀

In the next lesson, you'll learn how to use switch statements for multiple choices and better organization!

**Keep creating amazing patterns!** 🎉


