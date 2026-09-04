[python_notesv3.md](https://github.com/user-attachments/files/31846223/python_notesv3.md)


# Python Learning Notes

## Table of Contents
1. [Print Function](#1-print-function)
2. [Variables](#2-variables)
3. [Input Function](#3-input-function)
4. [Data Types](#4-data-types)
5. [Functions & Modules](#5-functions--modules)
6. [String Functions](#6-string-functions)
7. [Numeric Functions](#7-numeric-functions)
8. [Control Flow](#8-control-flow)

---

## 1. Print Function

- `\n` adds a new line
- `\t` adds a tab
- Wrapping text in `"""..."""` lets a `print()` span multiple lines

```python
print("Your Learning Path:\n\t-Python Basics\n\t-Data Engineering\n\t-AI")

# Same thing, spread across lines with triple quotes
print("""Your Learning Path:

\t-Python Basics

\t-Data Engineering

\t-AI""")
```

---

## 2. Variables

Variables store a value in memory under a name so it can be reused, making programs more dynamic.

```python
name = "Jack"
language = "Python"
print("My name is", name)
print(name, "is Learning", language)
print(name, "wants to be a", language, "Expert")

name = "Jeff"
print("My name is", name)
print(name, "is Learning Python")
print(name, "wants to be a Python Expert")
```

### Challenge: build strings with f-strings
Use `{}` inside an f-string (`f"..."`) to insert a variable without manual spacing/concatenation.

```python
name = "baraa"
print(f"info@datawith{name}.com")
print(f"support@datawith{name}.com")
print(f"www.datawith{name}.com")
```

---

## 3. Input Function

- **Dynamic value:** `name = input("Enter your name:")`
- **Static value:** `country = "'Merica"`

```python
name = input("Enter your name:")
country = "'Merica"
print(name, "comes from", country)
```

---

## 4. Data Types

### Core types
- **`str`** — letter/text values that can be referenced. Adding strings together does no math, it just combines them.
- **`int`** — numerical values that can be referenced.

Numbers written **without quotes** are integers; the same digits **with quotes** are strings.

### Single-value ("primitive") types
- No value: `None`
- Numeric: `int` (`50`), `float` (`3.14`), `complex` (`3 + 5j`)
- Text/logic: `str` (`"Hello"`), `bool` (`True`/`False`)
- Date/time: `date` (`2026-12-25`), `time` (`18:05:30`), `datetime` (`2026-12-25 18:05:30`)

### Multi-value types (Data Structures / Collections / Containers)
- `list`: `[1, 2, 3]`
- `set`: `{1, 2}`
- `tuple`: `('a', 'b', 'c')`
- `dict`: `{'a': 1, 'b': 2, 'c': 3}`

### Type notes
- `int` — whole numbers, no decimal
- `float` — partial numbers, with a decimal
- `str` — text or a sequence of characters, in single or double quotes
- `bool` — `True`/`False`, used for logic and decisions; case-sensitive, first letter capitalized
- `None` — means "no value" or "unknown," shows the absence of data
- Blank `""` — a string with zero characters; **not** the same as `None`
- Whitespace `" "` — a string with one or more spaces; **not** the same as `None` or blank

```python
a = 10       # int
b = 3.15     # float
c = "Tupac"  # str
d = 'Biggie' # str
e = "1234"   # str
f = True     # bool
g = False    # bool
h = None     # NoneType
i = ""       # str - Blank
j = " "      # str - Whitespace
```

---

## 5. Functions & Modules

**Functions + Data Types:** data is values, a function does something to that data → `Value + Function = New Value`.

### Functions vs. Methods
- **Function:** independent block of code — `function_name(value)` — e.g. `print("Hello")`, `type(50)`
- **Method:** a function that belongs to an object/class — `value.method_name()` — e.g. `"Hello".upper()`, `(50).bit_length()`

### Categories
| Category | Examples |
|---|---|
| Standalone functions | `print()`, `type()` |
| Methods of a class | `.upper()`, `.replace()` |
| Operators | `+`, `-`, `/`, `<`, `>`, `==`, `=`, `in`, `or` |

These live in the **Standard Library**. Extra functionality comes from 3rd-party libraries (Pandas, NumPy, TensorFlow, etc.).

### Modules
Modules are reusable, built-in code (e.g. `len()`, `type()`, `print()` are built in; importing the `math` module adds `abs()`, `round()`, `floor()`, etc.).

Methods are how functions are categorized by class (`str` methods vs. `int` methods) — a type's methods only work on that type:
- `str` methods (`.upper()`, `.replace()`) don't work on `int`.
- `int` methods (`.to_bytes()`) don't work on `str`.
- `len()` doesn't work on `int` — it's unable to be interpreted.
- Math-module functions (`abs()`, `round()`, `floor()`) do work on `int`/`float`.

### Playground
```python
text = "hi"
number = 10

print(type(text))     # tells you the data type
print(type(number))

print(len(text))       # works — text is a string
# print(len(number))    # breaks — int has no length

print(text.upper())            # "HI"
print(number.bit_length())     # bytes used to store the value
```

### Challenge
Create 5 variables, each a different data type (age, height, name, is_student, and an empty/`None` value), then print each variable's value, type, and length.

---

## 6. String Functions

### Overview, by category
- **Types:** `type()`, `str()`
  - `str()` — when used inside `print()`, it converts a value to a string only for that call; it doesn't change the original value's type.
- **Math:** `len()`, `.count()`
  - `.count()` — returns how often a substring appears in the string (case-sensitive).
- **Transformations:** `.replace()`, `+`, f-strings, `.split()`, `*`, extraction (`[0]`, `[1:3]`)
  - `.replace()` — takes an old value and a new value; finds the old and swaps in the new. Also a handy trick for removing unwanted characters by replacing them with `""`.
  - **f-string** — modern, easy way to format/build strings (f = "formatted"), e.g. `print(f"My name is {name} and i am {age} years old.")`
  - `.split()` — splits one string into multiple values, e.g. `"Adam-24-USA".split('-')` → `["Adam", "24", "USA"]`
- **Cleaning:** `.lstrip()`, `.rstrip()`, `.strip()`; case conversion: `.lower()`, `.upper()`
- **Search:** `.startswith()`, `.endswith()`, `.find()`, `in`
- **Validation:** `.isalpha()`, `.isnumeric()`

### 6.1 Types
```python
name = "Jeff"
print(type(name))          # <class 'str'>

age = 24
print(type(age))           # <class 'int'>
print("Your Age is:" + str(age))   # str() here only converts for this print call

age = age + 5
age = str(age)
print(type(age))           # now a str
# age = age + 5             # would break — age is now a string, not an int
```

### 6.2 Math — `len()` and `.count()`
```python
password = "1236344634634636a"
print(len(password))

if len(password) < 8:
    print("Your password is too short!")   # validates input length

# .count() — how often a substring appears (case-sensitive!)
text = """Python is easy to learn
Python is Powerful.
Many people love python.
"""
print(text.count("Python"))   # 2 — lowercase "python" doesn't match
```

### 6.3 Transformations — `.replace()`
```python
price = "$1,299.99"
print(price.replace("$", "").replace(",", ""))

phone = "815-675-6849"
print(phone.replace("-", " "))
```

**Challenge:** clean a messy international phone number down to digits only.
```python
phone_number = "+49 (176) 123-4567"
print(phone_number.replace("+", "").replace("(", "").replace(")", "")
                   .replace("-", "").replace(" ", ""))
```

### 6.4 Transformations — Concatenation (`+`) and f-strings
```python
first_name = "Scott"
last_name = "Michaelson"
last_name = first_name + " " + last_name
print(last_name)

folder = "C:/Users/Jeff"
file = "report.csv"
full_file_path = folder + "/" + file
print(full_file_path)
```

```python
name = "Jack"
age = 34
is_student = False

# The old, verbose way:
print("My name is " + name + ", I am " + str(age) +
      " years old, and student status is " + str(is_student) + ".")

# The f-string way:
print(f"My name is {name}, I am {age} years old, and student status is {is_student}.")

# f-strings can also evaluate expressions:
print(f"2 + 3 = {2 + 3}")

# Double the braces to print a literal { }:
print(f"{{this is me}}")
```

### 6.5 Transformations — `.split()`
```python
stamp = "2026-09-20 14:30"
print(stamp.split(" "))

stamp = "2026-09-20"
print(stamp.split("-"))

csv_file = "1234,Max,USA,1970-10-05,M"
print(csv_file.split(","))   # separates values into individual pieces
```

### 6.6 Transformations — Repetition (`*`) and Extraction (Indexing & Slicing)
```python
print("ha" * 3)
print("#" * 30)
```

- **Indexing:** every character in a string has a position.
  - *Positive index* — left to right, starting at `0`.
  - *Negative index* — right to left, starting at `-1` (no `0`).
- **Slicing `[start:end]`:** `start` is included, `end` is not.
- **Open-ended slicing `[1:]`:** everything from index 1 onward (the `:` is required — `[1]` alone gives just one character).
- **Step `[start:end:step]`:** skips characters as it goes, e.g. `"Hello"[0:4:2]` includes every 2nd character.

**When to use which:** positive index is easiest counting in from the left; negative is easiest counting in from the right. For a long string, pick whichever side simplifies the calculation.

```python
text = "python"
print(text[0], text[-6])   # first character, two ways
print(text[5], text[-1])   # last character, two ways

date = "2026-09-20"
print(date[0:4])    # year
print(date[:4])     # same result

print(date[5:7])    # month

print(date[8:])     # day
print(date[-2:])    # same result
```

### 6.7 Cleaning — whitespace strip
- `.lstrip()` — removes from the **left** only
- `.rstrip()` — removes from the **right** only
- `.strip()` — removes from **both** sides
- Only trims the *edges*, not the middle — and works on any character, not just spaces.

```python
print(" Engineering".lstrip())
print("Engineering ".rstrip())
print("     Engineering ".strip())
print("Data engineering".strip())
print("###abc###".strip("#"))
```

**Use case — detect hidden whitespace:**
```python
text = "  Engineering"
print(len(text))
print(len(text.strip()))

nr_of_spaces = len(text) - len(text.strip())
is_clean = len(text) == len(text.strip())
print("Nr of Spaces:", nr_of_spaces)
print("Is my Data Clean?", is_clean)
```

### 6.8 Cleaning — case conversion
Primarily used for cleaning up data before comparing/matching it.
```python
text = "python PROGRAMMING"
print(text.lower())
print(text.upper())

search = "email ".lower().strip()
data = " Email".lower().strip()
print(search == data)
```

### 6.9 Challenge — clean a messy record
Turn `"968-Maria, ( D@t@ Engineer ) ;;  27y  "` into `Name: Maria | role: data engineer | age: 27`

```python
text = "968-Maria, ( D@t@ Engineer ) ;;  27y  "

# Drop the leading id
maria = text.split("-", 1)[1]

# Split name from the rest
name, rest = maria.split(",", 1)
name = name.strip()

# Pull role out of the parentheses
role = rest.split("(")[1].split(")")[0].strip().replace("@", "a").lower()

# Everything after the closing paren is the age chunk
age = rest.split(")")[1].strip(" ;").rstrip("y")

print(f"Name: {name} | role: {role} | age: {age}")
```

### 6.10 Search — `.startswith()`, `.endswith()`, `in`, `.find()`
`in` searches a string for a match and is less restrictive than `.startswith()`/`.endswith()` — it checks anywhere in the string. `.find()` returns the position of a match.

```python
phone = "=49-176-12345"
print(phone.startswith("=49"))

email = "baraa@gmail.com"
print(email.endswith("gmail.com"))

file = "data_backup.csv"
print(file.endswith(".csv"))

print("@" in email)

url = "https://api.company.com/v1/data"
print("/api" in url)
```

`.find()` is great combined with slicing to make code dynamic instead of hardcoded:
```python
phone1 = "=49-176-12345"
phone2 = "48-654-57389"
phone3 = "0048-654-57389"

# Dynamic — works regardless of prefix length, unlike a hardcoded phone2[3:]
print(phone1[phone1.find("-")+1:])
print(phone2[phone2.find("-")+1:])
print(phone3[phone3.find("-")+1:])
print(phone1.find("-"))
```

### 6.11 Validation — `.isalpha()`, `.isnumeric()`
- `.isalpha()` — checks if the string contains only letters (boolean result).
- `.isnumeric()` — checks if the string contains only numeric values (no letters, signs, or decimals).
- Useful for preventing invalid data from reaching the wrong input.

```python
country = "USA"
print(country.isalpha())      # True — letters only

phone = "0854-085048"
print(phone.isnumeric())      # False — contains a "-"
```

---

## 7. Numeric Functions

### Number types
- `int` — whole numbers: `5`, `-12`, `10000`
- `float` — decimal/floating-point numbers, also used for percentages: `3.15`, `-0.5`, `100.00`
- `complex` — real + imaginary numbers (advanced math/engineering/physics/science)

### Reference
| Category | Functions |
|---|---|
| Type | `type()`, `int()`, `float()`, `complex()` |
| Math operators | `+`, `-`, `*`, `/`, `//`, `%`, `**` |
| Rounding | `abs()`, `round()`, `ceil()`, `floor()`, `trunc()` |
| Advanced math | `sqrt()`, `sin()`, `cos()`, `log()` *(no examples yet)* |
| Random | `random()`, `randint()` |
| Validation | `.is_integer()`, `isinstance()` |

For advanced math you need to `import` the `math` module — it adds these enhanced commands to your code.

### 7.1 Types
```python
x = 5
y = 5.7
z = 2 + 3j

print(type(x))   # int
print(type(y))   # float
print(type(z))   # complex

x = "24"
print(type(x))   # str
x = int(x)
print(type(x))   # int
print(x * 3)

x = "3.14"
x = float(x)
print(type(x))
print(x * 5)

x = 3
x = float(x)
print(type(x))
print(x * 7)
```

### 7.2 `complex()`
```python
x = 5   # Real
y = 7   # Imaginary
print(complex(x, y))
```

### 7.3 Math Operators
```python
print(2 + 3)
print(6 - 3)
print(74 * 9)
print(7 / 2)    # floating-point division
print(7 // 2)   # integer (floor) division
print(7 % 2)    # modulo — the leftover after division; common way to check even/odd
print(2 ** 3)   # exponent — raises to a power
```

### 7.4 Shortcut operators
`+=` (and similar) shorten `x = x + 3` into a smaller chunk of code.
```python
x = 2
x = x + 3
# The line above and below do the same thing:
x += 3
print(x)

x -= 1
print(x)

x *= 2
print(x)
```

### 7.5 Rounding
- **`abs()`** — returns the absolute (non-negative) value of a number; useful for measuring distance or size regardless of direction.
- **`math.floor()` / `math.ceil()`** — round to a whole number. `floor()` always rounds down no matter how close to the ceiling (e.g. `1.7` → `1`); `ceil()` always rounds up no matter how close to the floor (e.g. `1.3` → `2`). Great use case in data engineering for splitting data into pages or batches.
- **`round()`** — rounds to the nearest whole number, up or down depending on which is closer. Very useful in data analysis for cleaning up numbers for reports.
  - **Banker's rounding:** ties (like `.5`) round to the nearest *even* number — it only cares whether the result is odd or even.
- **`math.trunc()`** — keeps the whole number without rounding at all; this behavior is shared with `int()`.
  - **When to use `trunc()` vs. `int()`:** if you're not already using the `math` module, just use `int()`. If you've already imported `math`, use `trunc()` to make your intent clearer.

```python
# Measuring Distance
print(abs(2 - 10))

# Rounding Numbers
import math
price = 35.6746896848

print(round(price))
print(round(price, 2))   # rounds to a specified number of digits
print(round(price, 1))

print(math.floor(price))
print(math.ceil(price))
print(math.trunc(price))   # keeps the whole number without rounding
print(int(price))          # another way to drop the decimal
```

### 7.6 Random
`random.random()` returns a random float between `0.0` and `1.0`. `random.randint(a, b)` returns a random integer between two given values. Used to generate test/dummy data, and for random sampling — picking a smaller, random part of a huge dataset. Requires `import random`.

```python
import random
print(random.random())
print(random.randint(1, 6))
# used to generate test or dummy data
# Random Sampling - picking a smaller, random part of a huge dataset
```

### 7.7 Validation
- **`.is_integer()`** — tells you (as a boolean) whether a float is a truly whole number. Useful for checking if numbers coming from a file export (e.g. `40.00`, `25.00`, `24665.0000`) are actually whole.
- **`isinstance()`** — tells you whether a variable is a given type, as a boolean. Used to build logic, conditions, and data validation.

```python
x = 7.0
print(x.is_integer())   # True

y = 7.1
print(y.is_integer())   # False
# Check if numbers are truly whole floats with .0 — useful for values from file exports

x = 70
print(isinstance(x, int))     # True
print(isinstance(x, float))   # False
```

### 7.8 Challenge — random even/odd check
Generate a random integer between 1 and 100, and check whether the result is even.
```python
import random
x = random.randint(1, 100)
is_even = x % 2 == 0
# If x divided by 2 has no remainder, it's even
print(x, "Is even", is_even)
```

---

## 8. Control Flow

Control flow is the logic you write to control how your code runs — it helps your code decide:
- "Should I run this part of the code?"
- "Should I skip it?"
- "Should I repeat it?"

**Analogy:** control flow is like a traffic light system for cars, but for logic — it gives your code a path to follow instead of a straight line.

- **Straight-line code** — runs like a car driving in a straight line: executes the entire code from end to end.
- **Conditional statement** — a crossroads for the code: takes an input and goes down a path based on a True/False value.
- **Loops** — used for repeating a block of code multiple times. While the condition stays `True`, the loop keeps running; once it hits `False`, it stops and moves to the next step.

### Control Flow Tools

**Statements**
- Conditional statements: `if`, `else`, `elif`
- Loops: `for`, `while` — plus `break`, `pass`, and `continue` for exiting/skipping within a loop

**Expressions** — build questions/conditions that Python can evaluate as Yes/No
- Values: `True`, `False`
- Functions: `bool()`, `any()`, `all()`, `isinstance()`
- Comparison operators: `==`, `!=`, `<`, `>`, `>=`, `<=`
- Logical operators: `and`, `or`, `not`
- Membership operators: `in`, `not in`
- Identity operators: `is`, `is not`

*(Code examples for this section still to be added.)*
