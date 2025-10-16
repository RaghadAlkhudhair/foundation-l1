# قراءة المدخلات 📖
## جعل برامجك تفاعلية

### الأهداف التعليمية
بنهاية هذا الدرس، سيكون الطلاب قادرين على:
- استخدام `input()` للحصول على مدخلات المستخدم
- إنشاء برامج تفاعلية
- فهم كيفية تخزين استجابات المستخدمين
- بناء برامج تستجيب للمستخدمين

---

## ما هي المدخلات؟ 🤔

**المدخلات هي المعلومات التي تأتي من المستخدم إلى برنامجك!**

فكر فيها مثل محادثة:
- **أنت تسأل سؤالاً** (باستخدام `print()`)
- **المستخدم يكتب إجابة** (باستخدام `input()`)
- **برنامجك يستجيب** (باستخدام `print()`)

### تشبيه من العالم الحقيقي: طلب مطعم
- **النادل يسأل:** "ماذا تريد أن تأكل؟" (`print()`)
- **أنت تجيب:** "سآخذ بيتزا" (`input()`)
- **النادل يستجيب:** "اختيار رائع!" (`print()`)

---

## دالة `input()` 📝

### الصيغة الأساسية
```python
user_input = input("Ask your question here: ")
```

### كيف تعمل
1. **تعرض الرسالة** للمستخدم
2. **تنتظر** المستخدم ليكتب شيئاً
3. **تخزن** ما كتبه في متغير
4. **تستمر** مع باقي برنامجك

---

## برنامجك التفاعلي الأول! 🎉

### المثال الأول: تحية بالاسم
```python
name = input("What's your name? ")
print("Hello, " + name + "!")
print("Nice to meet you!")
```

**جربها!** ماذا يحدث عندما تشغل هذا؟

### المثال الثاني: فاحص العمر
```python
age = input("How old are you? ")
print("You are " + age + " years old!")
print("That's awesome!")
```

### المثال الثالث: اللون المفضل
```python
color = input("What's your favorite color? ")
print("I love " + color + " too!")
print(color + " is a beautiful color!")
```

---

## أمثلة من العالم الحقيقي 🌟

### المثال الأول: نظام طلب البيتزا
```python
print("🍕 Welcome to Pizza Palace! 🍕")
name = input("What's your name? ")
pizza_type = input("What type of pizza would you like? ")
size = input("What size? (Small, Medium, Large): ")

print("Thank you, " + name + "!")
print("You ordered a " + size + " " + pizza_type + " pizza!")
print("Your order will be ready in 20 minutes!")
```

### المثال الثاني: تسجيل مدرسي
```python
print("📚 School Registration Form 📚")
first_name = input("First name: ")
last_name = input("Last name: ")
grade = input("What grade are you in? ")
favorite_subject = input("What's your favorite subject? ")

print("Welcome to our school, " + first_name + " " + last_name + "!")
print("Grade " + grade + " is awesome!")
print("I hope you enjoy " + favorite_subject + "!")
```

### المثال الثالث: تطبيق الطقس
```python
print("🌤️ Weather Checker 🌤️")
city = input("What city are you in? ")
temperature = input("What's the temperature? ")
weather = input("Is it sunny, cloudy, or rainy? ")

print("Weather report for " + city + ":")
print("Temperature: " + temperature + " degrees")
print("Conditions: " + weather)
print("Have a great day!")
```

---

## ألعاب تفاعلية ممتعة! 🎮

### اللعبة الأولى: كرة 8 السحرية
```python
print("🔮 Magic 8-Ball 🔮")
question = input("Ask me a yes/no question: ")
print("You asked: " + question)
print("The Magic 8-Ball says: It is certain!")
print("Ask another question if you want!")
```

### اللعبة الثانية: منشئ الحيوانات الأليفة
```python
print("🐾 Create Your Virtual Pet! 🐾")
pet_name = input("What would you like to name your pet? ")
pet_type = input("What type of animal? (dog, cat, bird, etc.): ")
pet_color = input("What color should it be? ")

print("Meet your new pet!")
print("Name: " + pet_name)
print("Type: " + pet_type)
print("Color: " + pet_color)
print(pet_name + " is so happy to meet you!")
```

### اللعبة الثالثة: منشئ القصص
```python
print("📖 Interactive Story Creator 📖")
character = input("What's your character's name? ")
place = input("Where does the story take place? ")
animal = input("What animal appears in the story? ")
action = input("What does the character do? ")

print("Once upon a time...")
print("There was a brave character named " + character)
print("who lived in " + place)
print("One day, a " + animal + " appeared!")
print(character + " decided to " + action)
print("And they all lived happily ever after!")
print("The End! 🎉")
```

---

## الأخطاء الشائعة (وكيفية إصلاحها!) ❌➡️✅

### الخطأ الأول: نسيان تخزين المدخل
```python
# ❌ خطأ
input("What's your name? ")
print("Hello!")

# ✅ صحيح
name = input("What's your name? ")
print("Hello, " + name + "!")
```

### الخطأ الثاني: عدم استخدام المدخل
```python
# ❌ خطأ
name = input("What's your name? ")
print("Hello!")

# ✅ صحيح
name = input("What's your name? ")
print("Hello, " + name + "!")
```

### الخطأ الثالث: اسم متغير خاطئ
```python
# ❌ خطأ
name = input("What's your name? ")
print("Hello, " + user_name + "!")

# ✅ صحيح
name = input("What's your name? ")
print("Hello, " + name + "!")
```

---

## أمثلة متقدمة 🚀

### المثال الأول: حاسبة
```python
print("🧮 Simple Calculator 🧮")
num1 = input("Enter first number: ")
num2 = input("Enter second number: ")
operation = input("What operation? (+, -, *, /): ")

print("Calculating...")
print(num1 + " " + operation + " " + num2 + " = ?")
print("(We'll learn to do the math in the next lesson!)")
```

### المثال الثاني: نموذج المعلومات الشخصية
```python
print("📋 Personal Information Form 📋")
print("Please fill out the following information:")

first_name = input("First name: ")
last_name = input("Last name: ")
age = input("Age: ")
school = input("School name: ")
hobby = input("What's your hobby? ")

print("\n📄 Here's your information:")
print("Name: " + first_name + " " + last_name)
print("Age: " + age)
print("School: " + school)
print("Hobby: " + hobby)
print("Thank you for filling out the form!")
```

### المثال الثالث: لعبة اختبار
```python
print("🎯 Quick Quiz Game 🎯")
print("Answer these questions:")

q1 = input("What's 2 + 2? ")
q2 = input("What color is the sky? ")
q3 = input("How many days are in a week? ")

print("\nYour answers:")
print("2 + 2 = " + q1)
print("Sky color = " + q2)
print("Days in week = " + q3)
print("Thanks for playing!")
```

---

## تحديات ممتعة! 🎯

### التحدي الأول: مساعد شخصي
أنشئ برنامجاً يعمل كمساعد شخصي:

```python
print("🤖 Your Personal Assistant 🤖")
name = input("What's your name? ")
task = input("What do you need help with? ")
time = input("When do you need it done? ")

print("Hello " + name + "!")
print("I'll help you with: " + task)
print("I'll have it ready by: " + time)
print("Is there anything else I can help with?")
```

### التحدي الثاني: قائمة مطعم
أنشئ قائمة تفاعلية:

```python
print("🍽️ Welcome to Our Restaurant! 🍽️")
print("Here's our menu:")
print("1. Pizza - $10")
print("2. Burger - $8")
print("3. Salad - $6")

choice = input("What would you like to order? (1, 2, or 3): ")
name = input("What's your name for the order? ")

print("Thank you, " + name + "!")
print("Your order #" + choice + " will be ready soon!")
```

### التحدي الثالث: لعبة Mad Libs
أنشئ لعبة Mad Libs:

```python
print("📝 Mad Libs Game 📝")
print("Let's create a funny story!")

adjective1 = input("Enter an adjective: ")
noun1 = input("Enter a noun: ")
verb1 = input("Enter a verb: ")
adjective2 = input("Enter another adjective: ")
noun2 = input("Enter another noun: ")

print("\nHere's your story:")
print("The " + adjective1 + " " + noun1 + " decided to " + verb1)
print("in the " + adjective2 + " " + noun2 + ".")
print("It was the most " + adjective1 + " day ever!")
```

---

## ما التالي؟ 🚀

لقد تعلمت كيفية جعل برامجك تفاعلية! الآن يمكنك:
- طرح أسئلة على المستخدمين
- الحصول على استجاباتهم
- استخدام إجاباتهم في برامجك

**في الدرس التالي، ستتعلم:**
- كيفية تخزين المعلومات في متغيرات
- كيفية استخدام أنواع مختلفة من البيانات
- كيفية جعل برامجك أكثر قوة!

---

## وقت الممارسة! 💪

**جرب هذه التمارين:**

1. **أنشئ برنامجاً يسأل عن الأشياء المفضلة لديك**
2. **اصنع برنامجاً ينشئ تحية شخصية**
3. **ابني اختباراً بسيطاً عنك**
4. **صمم برنامجاً يساعد شخصاً في تخطيط يومه**

**تذكر:** كلما كانت برامجك أكثر تفاعلية، كلما أصبحت أكثر متعة!

---

## حقائق ممتعة! 🎉

- **دالة `input()`** تنتظر بصبر المستخدمين ليكتبوا
- **كل شيء من `input()`** يُعامل كنص (حتى الأرقام!)
- **البرامج التفاعلية** تُستخدم في كل تطبيق وموقع تقريباً
- **لقد تعلمت للتو** كيفية جعل البرامج تتحدث مع الناس!

---

## أسئلة للنقاش 💭

1. **ما هو البرنامج التفاعلي الأكثر متعة أنشأته؟**
2. **أي نوع من البرامج تريد أن تصنع يسأل المستخدمين أسئلة؟**
3. **كيف تعتقد أن المواقع والتطبيقات تستخدم المدخلات من المستخدمين؟**

---

## التالي: المتغيرات! 📦

في الدرس التالي، ستتعلم كيفية تخزين وتنظيم المعلومات باستخدام المتغيرات!

**استمر في بناء البرامج التفاعلية!** 🎉
