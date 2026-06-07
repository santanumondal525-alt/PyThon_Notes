# 📝 Python Quotes
<sub>📺 <a href="https://youtu.be/AmyPAtu0bxY?si=yb6xhzLraZej1ZuP">Video Link</a></sub>
## 🔹 What are Quotes in Python?

> Quotes are used to define **string literals** in Python.  
> Python supports **three types** of quotes:

| Quote Type | Example | Use Case |
|------------|---------|----------|
| Single quotes | `'Hello'` | Single-line strings |
| Double quotes | `"Hello"` | Single-line strings |
| Triple quotes | `'''Hello'''` or `"""Hello"""` | Multi-line strings & multi-line comments |

---

# 1. Single Quotes `' '` – Single Line Strings ✅

Used for **single-line** string literals.

```python
print('Hello World')
```

**Output:** `Hello World`

> ✅ Works perfectly for one line of text.

---

# 2. Double Quotes `" "` – Single Line Strings ✅

Also used for **single-line** string literals (identical to single quotes).

```python
print("Hello World")
```

**Output:** `Hello World`

> 💡 Both single and double quotes are **interchangeable** for single-line strings.

---

# 3. Triple Quotes `''' '''` or `""" """` – Multi-Line Strings 📄

Used when you want to write a string that **spans multiple lines**.

### Problem with Single/Double Quotes for Multi-Line:

```python
# ❌ This will cause an error
print('Should I do studies
      or should I apply
      for a job')
```

**Error:** `SyntaxError: unterminated string literal`

> ⚠️ Single and double quotes **cannot** span multiple lines.

### Solution – Triple Quotes:

```python
# ✅ Correct way for multi-line strings
print('''Should I do studies
or should I apply
for a job''')
```

**Output:**
```
Should I do studies
or should I apply
for a job
```

> ✅ Triple quotes preserve **line breaks** exactly as written.

---

# 4. Triple Quotes for Multi-Line Comments 💬

In Python, single-line comments start with `#`.  
For **multi-line comments**, you can use triple quotes (they are ignored by the interpreter).

### Single-line comment:
```python
# This is a single line comment
```

### Multi-line comment using triple quotes:
```python
"""
This is a multi-line comment
that spans multiple lines
and is ignored by Python
"""
print("Hello")
```

**Output:** `Hello` (the triple-quoted block is treated as a comment)

> 💡 Triple-quoted strings that are **not assigned to any variable** act as multi-line comments.

---

## 📊 Comparison Table

| Feature | Single Quotes `' '` | Double Quotes `" "` | Triple Quotes `''' '''` |
|---------|---------------------|---------------------|-------------------------|
| Multi-line | ❌ No | ❌ No | ✅ Yes |
| Single-line | ✅ Yes | ✅ Yes | ✅ Yes |
| Use as comment | ❌ No | ❌ No | ✅ Yes (unassigned) |
| Preserve line breaks | ❌ No | ❌ No | ✅ Yes |

---

## ✅ Important Points for Exams/Interviews

1. **Single and double quotes** are identical – use either for single-line strings.
2. **Triple quotes** are the **only way** to create multi-line strings in Python.
3. **Triple quotes** can also be used as **multi-line comments** (if not assigned to a variable).
4. Using single/double quotes for multi-line strings causes **SyntaxError**.
5. Triple quotes can be either `'''` (three single) or `"""` (three double) – both work the same.

---

## 🧪 Practice Examples (Try Yourself)

```python
# Example 1: Single quotes
print('Python is fun')           # ✅ Works

# Example 2: Double quotes
print("Python is fun")           # ✅ Works

# Example 3: Multi-line string with triple quotes
print("""Line 1
Line 2
Line 3""")                       # ✅ Works

# Example 4: Multi-line comment
"""
This whole block is ignored
It acts as a comment
"""
print("Hello")                   # ✅ Prints Hello

# Example 5: Error
# print('Line 1
#       Line 2')                 # ❌ SyntaxError
```

---

## 🎯 Final Pro Tips

| You want to... | Use this |
|----------------|----------|
| Write one line of text | `'Hello'` or `"Hello"` |
| Write multiple lines of text | `'''Line1\nLine2'''` or `"""Line1\nLine2"""` |
| Write a multi-line comment | `""" comment """` (unassigned) |
| Include a quote inside a string | Mix quotes: `"It's nice"` or `'He said "Hi"'` |

---

## 🚀 Summary

> - **Single/Double quotes** = single-line strings only  
> - **Triple quotes** = multi-line strings + multi-line comments  
> - Using single/double quotes for multi-line text → **SyntaxError**  
> - Triple quotes preserve **line breaks** exactly

```python
# Quick visual
'Hello'      # ✅ Single line
"Hello"      # ✅ Single line
'''Hello
World'''     # ✅ Multi-line (works)
"""Hello
World"""     # ✅ Multi-line (works)
```

---

Happy Coding! 🐍💬  
You are now ready to answer any question about quotes in Python. 💪
