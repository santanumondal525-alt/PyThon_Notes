# 🔍 Membership Operators in Python
<sub>📺 <a href="https://youtu.be/NXwpH79BUb4?si=KJAlx9CjsYMIShu1">Video Link</a></sub>

### Introduction

As the name suggests, **Membership Operators** check whether you are a **member** of a particular group or not.

| Real-Life Analogy |
| :--- |
| When you apply for an exam and **log in successfully** → you are a member ✅ |
| If you are **not registered** → access is denied ❌ |

> Membership operators test whether a **specific value or item is present** within a **sequence** (like a string, list, tuple, dictionary, or any collection).

---

## 1. 🎯 The Two Membership Operators

| Operator | Keyword | Meaning |
| :---: | :--- | :--- |
| `in` | Membership | Returns `True` if the value **is found** in the sequence |
| `not in` | Not Membership | Returns `True` if the value **is NOT found** in the sequence |

---

## 2. 📝 Basic Syntax & Logic

```python
value in sequence      # True if value exists in the sequence
value not in sequence  # True if value does NOT exist in the sequence
```

| Operator | If Value Exists | If Value Does NOT Exist |
| :---: | :---: | :---: |
| `in` | `True` ✅ | `False` ❌ |
| `not in` | `False` ❌ | `True` ✅ |

---

## 3. 📝 Example 1: Checking in a List

```python
list1 = [1, 2, 3, 4, 5]

print(1 in list1)       # True  (1 is present in the list)
print(10 in list1)      # False (10 is not in the list)
print(10 not in list1)  # True  (10 is indeed not in the list)
print(1 not in list1)   # False (1 is in the list)
```

| Expression | Meaning | Result |
| :--- | :--- | :---: |
| `1 in list1` | Is 1 present in list1? | `True` ✅ |
| `10 in list1` | Is 10 present in list1? | `False` ❌ |
| `10 not in list1` | Is 10 absent from list1? | `True` ✅ |
| `1 not in list1` | Is 1 absent from list1? | `False` ❌ |

---

## 4. 📝 Example 2: Checking in a String

```python
text = "Hello World"

print("H" in text)          # True
print("hello" in text)      # False (case-sensitive)
print("World" in text)      # True
print("Python" not in text) # True
```

> Membership works perfectly with **strings** too — it checks for substrings.

---

## 5. 📝 Example 3: Checking in a Dictionary

```python
student = {"name": "Varun", "age": 25, "city": "Delhi"}

print("name" in student)        # True (checks KEYS, not values)
print("Varun" in student)       # False (searches keys, not values)
print("Varun" in student.values())  # True (explicitly checking values)
```

> For dictionaries, `in` checks **keys** by default. Use `.values()` to check values.

---

## 6. 🎯 Real-Life Example: OTT Platform Membership Check

Let's create a simple membership verification system like an OTT platform (Netflix, Hotstar, etc.).

```python
registered_users = ["Varun", "Tarun", "Amit", "Priya", "Sneha"]

name = input("Enter Your Name: ")

if name in registered_users:
    print("Access Granted! Welcome,", name)
else:
    print("Access Denied! You are not registered.")
```

### Sample Run 1:
```
Enter Your Name: Varun
Access Granted! Welcome, Varun
```

| Input | In List? | Output |
| :--- | :---: | :--- |
| `Varun` | ✅ Yes | "Access Granted! Welcome, Varun" |

### Sample Run 2:
```
Enter Your Name: Rahul
Access Denied! You are not registered.
```

| Input | In List? | Output |
| :--- | :---: | :--- |
| `Rahul` | ❌ No | "Access Denied! You are not registered." |

---

## 7. 📊 Where Can You Use Membership Operators?

| Data Type | Works With? | Example |
| :--- | :---: | :--- |
| **String** | ✅ Yes | `"a" in "apple"` |
| **List** | ✅ Yes | `5 in [1, 2, 5]` |
| **Tuple** | ✅ Yes | `3 in (1, 2, 3)` |
| **Set** | ✅ Yes | `10 in {10, 20}` |
| **Dictionary** | ✅ Yes (keys only by default) | `"key" in dict` |
| **Range** | ✅ Yes | `5 in range(1, 10)` |

---

## 8. 📊 Summary Table

| Operator | Returns `True` When | Returns `False` When | Example |
| :---: | :--- | :--- | :--- |
| `in` | Value **is found** in sequence | Value **is not found** | `5 in [1,2,5]` → `True` |
| `not in` | Value **is NOT found** in sequence | Value **is found** | `5 not in [1,2,5]` → `False` |

---

## 9. 📝 Key Takeaways

| Point | Details |
| :--- | :--- |
| **2 Operators** | `in` and `not in` |
| **Purpose** | Check if a value exists in a sequence |
| **Returns** | Always a Boolean (`True` or `False`) |
| **Works With** | Strings, Lists, Tuples, Sets, Dictionaries (keys), Ranges |
| **Dictionary Note** | `in` checks **keys** by default; use `.values()` for values |
| **Real-Life Use** | Login checks, access control, searching, validation |
| **Case Sensitive** | String checks are case-sensitive (`"A"` ≠ `"a"`) |
| **Exam Tip** | Know what `in` returns for dictionaries (keys vs values) |

---

**Now you understand Membership Operators completely!** 🔍
