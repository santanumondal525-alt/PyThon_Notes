# 📌 Python Strings
<sub>📺 <a href="https://youtu.be/0peYiWVY_Ak?si=F1K5s67qI5X4OX2d">Video Link</a></sub>

## 🔹 What is a String?

> A **string** is a **sequence of characters**.

- Used to store text data like **name**, **father's name**, **station name**, **train name**, etc.
- Without strings, we can only store numbers – but real-world data needs text.

📌 *Example:* `"Hello World"`, `"John Doe"`, `"Delhi Junction"`

---

## 🔹 How to Define a String in Python?

You can define a string using:

- ✅ **Single quotes** – `'Hello'`
- ✅ **Double quotes** – `"Hello"`

> ⚠️ **Important:** If you start with a single quote, end with a single quote. Same for double quotes. Mixing them will cause an error.

📌 *Correct:*
```python
name = 'Alice'
city = "Mumbai"
```

📌 *Incorrect:*
```python
name = 'Alice"   ❌
```

---

## 🔹 Strings are Ordered – Indexing

- Strings are **ordered sequences** → each character has a fixed position.
- Positions are called **indexes**.
- Indexing starts from **0** (zero-based indexing).

📌 *Example:* `"Hello World!"`

| Character | H | e | l | l | o | space | W | o | r | l | d | ! |
|-----------|---|---|---|---|---|---|----|---|---|---|---|---|
| Index     | 0 | 1 | 2 | 3 | 4 | 5    | 6  | 7 | 8 | 9 | 10| 11 |

✅ Length = 12 characters (index 0 to 11)

📌 *Code Example:*
```python
s = "Hello World!"
print(s[1])   # Output: e
print(s[6])   # Output: W
```

---

## 🔹 Strings are Immutable 🔒

> **Immutable** means: You **cannot change** a string after it is created.

📌 *Example of what you **cannot** do:*
```python
s = "Hello"
s[1] = 'a'   # ❌ Error! Strings don't support item assignment
```

> ✅ You can only **read** or **create new strings**, not modify existing ones.

---

## 🔹 Slicing Strings ✂️

Slicing means extracting a part of the string.

**Syntax:** `string[start : end]`

- `start` index – included
- `end` index – **excluded** (character at end index is not taken)

📌 *Example:*
```python
s = "Hello World"
print(s[1:4])   # Output: ell
```

**Explanation:**  
Index 1 = `e`, index 2 = `l`, index 3 = `l`, index 4 = `o` (but 4 is excluded) → so `e l l`

---

## 🔹 Useful String Functions (Preview)

| Function | What it does |
|----------|----------------|
| `len(s)` | Returns length (total characters) |
| `s.upper()` | Converts to uppercase |
| `s.lower()` | Converts to lowercase |
| `s[ ]` | Indexing |
| `s[start:end]` | Slicing |

📌 *Example:*
```python
s = "Python"
print(len(s))      # 6
print(s[0:3])      # Pyt
```

---

## 🔹 Real-Life Importance of Strings 🌍

Without strings, you cannot store:
- Student names
- Father’s names
- Train names
- Station names
- Any text data

> ✅ Strings are essential for **databases**, **railway systems**, **student records**, and almost every software application.

---

## 🔹 Quick Revision Points 📝

| Concept | Explanation |
|---------|-------------|
| String | Sequence of characters |
| Quotes | Single (`'`) or double (`"`) – consistent |
| Indexing | Starts from 0 |
| Immutable | Cannot change after creation |
| Slicing | `[start:end]` – end is excluded |
| Use case | Names, places, text data |

---

## ✅ Sample Code – All in One

```python
# Defining strings
s1 = 'Hello'
s2 = "World"

# Indexing
print(s1[1])   # e

# Slicing
print(s2[1:4]) # orl

# Length
print(len(s1)) # 5

# Immutability check (this will cause error)
# s1[1] = 'a'   ❌
```

---

## 🧠 Pro Tip for Exams/Interviews

> **String = Ordered + Immutable + Indexed + Sliceable**

If anyone asks:  
- *Can you change a string?* → **No, strings are immutable.**  
- *How do you access a character?* → Using index like `s[2]`.  
- *What is slicing?* → Extracting a part using `[start:end]`.

---

## 🎯 Final Advice

- ✅ Like and subscribe to the channel (as the teacher says 😄)
- ✅ Practice all examples by typing them out
- ✅ Remember: **Index starts at 0, end index is excluded in slicing**

---

Happy Coding! 🐍💻  
You are now ready to answer any string-related question 🚀
