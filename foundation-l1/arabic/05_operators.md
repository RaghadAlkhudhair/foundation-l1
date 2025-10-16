# العوامل ➕➖✖️➗
## القيام بالرياضيات مع متغيراتك

### الأهداف التعليمية
بنهاية هذا الدرس، سيكون الطلاب قادرين على:
- استخدام العوامل الحسابية (+, -, *, /) مع المتغيرات
- فهم أولوية العوامل وترتيب العمليات
- إجراء الحسابات في برامجهم
- استخدام عوامل المقارنة (==, !=, <, >, <=, >=)
- تطبيق العوامل المنطقية (and, or, not)

---

## ما هي العوامل؟ 🤔

**العوامل هي رموز خاصة تخبر بايثون ماذا تفعل ببياناتك!**

فكر في العوامل كـ:
- **أدوات رياضية** للحسابات
- **أدوات مقارنة** للقرارات
- **أدوات منطقية** للتفكير المعقد

### تشبيه من العالم الحقيقي: أزرار الحاسبة
- **زر +** = عامل الجمع
- **زر -** = عامل الطرح
- **زر ×** = عامل الضرب
- **زر ÷** = عامل القسمة

---

## العوامل الحسابية 🧮

### 1. الجمع (+)
```python
# جمع أساسي
a = 5
b = 3
result = a + b
print("5 + 3 = " + str(result))  # الناتج: 5 + 3 = 8

# جمع المتغيرات
score = 100
bonus = 50
total_score = score + bonus
print("Total score: " + str(total_score))  # الناتج: Total score: 150
```

### 2. الطرح (-)
```python
# طرح أساسي
money = 100
spent = 25
remaining = money - spent
print("Money left: $" + str(remaining))  # الناتج: Money left: $75

# تغيير درجة الحرارة
current_temp = 85
temp_drop = 10
new_temp = current_temp - temp_drop
print("New temperature: " + str(new_temp) + "°F")  # الناتج: New temperature: 75°F
```

### 3. الضرب (*)
```python
# ضرب أساسي
length = 5
width = 3
area = length * width
print("Area: " + str(area) + " square units")  # الناتج: Area: 15 square units

# حساب التكلفة الإجمالية
price_per_item = 2.50
quantity = 4
total_cost = price_per_item * quantity
print("Total cost: $" + str(total_cost))  # الناتج: Total cost: $10.0
```

### 4. القسمة (/)
```python
# قسمة أساسية
total_points = 100
number_of_tests = 4
average = total_points / number_of_tests
print("Average: " + str(average))  # الناتج: Average: 25.0

# حساب السرعة
distance = 120
time = 2
speed = distance / time
print("Speed: " + str(speed) + " mph")  # الناتج: Speed: 60.0 mph
```

---

## أمثلة من العالم الحقيقي 🌟

### المثال الأول: حاسبة التسوق
```python
print("🛒 Shopping Calculator 🛒")

# الحصول على معلومات العنصر
item_name = input("What are you buying? ")
price = float(input("How much does it cost? $"))
quantity = int(input("How many do you want? "))
tax_rate = 0.08  # ضريبة 8%

# حساب التكاليف
subtotal = price * quantity
tax_amount = subtotal * tax_rate
total = subtotal + tax_amount

# عرض النتائج
print("\n📄 Receipt:")
print("Item: " + item_name)
print("Price each: $" + str(price))
print("Quantity: " + str(quantity))
print("Subtotal: $" + str(subtotal))
print("Tax (8%): $" + str(tax_amount))
print("Total: $" + str(total))
```

### المثال الثاني: حاسبة الدرجات
```python
print("📊 Grade Calculator 📊")

# الحصول على درجات الاختبارات
test1 = float(input("Test 1 score: "))
test2 = float(input("Test 2 score: "))
test3 = float(input("Test 3 score: "))
homework = float(input("Homework average: "))

# حساب المتوسط المرجح
test_average = (test1 + test2 + test3) / 3
final_grade = (test_average * 0.7) + (homework * 0.3)

# عرض النتائج
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

### المثال الثالث: مخطط حفلة البيتزا
```python
print("🍕 Pizza Party Planner 🍕")

# الحصول على معلومات الحفلة
num_people = int(input("How many people are coming? "))
slices_per_person = 3
slices_per_pizza = 8
cost_per_pizza = 12.99

# حساب احتياجات البيتزا
total_slices_needed = num_people * slices_per_person
pizzas_needed = total_slices_needed / slices_per_pizza
pizzas_to_order = int(pizzas_needed) + 1  # تقريب لأعلى
total_cost = pizzas_to_order * cost_per_pizza

# عرض الخطة
print("\n🎉 Party Plan:")
print("People: " + str(num_people))
print("Slices needed: " + str(total_slices_needed))
print("Pizzas to order: " + str(pizzas_to_order))
print("Total cost: $" + str(total_cost))
print("Have a great party!")
```

---

## عوامل المقارنة 🔍

### ما هي عوامل المقارنة؟
**تقارن قيمتين وتعيد True أو False!**

### 1. يساوي (==)
```python
age = 16
can_drive = (age == 16)
print("Can drive: " + str(can_drive))  # الناتج: Can drive: True

# التحقق من تطابق كلمات المرور
password1 = "mypassword123"
password2 = "mypassword123"
passwords_match = (password1 == password2)
print("Passwords match: " + str(passwords_match))  # الناتج: Passwords match: True
```

### 2. لا يساوي (!=)
```python
favorite_color = "blue"
user_guess = "red"
correct_guess = (user_guess != favorite_color)
print("Wrong guess: " + str(correct_guess))  # الناتج: Wrong guess: True
```

### 3. أكبر من (>)
```python
score = 85
passing_grade = 70
passed = (score > passing_grade)
print("Passed: " + str(passed))  # الناتج: Passed: True
```

### 4. أقل من (<)
```python
temperature = 32
freezing_point = 32
is_cold = (temperature < freezing_point)
print("Is cold: " + str(is_cold))  # الناتج: Is cold: False
```

### 5. أكبر من أو يساوي (>=)
```python
age = 18
voting_age = 18
can_vote = (age >= voting_age)
print("Can vote: " + str(can_vote))  # الناتج: Can vote: True
```

### 6. أقل من أو يساوي (<=)
```python
items_in_cart = 5
max_items = 10
cart_ok = (items_in_cart <= max_items)
print("Cart is OK: " + str(cart_ok))  # الناتج: Cart is OK: True
```

---

## العوامل المنطقية 🧠

### 1. AND (and)
```python
# يجب أن تكون كلا الحالتين صحيحتين
age = 16
has_license = True
can_drive = (age >= 16) and has_license
print("Can drive: " + str(can_drive))  # الناتج: Can drive: True

# مثال الطقس
temperature = 75
is_sunny = True
perfect_weather = (temperature > 70) and is_sunny
print("Perfect weather: " + str(perfect_weather))  # الناتج: Perfect weather: True
```

### 2. OR (or)
```python
# يجب أن تكون إحدى الحالتين على الأقل صحيحة
is_weekend = False
is_holiday = True
day_off = is_weekend or is_holiday
print("Day off: " + str(day_off))  # الناتج: Day off: True

# مثال الدرجات
test_score = 85
homework_score = 95
good_grade = (test_score >= 80) or (homework_score >= 90)
print("Good grade: " + str(good_grade))  # الناتج: Good grade: True
```

### 3. NOT (not)
```python
# يعكس النتيجة
is_raining = False
is_sunny = not is_raining
print("Is sunny: " + str(is_sunny))  # الناتج: Is sunny: True

# فحص العمر
age = 15
is_adult = not (age < 18)
print("Is adult: " + str(is_adult))  # الناتج: Is adult: False
```

---

## أمثلة تفاعلية ممتعة 🎮

### المثال الأول: لعبة اختبار الرياضيات
```python
print("🧮 Math Quiz Game 🧮")

# توليد أرقام عشوائية
import random
num1 = random.randint(1, 10)
num2 = random.randint(1, 10)
operation = random.choice(['+', '-', '*'])

# حساب الإجابة الصحيحة
if operation == '+':
    correct_answer = num1 + num2
elif operation == '-':
    correct_answer = num1 - num2
else:
    correct_answer = num1 * num2

# طرح السؤال
print("What is " + str(num1) + " " + operation + " " + str(num2) + "?")
user_answer = int(input("Your answer: "))

# فحص الإجابة
if user_answer == correct_answer:
    print("🎉 Correct! Great job!")
else:
    print("❌ Wrong! The answer was " + str(correct_answer))
```

### المثال الثاني: توصيات مبنية على العمر
```python
print("🎯 Age-Based Recommendations 🎯")

age = int(input("How old are you? "))

# توصيات مبنية على العمر
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

# فحوصات إضافية
can_vote = age >= 18
can_drive = age >= 16
can_work = age >= 14

print("\nYour privileges:")
print("Can vote: " + str(can_vote))
print("Can drive: " + str(can_drive))
print("Can work: " + str(can_work))
```

### المثال الثالث: صانع قرارات الطقس
```python
print("🌤️ Weather Decision Maker 🌤️")

temperature = int(input("What's the temperature? "))
is_raining = input("Is it raining? (yes/no): ").lower() == "yes"
is_windy = input("Is it windy? (yes/no): ").lower() == "yes"

# تقديم التوصيات
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

## أولوية العوامل 📊

### ترتيب العمليات (PEMDAS)
1. **P**arentheses (الأقواس)
2. **E**xponents (الأسس)
3. **M**ultiplication and **D**ivision (الضرب والقسمة من اليسار لليمين)
4. **A**ddition and **S**ubtraction (الجمع والطرح من اليسار لليمين)

```python
# مثال بأولوية مختلفة
result1 = 2 + 3 * 4  # = 2 + 12 = 14
result2 = (2 + 3) * 4  # = 5 * 4 = 20

print("2 + 3 * 4 = " + str(result1))
print("(2 + 3) * 4 = " + str(result2))

# حساب معقد
total = 100 + (50 * 2) - (25 / 5)  # = 100 + 100 - 5 = 195
print("100 + (50 * 2) - (25 / 5) = " + str(total))
```

---

## الأخطاء الشائعة (وكيفية إصلاحها!) ❌➡️✅

### الخطأ الأول: استخدام = بدلاً من ==
```python
# ❌ خطأ
age = 16
if age = 16:  # هذا تعيين، وليس مقارنة!
    print("You are 16")

# ✅ صحيح
age = 16
if age == 16:  # هذه مقارنة
    print("You are 16")
```

### الخطأ الثاني: نسيان تحويل المدخل إلى أرقام
```python
# ❌ خطأ
num1 = input("Enter first number: ")
num2 = input("Enter second number: ")
result = num1 + num2  # هذا يربط النصوص!
print("Sum: " + result)  # الناتج: Sum: 12 (إذا أدخل المستخدم 1 و 2)

# ✅ صحيح
num1 = int(input("Enter first number: "))
num2 = int(input("Enter second number: "))
result = num1 + num2  # هذا يجمع الأرقام!
print("Sum: " + str(result))  # الناتج: Sum: 3 (إذا أدخل المستخدم 1 و 2)
```

### الخطأ الثالث: عامل خاطئ للقسمة
```python
# ❌ خطأ
a = 10
b = 3
result = a / b
print("Result: " + str(int(result)))  # هذا يقطع العلامة العشرية

# ✅ صحيح
a = 10
b = 3
result = a / b
print("Result: " + str(result))  # هذا يظهر العلامة العشرية
```

---

## تحديات ممتعة! 🎯

### التحدي الأول: متتبع المالية الشخصية
أنشئ برنامجاً يتتبع المالية الشخصية:

```python
print("💰 Personal Finance Tracker 💰")

# الحصول على المعلومات المالية
income = float(input("Monthly income: $"))
rent = float(input("Monthly rent: $"))
food = float(input("Monthly food expenses: $"))
entertainment = float(input("Monthly entertainment: $"))

# حساب المجاميع
total_expenses = rent + food + entertainment
savings = income - total_expenses
savings_percentage = (savings / income) * 100

# عرض النتائج
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

### التحدي الثاني: حاسبة اللياقة البدنية
أنشئ برنامجاً يحسب مقاييس اللياقة البدنية:

```python
print("💪 Fitness Calculator 💪")

# الحصول على معلومات المستخدم
weight = float(input("Your weight (lbs): "))
height = float(input("Your height (inches): "))
age = int(input("Your age: "))
activity_level = input("Activity level (low/medium/high): ").lower()

# حساب مؤشر كتلة الجسم
bmi = (weight / (height * height)) * 703

# حساب السعرات الحرارية اليومية (تقدير تقريبي)
if activity_level == "low":
    calories = weight * 15
elif activity_level == "medium":
    calories = weight * 17
else:
    calories = weight * 20

# عرض النتائج
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

### التحدي الثالث: متتبع نقاط اللعبة
أنشئ برنامجاً يتتبع نقاط اللعبة:

```python
print("🎮 Game Score Tracker 🎮")

# الحصول على معلومات اللعبة
player_name = input("Player name: ")
level = int(input("Current level: "))
score = int(input("Current score: "))
time_played = int(input("Time played (minutes): "))

# حساب المقاييس
score_per_minute = score / time_played
level_progress = (level / 100) * 100  # افتراض أن المستوى الأقصى هو 100

# عرض النتائج
print("\n🏆 Game Statistics for " + player_name + ":")
print("Level: " + str(level))
print("Score: " + str(score))
print("Time Played: " + str(time_played) + " minutes")
print("Score per Minute: " + str(round(score_per_minute, 2)))
print("Level Progress: " + str(round(level_progress, 1)) + "%")

# تقييم الأداء
if score_per_minute > 100:
    print("Rating: ⭐⭐⭐ Excellent!")
elif score_per_minute > 50:
    print("Rating: ⭐⭐ Good!")
else:
    print("Rating: ⭐ Keep practicing!")
```

---

## ما التالي؟ 🚀

لقد تعلمت كيفية القيام بالرياضيات والمقارنات مع متغيراتك! الآن يمكنك:
- إجراء الحسابات في برامجك
- مقارنة القيم واتخاذ القرارات
- استخدام العوامل المنطقية للتفكير المعقد

**في الدرس التالي، ستتعلم:**
- كيفية استخدام عبارات if لاتخاذ القرارات
- كيفية إنشاء مسارات مختلفة في برامجك
- كيفية جعل برامجك أكثر ذكاءً!

---

## وقت الممارسة! 💪

**جرب هذه التمارين:**

1. **أنشئ برنامجاً يحسب مساحة الأشكال المختلفة**
2. **اصنع برنامجاً يحدد ما إذا كان شخص ما يمكنه التصويت**
3. **ابني برنامجاً يحسب البقشيش للمطاعم**
4. **صمم برنامجاً يحول درجات الحرارة بين السيليزيوس والفهرنهايت**

**تذكر:** العوامل تجعل برامجك قوية وقادرة على إجراء حسابات حقيقية!

---

## حقائق ممتعة! 🎉

- **بايثون تتبع PEMDAS** تماماً مثل فصل الرياضيات!
- **عوامل المقارنة** تعيد دائماً True أو False
- **العوامل المنطقية** تساعدك في اتخاذ قرارات معقدة
- **يمكنك دمج** العديد من العوامل في تعبير واحد!

---

## أسئلة للنقاش 💭

1. **ما هو الحساب الأكثر إثارة للاهتمام قمت به؟**
2. **كيف تعتقد أن العوامل تساعد في جعل البرامج أكثر فائدة؟**
3. **أي نوع من مشاكل العالم الحقيقي يمكنك حلها بالعوامل؟**

---

## التالي: عبارات If! 🤔

في الدرس التالي، ستتعلم كيفية جعل برامجك تتخذ قرارات وتختار مسارات مختلفة!

**استمر في الحساب والمقارنة!** 🎉
