# المتغيرات 📦
## تخزين المعلومات في برامجك

### الأهداف التعليمية
بنهاية هذا الدرس، سيكون الطلاب قادرين على:
- فهم ما هي المتغيرات ولماذا هي مهمة
- إنشاء واستخدام متغيرات لتخزين أنواع مختلفة من البيانات
- تسمية المتغيرات باتباع الممارسات الجيدة
- استخدام المتغيرات لجعل البرامج أكثر مرونة وقوة

---

## ما هي المتغيرات؟ 🤔

**المتغيرات تشبه الصناديق المُلصقة التي تخزن المعلومات!**

فكر في المتغيرات كـ:
- **حاويات تخزين** لبياناتك
- **ملصقات** تساعدك في العثور على المعلومات لاحقاً
- **فتحات ذاكرة** تتذكر الأشياء لك

### تشبيه من العالم الحقيقي: خزانة المدرسة
- **الخزانة** = المتغير
- **رقم الخزانة** = اسم المتغير
- **الكتب بداخلها** = البيانات المخزنة في المتغير
- **يمكنك تغيير** ما بداخلها في أي وقت!

---

## لماذا نحتاج المتغيرات؟ 🌟

### بدون متغيرات (صعب التغيير)
```python
print("Hello, Sarah!")
print("Sarah is 15 years old")
print("Sarah's favorite color is blue")
print("Sarah likes pizza")
```

### مع المتغيرات (سهل التغيير!)
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

**أترى الفرق؟** مع المتغيرات، يمكنك بسهولة تغيير معلومات الشخص!

---

## إنشاء المتغيرات 📝

### الصيغة الأساسية
```python
variable_name = value
```

### قواعد أسماء المتغيرات
1. **ابدأ بحرف** (ليس رقماً)
2. **استخدم الحروف والأرقام والشرطات السفلية** فقط
3. **لا مسافات** (استخدم الشرطات السفلية بدلاً من ذلك)
4. **كن وصفياً** (الاسم يخبرك بما يخزن)

### أسماء متغيرات جيدة مقابل سيئة
```python
# ✅ أسماء جيدة
student_name = "Alex"
student_age = 14
favorite_game = "Minecraft"

# ❌ أسماء سيئة
a = "Alex"           # غير وصفي
student name = "Alex" # يحتوي على مسافة
2name = "Alex"       # يبدأ برقم
```

---

## أنواع البيانات في المتغيرات 🗂️

### 1. النص (Strings)
```python
name = "Sarah"
school = "Lincoln Middle School"
favorite_color = "purple"
```

### 2. الأرقام (Integers)
```python
age = 15
grade = 8
number_of_pets = 2
```

### 3. الأرقام العشرية (Floats)
```python
height = 5.4
weight = 120.5
temperature = 72.3
```

### 4. صحيح/خطأ (Booleans)
```python
is_student = True
has_pets = False
likes_pizza = True
```

---

## أمثلة من العالم الحقيقي 🌟

### المثال الأول: نظام معلومات الطلاب
```python
print("📚 Student Information System 📚")

# تخزين معلومات الطالب
student_name = "Emma Johnson"
student_id = 12345
grade_level = 9
gpa = 3.8
is_honor_student = True
favorite_subject = "Computer Science"

# عرض المعلومات
print("Student: " + student_name)
print("ID: " + str(student_id))
print("Grade: " + str(grade_level))
print("GPA: " + str(gpa))
print("Honor Student: " + str(is_honor_student))
print("Favorite Subject: " + favorite_subject)
```

### المثال الثاني: عربة التسوق
```python
print("🛒 Shopping Cart 🛒")

# تخزين معلومات العنصر
item_name = "Gaming Headset"
item_price = 79.99
quantity = 2
is_on_sale = True
discount_percent = 20

# حساب المجموع
subtotal = item_price * quantity
discount_amount = subtotal * (discount_percent / 100)
total = subtotal - discount_amount

# عرض المعلومات
print("Item: " + item_name)
print("Price: $" + str(item_price))
print("Quantity: " + str(quantity))
print("On Sale: " + str(is_on_sale))
print("Discount: " + str(discount_percent) + "%")
print("Total: $" + str(total))
```

### المثال الثالث: محطة الطقس
```python
print("🌤️ Weather Station 🌤️")

# تخزين بيانات الطقس
city = "New York"
temperature = 72.5
humidity = 65
is_sunny = True
wind_speed = 12.3

# عرض تقرير الطقس
print("Weather Report for " + city)
print("Temperature: " + str(temperature) + "°F")
print("Humidity: " + str(humidity) + "%")
print("Sunny: " + str(is_sunny))
print("Wind Speed: " + str(wind_speed) + " mph")
```

---

## أمثلة متغيرات تفاعلية 🎮

### المثال الأول: منشئ الملف الشخصي
```python
print("👤 Personal Profile Creator 👤")

# الحصول على معلومات من المستخدم
name = input("What's your name? ")
age = input("How old are you? ")
favorite_color = input("What's your favorite color? ")
favorite_food = input("What's your favorite food? ")
has_pets = input("Do you have pets? (yes/no): ")

# تخزين المعلومات
print("\n📋 Your Profile:")
print("Name: " + name)
print("Age: " + age)
print("Favorite Color: " + favorite_color)
print("Favorite Food: " + favorite_food)
print("Has Pets: " + has_pets)
```

### المثال الثاني: منشئ شخصية اللعبة
```python
print("🎮 Game Character Creator 🎮")

# إنشاء الشخصية
character_name = input("What's your character's name? ")
character_class = input("What class? (Warrior, Mage, Archer): ")
character_level = input("What level? (1-100): ")
character_health = input("Health points: ")
character_mana = input("Mana points: ")

# عرض إحصائيات الشخصية
print("\n⚔️ Character Stats:")
print("Name: " + character_name)
print("Class: " + character_class)
print("Level: " + character_level)
print("Health: " + character_health)
print("Mana: " + character_mana)
print("Ready for adventure!")
```

### المثال الثالث: حاسبة الوصفات
```python
print("👨‍🍳 Recipe Calculator 👨‍🍳")

# معلومات الوصفة
recipe_name = input("What are you making? ")
servings = input("How many servings? ")
cooking_time = input("How long does it take? (minutes): ")
difficulty = input("Difficulty level? (Easy/Medium/Hard): ")

# عرض معلومات الوصفة
print("\n📖 Recipe Information:")
print("Dish: " + recipe_name)
print("Servings: " + servings)
print("Cooking Time: " + cooking_time + " minutes")
print("Difficulty: " + difficulty)
print("Bon appétit!")
```

---

## تغيير المتغيرات 🔄

### يمكنك تغيير المتغيرات في أي وقت!
```python
# ابدأ بقيمة واحدة
score = 0
print("Score: " + str(score))

# غيّر القيمة
score = 10
print("Score: " + str(score))

# غيّرها مرة أخرى
score = 25
print("Score: " + str(score))
```

### مثال من العالم الحقيقي: متتبع النقاط
```python
print("🎯 Score Tracker 🎯")

# النقاط الأولية
score = 0
print("Starting score: " + str(score))

# أحداث اللعبة
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

## الأخطاء الشائعة (وكيفية إصلاحها!) ❌➡️✅

### الخطأ الأول: نسيان تحويل الأرقام إلى نص
```python
# ❌ خطأ
age = 15
print("I am " + age + " years old")

# ✅ صحيح
age = 15
print("I am " + str(age) + " years old")
```

### الخطأ الثاني: استخدام اسم متغير خاطئ
```python
# ❌ خطأ
name = "Sarah"
print("Hello, " + student_name + "!")

# ✅ صحيح
name = "Sarah"
print("Hello, " + name + "!")
```

### الخطأ الثالث: عدم استخدام علامات الاقتباس للنص
```python
# ❌ خطأ
favorite_color = blue

# ✅ صحيح
favorite_color = "blue"
```

### الخطأ الرابع: استخدام مسافات في أسماء المتغيرات
```python
# ❌ خطأ
student name = "Alex"

# ✅ صحيح
student_name = "Alex"
```

---

## تحديات ممتعة! 🎯

### التحدي الأول: مذكرات شخصية
أنشئ برنامجاً يخزن ويعرض المعلومات الشخصية:

```python
print("📔 Personal Diary 📔")

# تخزين المعلومات الشخصية
name = input("Your name: ")
birthday = input("Your birthday: ")
hobby = input("Your hobby: ")
dream_job = input("Your dream job: ")
favorite_place = input("Your favorite place: ")

# عرض إدخال المذكرات
print("\n📝 Diary Entry:")
print("Today I'm thinking about " + name + ".")
print("I was born on " + birthday + ".")
print("I love " + hobby + ".")
print("When I grow up, I want to be a " + dream_job + ".")
print("My favorite place is " + favorite_place + ".")
print("What a great day!")
```

### التحدي الثاني: كشف درجات مدرسي
أنشئ برنامجاً يتتبع الدرجات:

```python
print("📊 School Report Card 📊")

# الحصول على معلومات الطالب
student_name = input("Student name: ")
math_grade = input("Math grade: ")
science_grade = input("Science grade: ")
english_grade = input("English grade: ")
history_grade = input("History grade: ")

# عرض كشف الدرجات
print("\n🎓 Report Card for " + student_name)
print("Math: " + math_grade)
print("Science: " + science_grade)
print("English: " + english_grade)
print("History: " + history_grade)
print("Keep up the great work!")
```

### التحدي الثالث: متتبع رعاية الحيوانات الأليفة
أنشئ برنامجاً يتتبع معلومات الحيوانات الأليفة:

```python
print("🐕 Pet Care Tracker 🐕")

# معلومات الحيوان الأليف
pet_name = input("Pet's name: ")
pet_type = input("Type of pet: ")
pet_age = input("Pet's age: ")
last_vet_visit = input("Last vet visit: ")
favorite_toy = input("Favorite toy: ")

# عرض ملف الحيوان الأليف
print("\n🐾 Pet Profile:")
print("Name: " + pet_name)
print("Type: " + pet_type)
print("Age: " + pet_age)
print("Last Vet Visit: " + last_vet_visit)
print("Favorite Toy: " + favorite_toy)
print(pet_name + " is such a good " + pet_type + "!")
```

---

## ما التالي؟ 🚀

لقد تعلمت كيفية تخزين وتنظيم المعلومات باستخدام المتغيرات! الآن يمكنك:
- تتبع أنواع مختلفة من البيانات
- جعل برامجك أكثر مرونة
- تخزين مدخلات المستخدم للاستخدام لاحقاً

**في الدرس التالي، ستتعلم:**
- كيفية القيام بالرياضيات مع المتغيرات
- كيفية استخدام العوامل (+, -, *, /)
- كيفية إجراء الحسابات في برامجك!

---

## وقت الممارسة! 💪

**جرب هذه التمارين:**

1. **أنشئ برنامجاً يخزن معلومات عائلتك**
2. **اصنع برنامجاً يتتبع أفلامك وكتبك المفضلة**
3. **ابني برنامجاً يخزن معلومات عن أصدقائك**
4. **صمم برنامجاً يتتبع أنشطتك اليومية**

**تذكر:** المتغيرات تجعل برامجك قوية ومرنة!

---

## حقائق ممتعة! 🎉

- **المتغيرات تشبه الذاكرة** - تتذكر الأشياء لك
- **يمكنك تغيير المتغيرات** في أي وقت في برنامجك
- **أسماء المتغيرات الجيدة** تجعل كودك سهلاً للفهم
- **كل لغة برمجة** تستخدم المتغيرات لتخزين البيانات!

---

## أسئلة للنقاش 💭

1. **ما هو الشيء الأكثر إثارة للاهتمام خزنته في متغير؟**
2. **كيف تعتقد أن المتغيرات تساعد في جعل البرامج أكثر فائدة؟**
3. **أي نوع من المعلومات تريد أن تخزن في برنامج؟**

---

## التالي: العوامل! ➕➖✖️➗

في الدرس التالي، ستتعلم كيفية القيام بالرياضيات والحسابات مع متغيراتك!

**استمر في تخزين وتنظيم المعلومات!** 🎉
