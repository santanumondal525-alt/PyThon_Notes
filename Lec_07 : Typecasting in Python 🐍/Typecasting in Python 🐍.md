# 🔄 Type Casting in Python
<sub>📺 <a href="https://youtu.be/c98KSQXQopI?si=I6a1oO1KerbbwZA8">Video Link</a></sub>

### The Problem That Type Casting Solves

Let's start with a simple program that adds two numbers taken from the user at runtime:

```python
num1 = input("Enter First Number: ")
num2 = input("Enter Second Number: ")
print(num1 + num2)
```

**Sample Run:**
```
Enter First Number: 12
Enter Second Number: 14
Output: 1214    ❌ Wrong! Expected 26
```

### Why Did This Happen?

| What We Input | How Python Treats It | Result |
| :--- | :--- | :--- |
| `12` | Stored as **string** `"12"` | |
| `14` | Stored as **string** `"14"` | |
| `"12" + "14"` | String **concatenation**, not addition | `"1214"` |

> **The `input()` function always returns a string by default.** So even though we entered numbers, they were stored as strings, and the `+` operator concatenated them instead of adding them.

---

## 1. 🎯 What is Type Casting?

**Type Casting** is the process of converting data from one data type to another.

> It is also called **Type Conversion**.

---

## 2. 📊 Two Types of Type Casting

| Type | Who Does It? | When? |
| :--- | :--- | :--- |
| **Implicit** 🤖 | Python does it **automatically** | During runtime, without user instruction |
| **Explicit** ✍️ | **Programmer/User** does it manually | Using functions like `int()`, `float()`, etc. |

---

## 3. ✍️ Explicit Type Casting

When we **manually** convert one data type to another using built-in functions.

### 3.1 Fixing Our Addition Problem

```python
num1 = int(input("Enter First Number: "))    # Convert to int
num2 = int(input("Enter Second Number: "))   # Convert to int
print(num1 + num2)
```

**Sample Run:**
```
Enter First Number: 12
Enter Second Number: 14
Output: 26    ✅ Correct!
```

> By wrapping `input()` inside `int()`, we **explicitly** tell Python to treat the input as an integer.

---

### 3.2 Explicit Conversion Functions

| Function | Converts To | Example | Output |
| :--- | :--- | :--- | :--- |
| `int()` | Integer | `int("10")` | `10` |
| `float()` | Float | `float(11)` | `11.0` |
| `str()` | String | `str(10)` | `"10"` |
| `bool()` | Boolean | `bool(1)` | `True` |
| `hex()` | Hexadecimal | `hex(11)` | `0xb` |
| `oct()` | Octal | `oct(11)` | `0o13` |
| `bin()` | Binary | `bin(11)` | `0b1011` |
| `ord()` | Unicode/ASCII code | `ord("A")` | `65` |
| `chr()` | Character from code | `chr(65)` | `"A"` |

---

### 3.3 Conversion Examples in Action

```python
a = 11

print(float(a))      # 11.0
print(hex(a))        # 0xb        (11 in hex = B)
print(oct(a))        # 0o13       (11 in octal = 13)
print(bin(a))        # 0b1011     (11 in binary = 1011)
```

| Decimal 11 | Hexadecimal | Octal | Binary |
| :---: | :---: | :---: | :---: |
| 11 | `b` | `13` | `1011` |

### ASCII / Unicode Conversions:

| Function | Input | Output | Explanation |
| :--- | :---: | :---: | :--- |
| `ord("A")` | `"A"` | `65` | ASCII code of capital A |
| `chr(65)` | `65` | `"A"` | Character for code 65 |

> **Prefix Meanings:**
> - `0b` → Binary
> - `0o` → Octal
> - `0x` → Hexadecimal

---

## 4. 🤖 Implicit Type Casting

When Python **automatically** converts one data type to another **without the programmer's instruction**.

### Rule of Implicit Conversion:

> **Python always converts the LOWER data type to the HIGHER data type to prevent data loss.**

| Lower Type | Higher Type |
| :---: | :---: |
| `int` | `float` |
| `int` | `complex` |

### Example:

```python
a = 20      # int
b = 20.5    # float

print(a + b)        # 40.5  → int converted to float automatically
print(a * b)        # 410.0 → int converted to float automatically
```

### Why Does Python Do This?

| Scenario | Result | Data Loss? |
| :--- | :--- | :---: |
| Convert `int` → `float` | `20` → `20.0` | ❌ No loss |
| Convert `float` → `int` | `20.5` → `20` | ✅ Yes, `.5` is lost! |

> Python **never** wants to lose data, so it always converts the **smaller type** (`int`) to the **larger type** (`float`).

---

## 5. 📊 Explicit vs Implicit — Quick Comparison

| Feature | Explicit | Implicit |
| :--- | :--- | :--- |
| **Who does it?** | Programmer/User | Python automatically |
| **How?** | Using functions like `int()`, `float()` | Automatically during mixed-type operations |
| **Example** | `int("10")` | `20 + 20.5` → int becomes float |
| **Direction** | Any direction (user decides) | Always lower → higher type |
| **Data Loss Risk** | Yes, if user is careless | No, Python prevents data loss |

---

## 6. 📝 All Conversion Functions — Quick Reference

| Function | Purpose | Example Input | Example Output |
| :--- | :--- | :---: | :---: |
| `int()` | Convert to Integer | `int("10")` | `10` |
| `float()` | Convert to Float | `float(11)` | `11.0` |
| `str()` | Convert to String | `str(10)` | `"10"` |
| `bool()` | Convert to Boolean | `bool(0)` | `False` |
| `hex()` | Convert to Hexadecimal | `hex(11)` | `0xb` |
| `oct()` | Convert to Octal | `oct(11)` | `0o13` |
| `bin()` | Convert to Binary | `bin(11)` | `0b1011` |
| `ord()` | Character → ASCII/Unicode | `ord("A")` | `65` |
| `chr()` | ASCII/Unicode → Character | `chr(65)` | `"A"` |

---

## 7. 📝 Key Takeaways

| Point | Details |
| :--- | :--- |
| **Default Input Type** | `input()` always returns string — type cast when doing math |
| **Type Casting** | Converting data from one type to another |
| **Explicit** | Manual conversion using `int()`, `float()`, etc. |
| **Implicit** | Automatic conversion by Python (lower → higher type) |
| **Data Loss Prevention** | Python never converts higher to lower type implicitly |
| **Exam Tip** | Know the difference between explicit and implicit, and remember all conversion function names |

---

**Now you understand Type Casting completely!** 🔄
