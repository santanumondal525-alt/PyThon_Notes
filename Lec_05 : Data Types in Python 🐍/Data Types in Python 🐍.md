# 📊 Data Types in Python
<sub>📺 <a href="https://youtu.be/k7OTRmVrw7w?si=PVU9Gx4Ts00Mv5FB">Video Link</a></sub>

### Introduction

In the last video, we learned that **variables are used to store data**. But what **type** of data are we storing? That depends on the **Data Type**.

| In C / C++ / Java | In Python |
| :--- | :--- |
| You must **explicitly declare** the data type: `int a = 10;` | Python is **dynamically typed** — it automatically detects the type at **runtime** based on the value you assign. |

> You don't need to mention the type. Python figures it out automatically.

---

## 1. 🗂️ Data Types in Python

| Category | Data Types Included |
| :--- | :--- |
| **Numeric** 🔢 | `int`, `float`, `complex` |
| **Text** 📝 | `str` |
| **Boolean** ✅ | `bool` |
| **Sequence** 📋 | `list`, `tuple`, `range` |
| **Mapping** 🗺️ | `dict` |
| **Set** 🎯 | `set`, `frozenset` |
| **Binary** 💾 | `bytes`, `bytearray`, `memoryview` |
| **None** 🚫 | `NoneType` |

---

## 2. 🔢 Numeric Types

### 2.1 Integer (`int`)

Whole numbers without decimal points.

```python
age = 32
print(type(age))    # Output: <class 'int'>
```

### 2.2 Float (`float`)

Numbers with decimal points.

```python
weight = 72.5
print(type(weight))    # Output: <class 'float'>
```

### 2.3 Complex (`complex`)

Imaginary numbers (rarely used). Written with `j` suffix.

```python
c = 1 + 2j
print(type(c))    # Output: <class 'complex'>
```

---

## 3. 📝 Text Type (`str`)

Used for storing names, addresses, any text.

```python
name = "Varun"
print(type(name))    # Output: <class 'str'>
```

> String can be written in **single quotes `' '`** or **double quotes `" "`**. Both work perfectly.

---

## 4. ✅ Boolean Type (`bool`)

Only two possible values: `True` or `False`.

```python
is_valid = True
print(type(is_valid))    # Output: <class 'bool'>
```

> **Important:** `True` and `False` must have **capital first letters** (`T` and `F`).

---

## 5. 📋 Sequence Types

### 5.1 List (`list`)

- Ordered collection of items
- **Mutable** — can be changed, modified, inserted, deleted
- Written with **square brackets `[ ]`**

```python
list1 = [10, 20, 30, "Varun"]
print(list1)            # Output: [10, 20, 30, 'Varun']
print(type(list1))      # Output: <class 'list'>
```

### 5.2 Tuple (`tuple`)

- Ordered collection of items
- **Immutable** — once created, cannot be changed
- Written with **parentheses `( )`**

```python
tup1 = (10, 20, 30)
print(type(tup1))       # Output: <class 'tuple'>
```

### 5.3 Range (`range`)

- Represents a sequence of numbers
- Used for iterations

```python
r = range(1, 5)
print(r)                # Output: range(1, 5)
print(type(r))          # Output: <class 'range'>
```

---

## 6. 🗺️ Mapping Type (`dict`)

- Stores data in **key-value pairs**
- Like a real dictionary: word (key) → meaning (value)
- Written with **curly braces `{ }`**, using `key : value` format

```python
dict1 = {
    "name": "Varun",
    "age": 32,
    "city": "Chandigarh"
}
print(dict1)                    # Output: {'name': 'Varun', 'age': 32, 'city': 'Chandigarh'}
print(dict1["city"])            # Output: Chandigarh
print(type(dict1))              # Output: <class 'dict'>
```

---

## 7. 🎯 Set Types

### 7.1 Set (`set`)

- Collection of **unique**, **unordered** items
- No indexing — cannot access by position
- Written with **curly braces `{ }`** (without key-value pairs)

```python
set1 = {10, 20, 30, 10}
print(set1)             # Output: {10, 20, 30} (duplicates removed automatically)
```

### 7.2 Frozenset (`frozenset`)

- Same as set, but **immutable** (cannot be changed after creation)

---

## 8. 💾 Binary Types

| Type | Description |
| :--- | :--- |
| `bytes` | **Immutable** — cannot change after creation |
| `bytearray` | **Mutable** — can change, insert, delete |
| `memoryview` | Memory view of binary data |

### Example:

```python
b = bytes([65, 66, 97])
print(b)                # Output: b'ABa'
```

| ASCII Code | Character |
| :--- | :--- |
| 65 | A (Capital) |
| 66 | B (Capital) |
| 97 | a (Small) |

> **Key Difference:** `bytes` is immutable, `bytearray` is mutable.

---

## 9. 🚫 None Type (`NoneType`)

- Represents **no value** or **empty** value
- Like `null` in other languages

```python
x = None
print(type(x))    # Output: <class 'NoneType'>
```

> **Important:** `None` must have a **capital N**.

---

## 10. 🔍 How to Check Data Type

Use the `type()` function:

```python
x = 10
print(type(x))    # Output: <class 'int'>
```

---

## 11. 📊 Complete Summary Table

| Data Type | Category | Example | Mutable? |
| :--- | :--- | :--- | :---: |
| `int` | Numeric | `x = 10` | No |
| `float` | Numeric | `x = 10.5` | No |
| `complex` | Numeric | `x = 1 + 2j` | No |
| `str` | Text | `x = "Hello"` | No |
| `bool` | Boolean | `x = True` | No |
| `list` | Sequence | `x = [1, 2, 3]` | ✅ Yes |
| `tuple` | Sequence | `x = (1, 2, 3)` | ❌ No |
| `range` | Sequence | `x = range(1, 5)` | No |
| `dict` | Mapping | `x = {"a": 1}` | ✅ Yes |
| `set` | Set | `x = {1, 2, 3}` | ✅ Yes |
| `frozenset` | Set | `x = frozenset({1, 2})` | ❌ No |
| `bytes` | Binary | `x = b"Hello"` | ❌ No |
| `bytearray` | Binary | `x = bytearray(5)` | ✅ Yes |
| `NoneType` | None | `x = None` | — |

---

## 12. 📝 Key Takeaways

| Point | Details |
| :--- | :--- |
| **Dynamic Typing** | Python auto-detects data type at runtime |
| **Check Type** | Use `type()` function |
| **Mutable vs Immutable** | Lists, Dicts, Sets = Mutable; Tuples, Strings, Bytes = Immutable |
| **Capitalization** | `True`, `False`, `None` — first letter must be capital |
| **Exam Tip** | Know the difference between mutable and immutable types, and the categories of data types |

---

**Now you know all Data Types in Python!** 📊
