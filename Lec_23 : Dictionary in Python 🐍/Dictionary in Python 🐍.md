# 📖 Python Dictionary
<sub>📺 <a href="https://youtu.be/brnsFCa7npc?si=tvhFSh1oG5yDkkMl">Video Link</a></sub>
## 🔹 What is a Dictionary?

> A **dictionary** is a collection that stores data in **key-value pairs**.

✅ It is one of the most important data types in Python for handling **unstructured data**.

---

## 🔹 Why Use a Dictionary? – The Problem It Solves

In real life, data is often **unstructured**. You need to store related information together.

**Example:** A student record – Roll number, Name, Address, Marks.

| Key (Unique) | Value (Can be duplicate) |
|--------------|--------------------------|
| 1 | "Amit" |
| 2 | "Varun" |
| 3 | "Neha" |

> ✅ Dictionary allows you to store such **related data** in a single structure.

---

## 🔹 Dictionary vs Other Data Structures

| Data Structure | Format | Search Speed |
|----------------|--------|---------------|
| List | Indexed by position (0,1,2...) | Slow (sequential search) |
| Dictionary | Key-value pair | **Very fast** (direct access via key) |

> 💡 Dictionaries are similar to **Hash Tables** – they use hashing for fast lookups.

---

## 🔹 Properties of a Dictionary

| Property | Meaning |
|----------|---------|
| **Unordered** | Items are not stored in any specific order (before Python 3.7) |
| **Mutable** | Can add, remove, or change values after creation |
| **Keys are unique** | Duplicate keys are **not allowed** |
| **Values can duplicate** | Multiple keys can have same value |
| **Keys must be immutable** | Keys can be numbers, strings, tuples (not lists) |
| **Fast searching** | Uses hashing – O(1) average time complexity |

---

## 🔹 How to Create a Dictionary

### 1. Empty Dictionary
```python
my_dict = {}
print(type(my_dict))   # <class 'dict'>
```

### 2. Dictionary with Key-Value Pairs
```python
student = {
    1: "Amit",
    2: "Varun",
    3: "Neha"
}
print(student)   # {1: 'Amit', 2: 'Varun', 3: 'Neha'}
```

### 3. Dictionary with Mixed Data Types
```python
info = {
    "name": "Varun",
    "age": 25,
    "city": "Delhi"
}
print(info)   # {'name': 'Varun', 'age': 25, 'city': 'Delhi'}
```

> ✅ **Syntax:** `{key1: value1, key2: value2, ...}`

---

## 🔹 Important Rules for Keys

| Allowed as Key | Not Allowed as Key |
|----------------|---------------------|
| Numbers (`int`, `float`) | Lists (mutable) |
| Strings | Dictionaries (mutable) |
| Tuples (immutable) | Sets (mutable) |
| Booleans | |

> 🔥 **Key must be immutable and unique.**

---

## 🔹 Accessing Values from a Dictionary

### Method 1: Using Square Brackets `[]`
```python
student = {1: "Amit", 2: "Varun", 3: "Neha"}
print(student[2])   # Output: Varun
```

⚠️ If key doesn't exist → `KeyError`

### Method 2: Using `get()` method (safer)
```python
print(student.get(2))   # Output: Varun
print(student.get(5))   # Output: None (no error)
print(student.get(5, "Not Found"))   # Output: Not Found
```

> ✅ `get()` is preferred because it doesn't throw an error.

---

## 🔹 Why Dictionaries are Super Fast – Hashing Concept 🚀

### Normal Search (List/Tuple) – O(n)
- Searches **sequentially** one by one
- May need to check all elements

### Dictionary Search – O(1) (constant time)
- Uses a **mathematical function (hash function)** to calculate the exact location
- Directly jumps to that location

**Example:**
- Key `15` → hash function `15 % 10 = 5` → directly go to index `5`
- No need to search through all items!

> 💡 This is why dictionaries are used in **real-life applications** like databases, caches, and lookups.

---

## 🔹 Basic Dictionary Operations (Overview)

| Operation | Syntax | Example |
|-----------|--------|---------|
| Create | `d = {}` | `d = {"name": "Varun"}` |
| Access | `d[key]` or `d.get(key)` | `d["name"]` |
| Add/Update | `d[key] = value` | `d["age"] = 25` |
| Delete | `del d[key]` | `del d["age"]` |
| Check key | `key in d` | `"name" in d` → True |
| Length | `len(d)` | `len(d)` |

---

## 📊 Quick Reference Table

| Concept | Example | Output |
|---------|---------|--------|
| Create dict | `d = {1:"A", 2:"B"}` | `{1:'A',2:'B'}` |
| Access by key | `d[1]` | `'A'` |
| Safe access | `d.get(3)` | `None` |
| Add new pair | `d[3] = "C"` | `{1:'A',2:'B',3:'C'}` |
| Update value | `d[1] = "Z"` | `{1:'Z',2:'B',3:'C'}` |
| Delete key | `del d[2]` | `{1:'Z',3:'C'}` |
| Check key | `1 in d` | `True` |
| Length | `len(d)` | `2` |

---

## ✅ Important Points for Exams/Interviews

1. **Keys must be unique and immutable** (strings, numbers, tuples – but not lists).
2. **Values can be any data type** and can be duplicated.
3. **Dictionaries are unordered** (in older Python versions; Python 3.7+ preserves insertion order).
4. **Dictionaries are mutable** – you can change, add, or remove items.
5. **`get()` method** is safer than direct access (`[]`).
6. **Hashing** makes dictionary search **very fast (O(1))** compared to lists (O(n)).
7. **Real-life use:** Storing student records, phonebooks, caches, JSON data.

---

## 🧪 Practice Examples (Try Yourself)

```python
# Create a dictionary
student = {"roll": 101, "name": "Varun", "city": "Mumbai"}

print(student["name"])           # ?
print(student.get("city"))       # ?
print(student.get("age", 18))    # ?

# Add new key-value pair
student["age"] = 22
print(student)                   # ?

# Update existing value
student["city"] = "Pune"
print(student)                   # ?

# Check if key exists
print("roll" in student)         # ?
print("marks" in student)        # ?

# Get length
print(len(student))              # ?
```

**Answers:**
- `"Varun"`
- `"Mumbai"`
- `18`
- `{'roll':101, 'name':'Varun', 'city':'Mumbai', 'age':22}`
- `{'roll':101, 'name':'Varun', 'city':'Pune', 'age':22}`
- `True`
- `False`
- `4`

---

## 🎯 Final Pro Tips

| You want to... | Use this |
|----------------|----------|
| Store related data | Dictionary |
| Fast lookup by ID/name | Dictionary key |
| Safe access (no error) | `.get()` method |
| Check if key exists | `key in dict` |
| Add/update value | `dict[key] = value` |
| Remove a key | `del dict[key]` |

---

## 🚀 Summary

> **Dictionary = {key1: value1, key2: value2, ...}**  
> - Stores data in **key-value pairs**  
> - **Keys are unique and immutable**  
> - **Values can be anything** (duplicates allowed)  
> - **Mutable** (can change after creation)  
> - **Very fast** due to hashing (O(1) lookup)  
> - Used in real life for phonebooks, student records, JSON, caches, etc.

---

Happy Coding! 🐍📖  
You are now ready to answer any dictionary-related question in exams and interviews. 💪
