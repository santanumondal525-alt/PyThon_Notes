# 📋 Python Lists
<sub>📺 <a href="https://youtu.be/Icw4cLTtKh4?si=rZ8cJQ_UWBOPUFDA">Video Link</a></sub>

## 🔹 What is a List?

> A **list** is a collection that can hold **multiple items of different data types** at the same time.

✅ Lists are one of the **most versatile data types** in Python.

---

## 🔹 Why Lists?

In real life, data is not always of the same type. For example:

| Field | Data Type |
|-------|-----------|
| Student ID | Integer (e.g., 101) |
| Name | String (e.g., "Varun") |
| Marks | Float (e.g., 85.5) |

> A **list** allows you to store **all these together** in one place.

---

## 🔹 List vs Array vs Table

| Data Structure | Can mix data types? | Dimensions |
|----------------|---------------------|-------------|
| Array (C/C++/Java) | ❌ No (same type only) | 1D or 2D |
| Table (Database) | ✅ Yes | 2D (rows & columns) |
| **Python List** | ✅ Yes | 1D (but can have nested lists) |

> 💡 In Python, a list can hold **integers, floats, strings, booleans, even other lists**!

---

## 🔹 How to Create a List

Use **square brackets `[]`** and separate items with commas.

```python
list1 = [10, 5.5, "Hello", True]
print(list1)   # Output: [10, 5.5, 'Hello', True]
```

✅ This list contains: `int`, `float`, `str`, `bool`

---

## 🔹 Properties of Lists

| Property | Meaning |
|----------|---------|
| **Ordered** | Items have a fixed position (index) |
| **Mutable** | Can change, add, or remove items after creation |
| **Heterogeneous** | Can hold different data types |
| **Indexed** | Access items by index (starts at 0) |
| **Nested** | Can contain other lists inside |

---

## 🔹 Indexing in Lists (Positive)

Index starts at **0** for the first element.

```python
list1 = [10, 5.5, "Hello", True]
# Index:  0    1     2       3
```

| Access | Code | Output |
|--------|------|--------|
| First element | `list1[0]` | `10` |
| Second element | `list1[1]` | `5.5` |
| Third element | `list1[2]` | `"Hello"` |
| Fourth element | `list1[3]` | `True` |

---

## 🔹 Negative Indexing (from Right)

Negative index starts at **-1** for the last element.

```python
list1 = [10, 5.5, "Hello", True]
# Negative: -4   -3    -2     -1
```

| Access | Code | Output |
|--------|------|--------|
| Last element | `list1[-1]` | `True` |
| Second last | `list1[-2]` | `"Hello"` |
| Third last | `list1[-3]` | `5.5` |
| First element | `list1[-4]` | `10` |

> 💡 **Important:** `list1[-1]` is always the last element.

---

## 🔹 Length of List & Index Range

If a list has **n** elements:
- Positive indexes: `0` to `n-1`
- Negative indexes: `-1` to `-n`

```python
list1 = [10, 5.5, "Hello", True]
print(len(list1))   # Output: 4

# Last element using length
print(list1[len(list1)-1])   # Output: True (same as list1[-1])
```

> ⚠️ Trying to access an index beyond range → `IndexError`

---

## 🔹 Lists are Mutable – You Can Change Them ✏️

```python
list1 = [10, 5.5, "Hello", True]
list1[2] = "Good"   # Change third element
print(list1)        # Output: [10, 5.5, 'Good', True]
```

> ✅ Unlike strings, lists **allow modification** after creation.

---

## 🔹 Nested Lists – List Inside Another List 📦

```python
nested_list = [[1, 2, 3], ["a", "b", "c"], [True, False]]
print(nested_list[0])    # Output: [1, 2, 3]
print(nested_list[1][2]) # Output: 'c' (second list, third element)
```

> 💡 Used for representing **tables, matrices, or grouped data**.

---

## 🔹 Real-Life Use Case Example 🛒

When you shop online, your data is stored like this:

```python
customer = [101, "Varun", "varun@email.com", 2500.50]
# ID, Name, Email, Bill Amount
```

✅ Different data types – all stored in **one list**.

---

## 📊 Quick Reference Table

| Operation | Code | Example (list1 = [10, 5.5, "Hello", True]) |
|-----------|------|---------------------------------------------|
| Create list | `list1 = [...]` | `[10, 5.5, "Hello", True]` |
| Access element | `list1[index]` | `list1[2]` → `"Hello"` |
| Negative index | `list1[-1]` | `True` |
| Change element | `list1[index] = new` | `list1[2] = "Good"` |
| Get length | `len(list1)` | `4` |
| Nested list access | `list1[i][j]` | Access inner list elements |

---

## ✅ Important Points for Exams/Interviews

1. **List is mutable** – can be changed after creation.
2. **List is ordered** – maintains the sequence of elements.
3. **List can hold mixed data types** – unlike arrays.
4. **Index starts at 0** – very common mistake.
5. **Negative index -1** gives the last element.
6. **Nested lists** are lists inside lists – useful for matrices.
7. **IndexError** occurs if you access an index >= length.

---

## 🧪 Practice Examples (Try Yourself)

```python
my_list = [100, 200.5, "Python", [1, 2, 3]]

# Questions:
print(my_list[0])      # ?
print(my_list[-1])     # ?
print(my_list[2])      # ?
print(my_list[3][1])   # ?
print(len(my_list))    # ?
my_list[1] = 999
print(my_list)         # ?
```

**Answers:**
- `100`
- `[1, 2, 3]`
- `"Python"`
- `2`
- `4`
- `[100, 999, 'Python', [1, 2, 3]]`

---

## 🎯 Final Pro Tips

| You want to... | Use this |
|----------------|----------|
| Store mixed data types | List |
| Change a value later | List (mutable) |
| Access last element | `list[-1]` |
| Get number of items | `len(list)` |
| Create a 2D structure | Nested list |

---

## 🚀 Summary

> **List = [item1, item2, item3, ...]**  
> - Ordered, mutable, indexed, heterogeneous  
> - Index starts at 0 (positive) and -1 (negative from right)  
> - Can contain any data type, including other lists  
> - Perfect for real-life data storage

---

Happy Coding! 🐍📋  
You are now ready to answer any list-related question in exams and interviews. 💪
