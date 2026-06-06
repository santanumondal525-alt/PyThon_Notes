# 📥 How to Take Input from User in Python
<sub>📺 <a href="https://youtu.be/XFRyVsSdT28?si=42LkZJuhiT2bRMEw">Video Link</a></sub>

### Introduction

Just like we use:
- `scanf()` in C
- `cin` in C++

Python provides the **`input()`** function to take input from the user during runtime.

---

## 1. 🎯 Basic Syntax & Example

```python
name = input("Enter Your Name: ")
print("Hello " + name)
```

### How it Works:

| Step | Explanation |
| :--- | :--- |
| `input("Enter Your Name: ")` | Displays the prompt message and waits for user to type something. |
| `name =` | Whatever the user types gets stored in the variable `name`. |
| `print("Hello " + name)` | Concatenates "Hello " with the user's input and displays it. |

### Sample Execution:

```
Enter Your Name: Varun
Hello Varun
```

---

## 2. ⚠️ Default Data Type is ALWAYS String

This is the most important concept — often asked in exams and interviews.

> **No matter what the user enters (number, float, boolean, character), the `input()` function ALWAYS returns a `str` (String) type.**

### Proof with Example:

```python
name = input("Enter Something: ")
print(type(name))
```

| User Enters | Stored As | Type Output |
| :--- | :--- | :--- |
| `Varun` | `"Varun"` | `<class 'str'>` |
| `10` | `"10"` | `<class 'str'>` |
| `10.5` | `"10.5"` | `<class 'str'>` |
| `True` | `"True"` | `<class 'str'>` |

> Even if you enter a number like `10`, it is stored as the string `"10"`, NOT as an integer.

---

## 3. 🚫 The Problem This Creates

If you try to do math with a string input, Python will throw an error.

### Wrong Code:
```python
num = input("Enter a Number: ")
print(num + 2)
```

### Why It Fails:

| What Happens | Explanation |
| :--- | :--- |
| User enters `10` | Stored as string `"10"` |
| `num + 2` attempted | `"10" + 2` — Cannot add string and integer |
| Error | `TypeError: can only concatenate str (not "int") to str` |

You expected `12`, but got an error!

---

## 4. ✅ The Solution: Type Casting

To fix this, you must **convert** (type cast) the input to the desired data type.

### 4.1 Convert to Integer (`int`)

```python
num = int(input("Enter a Number: "))
print(num + 2)
```

| Input | After Casting | `num + 2` Result |
| :--- | :--- | :--- |
| `10` | `10` (int) | `12` |

---

### 4.2 Convert to Float (`float`)

```python
num = float(input("Enter a Number: "))
print(num + 2)
```

| Input | After Casting | `num + 2` Result |
| :--- | :--- | :--- |
| `10` | `10.0` (float) | `12.0` |
| `10.5` | `10.5` (float) | `12.5` |

> Float always shows decimal values.

---

### 4.3 Convert to Boolean (`bool`)

```python
val = bool(input("Enter Something: "))
print(val)
print(type(val))
```

**Boolean Conversion Rules:**

| Input Given | Converted To | Reason |
| :--- | :--- | :--- |
| Any non-empty value (e.g., `10`, `hello`, `True`) | `True` | Default for any non-empty input |
| Empty input (just press Enter without typing) | `False` | Empty string is considered `False` |

---

## 5. 📊 Summary Table

| Desired Type | Syntax | Example |
| :--- | :--- | :--- |
| **String** (default) | `input("Prompt: ")` | `name = input("Name: ")` |
| **Integer** | `int(input("Prompt: "))` | `age = int(input("Age: "))` |
| **Float** | `float(input("Prompt: "))` | `price = float(input("Price: "))` |
| **Boolean** | `bool(input("Prompt: "))` | `flag = bool(input("Continue? "))` |

---

## 6. 📝 Key Takeaways

| Rule | Details |
| :--- | :--- |
| **Default Type** | `input()` always returns **String** |
| **Mathematical Operations** | Won't work on string input — causes `TypeError` |
| **Type Casting** | Use `int()`, `float()`, `bool()` to convert input |
| **Exam Tip** | This is a favourite interview and exam question — never forget the default string behavior |

---

**Now you can take any type of input from the user correctly!** 🎯
