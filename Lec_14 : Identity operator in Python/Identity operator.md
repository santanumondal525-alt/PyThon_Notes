# 🆔 Identity Operators in Python
<sub>📺 <a href="https://youtu.be/jfV5BnUPD6I?si=gIX8YSjaXIcYNLDE">Video Link</a></sub>

### Introduction

As the name suggests, **Identity Operators** check whether two things are **identical** — not just in value, but in **memory location**.

> Identity operators are used to check whether two **objects** have the **same memory location (ID)**.

---

## 1. 🎯 The Two Identity Operators

| Operator | Keyword | Meaning |
| :---: | :--- | :--- |
| `is` | Identity | Returns `True` if both objects share the **same memory location** |
| `is not` | Not Identity | Returns `True` if both objects have **different memory locations** |

---

## 2. 🧠 Understanding Objects in Python

In Python, **everything is an object** (because Python is Object-Oriented).

```python
x = 10
```

| Component | What It Is |
| :--- | :--- |
| **Object Value** | `10` — the actual data |
| **Object Name/Tag** | `x` — the variable name pointing to the data |
| **Memory Location (ID)** | Where `10` is stored in memory (e.g., location `1000`) |

> The **identity** of an object is its **memory location**, not its value.

---

## 3. 💡 How Memory Works in Python (Key Difference from C/C++)

### In C / C++:
```c
int x = 10;
int a = 10;
```
- Two **separate memory locations** are created
- `x` and `a` are stored independently

### In Python:
```python
x = 10
a = 10
```
- Python sees: same value (`10`), same type (`int`)
- Python **does NOT create a new memory location** for `a`
- Instead, `a` **points to the same memory location** as `x`

| Language | Memory Usage |
| :--- | :--- |
| C / C++ | Creates separate memory for each variable |
| **Python** | Reuses the same memory location for same values (memory optimization) |

---

## 4. 📝 Example: `is` Operator

```python
x = 10
a = 10
print(x is a)       # True
```

### Why `True`?

| Object | Value | Memory Location |
| :--- | :---: | :--- |
| `x` | `10` | `1000` (example) |
| `a` | `10` | `1000` (same!) |

> Both `x` and `a` point to the **same memory location**, so `x is a` returns `True`.

---

## 5. 📝 Example: When Values Differ

```python
x = 10
a = 20
print(x is a)       # False
```

| Object | Value | Memory Location |
| :--- | :---: | :--- |
| `x` | `10` | `1000` |
| `a` | `20` | `2000` |

> Different values → different memory locations → `False`.

---

## 6. 📝 Example: Multiple Assignments Point to Same Location

```python
x = 10
c = x    # Assign x's value to c
```

| Object | Memory Location |
| :--- | :--- |
| `x` → `10` | `1000` |
| `c` → `10` | `1000` (same! `c` points to the same location) |

```python
print(x is c)       # True
print(a is c)       # False (a = 20 is at a different location)
```

---

## 7. 🔍 Checking Object IDs

You can verify memory locations using the `id()` function.

```python
x = 10
a = 10
c = x

print(id(x))    # 140725678901234 (example)
print(id(a))    # 140725678901234 (same!)
print(id(c))    # 140725678901234 (same!)

print(x is a)   # True
print(x is c)   # True
```

> **All three share the same ID (memory location)!**

---

## 8. 📊 Where `is` Works vs Where It Doesn't

| Data Type | Same Value? | Same Memory Location? | `is` Result |
| :--- | :---: | :---: | :---: |
| **Integer** (small values) | ✅ Yes | ✅ Yes | `True` |
| **String** (same string) | ✅ Yes | ✅ Yes | `True` |
| **None** | ✅ Yes | ✅ Yes | `True` |
| **List / Tuple / Dict** (same values) | ✅ Yes | ❌ No (different objects) | `False` |

---

## 9. 🚫 Important Exception: Collection Data Types

For **collections** like `list`, `tuple`, `dict`, even if they have the **same values**, Python allocates **different memory locations**.

### Example with Lists:

```python
list1 = [10, 20, 30]
list2 = [10, 20, 30]

print(list1 == list2)    # True  (values are equal)
print(list1 is list2)    # False (different memory locations!)
```

### Why?

| Object | Values | Memory Location |
| :--- | :--- | :--- |
| `list1` | `[10, 20, 30]` | Location `3000` |
| `list2` | `[10, 20, 30]` | Location `4000` (different!) |

> **`==` checks value equality. `is` checks memory location identity.**

---

## 10. 🧪 Verifying with `id()`

```python
list1 = [10, 20, 30]
list2 = [10, 20, 30]

print(id(list1))    # 234567890123 (example)
print(id(list2))    # 234567890456 (different!)
```

| Object | ID (Memory) | `is` Result |
| :--- | :--- | :---: |
| `list1` | `...0123` | |
| `list2` | `...0456` | `False` ❌ |

---

## 11. 📝 The `is not` Operator

`is not` is the **opposite** of `is`.

```python
x = 10
a = 20
print(x is not a)       # True (different memory locations)

list1 = [10, 20, 30]
list2 = [10, 20, 30]
print(list1 is not list2)   # True (different memory locations)
```

---

## 12. 📊 Summary: `is` vs `==`

| Feature | `is` (Identity) | `==` (Equality) |
| :--- | :--- | :--- |
| **What it checks** | Memory location (ID) | Value |
| **Returns True if** | Same memory location | Same value |
| **For `[10, 20]` and `[10, 20]`** | `False` | `True` |

---

## 13. 📊 Complete Behavior Table

| Scenario | Example | `is` Result | Reason |
| :--- | :--- | :---: | :--- |
| Same integer value | `x=10; a=10` | `True` ✅ | Same memory (optimization) |
| Different integer value | `x=10; a=20` | `False` ❌ | Different memory |
| Assignment from same variable | `x=10; c=x` | `True` ✅ | Points to same location |
| Same string value | `"hello"` and `"hello"` | `True` ✅ | Same memory |
| Same list values | `[10,20]` and `[10,20]` | `False` ❌ | Different objects created |
| `None` type | `a=None; b=None` | `True` ✅ | Same memory |
| Different type, same value | `10` and `"10"` | `False` ❌ | Different types, different memory |

---

## 14. 📝 Key Takeaways

| Point | Details |
| :--- | :--- |
| **2 Operators** | `is` and `is not` |
| **Checks Identity** | Memory location (ID), NOT value |
| **`is` vs `==`** | `is` = same memory; `==` = same value |
| **Integers & Strings** | Same values share same memory (optimization) |
| **Collections** (list, tuple, dict) | Even same values get **different** memory locations |
| **None** | Always shares the same memory location |
| **Use `id()`** | To check the actual memory address |
| **Exam Tip** | Difference between `is` and `==`, and list behavior with `is` are common interview questions |

---

**Now you understand Identity Operators completely!** 🆔
