# 📊 Data Types in Python
<sub>📺 <a href="https://youtu.be/JXQ_lFGM0bg?si=AXKyLg98lvNnNTqA">Video Link</a></sub>

### Why Data Types are Important

Whenever we store data in different variables, knowing their **type** is very important because:

- Data retrieval depends on the data type
- Memory allocation depends on the data type
- Operations you can perform depend on the data type

> Data Types is one of the most important topics in Python.

---

## 1. 🔄 Two Major Categories: Mutable vs Immutable

This is a fundamental concept in Python.

| Category | Meaning | Can Change After Creation? | Also Called |
| :--- | :--- | :---: | :--- |
| **Mutable** 🔧 | Values can be changed after creation | ✅ Yes | Read & Write |
| **Immutable** 🔒 | Values cannot be changed after creation | ❌ No | Read-Only |

### Real-Life Analogy:

| Concept | Mutable Example | Immutable Example |
| :--- | :--- | :--- |
| **Memory** | If memory location `#001` has value `20`, you can change it to `30` at the same location | Once created at a location, changing value creates a **new memory location** — memory usage doubles |

---

## 2. 📊 Classification of Data Types

| Category | Mutable? | Data Types Included |
| :--- | :---: | :--- |
| **Mutable** | ✅ | `list`, `set`, `dict` |
| **Immutable** | ❌ | `int`, `float`, `str`, `tuple`, `frozenset`, `bytes` |

---

## 3. 📋 Detailed Breakdown of Major Data Types

### 3.1 String (`str`) — Immutable ❌

- **Ordered** ✅ — maintains insertion order
- **Indexed** ✅ — can access via index
- **Immutable** ❌ — cannot change after creation
- Stores text data

```python
name = "Varun"
# name[0] = "B"   ❌ Not allowed — strings are immutable
```

> **Ordered does NOT mean Sorted.** Ordered means Python maintains the sequence you created. For sorting, you need to use the `sort()` function separately.

---

### 3.2 List (`list`) — Mutable ✅

- **Ordered** ✅
- **Indexed** ✅
- **Mutable** ✅ — can add, remove, change items
- **Allows Duplicates** ✅
- Written with square brackets `[ ]`

```python
my_list = [10, 20, 30, 10]    # Duplicate 10 is allowed
my_list[0] = 100              # ✅ Allowed — lists are mutable
```

| Feature | List |
| :--- | :--- |
| Can store mixed data types? | ✅ Yes — integers, strings, booleans, all can mix |
| Analogy | **Pencil Box** — contains pens, pencils, erasers, sharpeners (mixed items) |

---

### 3.3 Tuple (`tuple`) — Immutable ❌

- **Ordered** ✅
- **Indexed** ✅
- **Immutable** ❌ — cannot change after creation
- **Allows Duplicates** ✅
- Written with parentheses `( )`

```python
my_tuple = (10, 20, 30)
# my_tuple[0] = 100   ❌ Not allowed — tuples are immutable
```

| Feature | List | Tuple |
| :--- | :---: | :---: |
| Mutable | ✅ Yes | ❌ No |
| Speed | Slower | Faster (due to immutability) |
| Use Case | Data that may change | Fixed data that shouldn't change |

> **Key Difference:** Lists are mutable, Tuples are immutable. That's the major and often the only difference asked in interviews.

---

### 3.4 Set (`set`) — Mutable ✅

- **Unordered** ❌ — no index, no fixed order
- **Unique Values Only** ❌ — duplicates are automatically removed
- **Mutable** ✅ — can add/remove items
- Written with curly braces `{ }`

```python
my_set = {10, 20, 30, 10}
print(my_set)    # Output: {10, 20, 30} — duplicate 10 removed automatically
```

| Feature | Set |
| :--- | :--- |
| Duplicates Allowed? | ❌ No — stores only unique values |
| Indexed? | ❌ No — cannot access by index |
| Can store lists inside? | ❌ No — lists cannot be elements of a set |

---

### 3.5 Dictionary (`dict`) — Mutable ✅

- **Key-Value Pairs** — stores data as `key : value`
- **Keys must be unique** — values can be duplicated
- **Mutable** ✅
- Written with curly braces `{ }` with `key : value` format

```python
my_dict = {
    "name": "Varun",
    "age": 32,
    "city": "Chandigarh"
}
```

| Feature | Dictionary |
| :--- | :--- |
| Structure | Key : Value pairs |
| Best For | Storing huge amounts of structured data |
| Analogy | **School Bag** — contains geometry box, lunch box, books (everything organized) |

> **Real-life use:** Used heavily in handling **unstructured data** (like NoSQL databases, JSON data) where each entity has unique keys.

---

## 4. 🏫 Real-Life Analogies for Quick Recall

| Data Type | Analogy | What it Holds |
| :--- | :--- | :--- |
| **String** | Single item | Just text |
| **List** | Pencil Box ✏️ | Mixed items — can be changed |
| **Tuple** | Geometry Box 📐 | Fixed set of items — cannot be changed |
| **Set** | Unique collection | Only distinct items — no repeats |
| **Dictionary** | School Bag 🎒 | Everything inside, organized by labels (keys) |

---

## 5. 📊 Complete Comparison Table

| Data Type | Ordered? | Indexed? | Mutable? | Duplicates? | Syntax |
| :--- | :---: | :---: | :---: | :---: | :--- |
| **String** | ✅ | ✅ | ❌ | ✅ | `" "` or `' '` |
| **List** | ✅ | ✅ | ✅ | ✅ | `[ ]` |
| **Tuple** | ✅ | ✅ | ❌ | ✅ | `( )` |
| **Set** | ❌ | ❌ | ✅ | ❌ | `{ }` |
| **Dictionary** | ✅ (Python 3.7+) | Keys only | ✅ | Keys: ❌, Values: ✅ | `{key: value}` |

---

## 6. 📝 Key Takeaways

| Point | Details |
| :--- | :--- |
| **Two Categories** | Mutable (can change) and Immutable (cannot change) |
| **Mutable Types** | `list`, `set`, `dict` |
| **Immutable Types** | `int`, `float`, `str`, `tuple` |
| **Ordered vs Sorted** | Ordered = maintains sequence; Sorted = arranged in ascending/descending (needs `sort()`) |
| **Set** | Unordered, unique values only, duplicates auto-removed |
| **Dictionary** | Key-value pairs, best for huge structured/unstructured data |
| **Interview Tip** | Difference between List vs Tuple (mutability) and all Mutable vs Immutable concepts are favorite questions |

---

**Now you know everything about Data Types in Python!** 📊
