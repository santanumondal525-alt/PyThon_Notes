# 🧪 Python Strings – Execution & Practical
<sub>📺 <a href="https://youtu.be/nEfioTUG3xE?si=HUE5vUKNTN6ekQXl">Video Link</a></sub>

## 1. Printing and Length (len) 📏

```python
s = "Hello World!"
print(s)      # Output: Hello World!
print(len(s)) # Output: 13
```

> 💡 **Remember:** Spaces and punctuation (`!`) are also characters.  
> Index goes from `0` to `12`, so length = `13`.

---

## 2. Indexing – Accessing a Character 🎯

```python
s = "Hello World!"
print(s[1])   # Output: e
```

> ✅ Index `1` → second character (because index `0` = `H`).

---

## 3. Immutability – Cannot Change a String ❌

```python
s = "Hello World!"
s[1] = 'a'    # ❌ Error!
```

**Error Message:**
> `'str' object does not support item assignment`

> 🔒 **Key Point:** Strings are **immutable** – once created, you cannot modify them.

---

## 4. Slicing – Extract a Part ✂️

**Syntax:** `[start:end]` – end index is **excluded**.

```python
s = "Hello World!"
print(s[1:4])   # Output: ell
```

**Explanation:**  
Index `1` = `e`, `2` = `l`, `3` = `l`, `4` = `o` (excluded) → `ell`

---

## 5. Mutable vs Immutable – List vs String 🔁

| Type | Mutable? | Example |
|------|----------|---------|
| List | ✅ Yes | Can change values anytime |
| String | ❌ No | Cannot change after creation |

```python
# List (mutable)
lst = [1, 2, 3]
lst[1] = 30   # ✅ Works
print(lst)    # [1, 30, 3]

# String (immutable)
s = "Hello"
# s[1] = 'a'  # ❌ Error
```

---

## 6. Concatenation – Joining Strings ➕

```python
s1 = "Hello"
s2 = "World"
s3 = s1 + s2
print(s3)   # Output: HelloWorld (no space!)
```

### 🔹 To add a space in between:
```python
s3 = s1 + " " + s2
print(s3)   # Output: Hello World
```

> ⚠️ `+` does **not** automatically add spaces – you must add them explicitly.

---

## 7. String + Number = Error ❌

```python
s1 = "Hello"
num = 20
print(s1 + num)   # ❌ TypeError
```

**Reason:** Cannot mix `str` and `int` directly.

### 🔹 Solutions – Type Casting:

**Method 1:** Convert number to string using quotes  
```python
print(s1 + "20")   # ✅ Hello20
```

**Method 2:** Use `str()` function  
```python
print(s1 + str(num))   # ✅ Hello20
```

**Method 3:** Convert during runtime  
```python
print(s1 + str(20))    # ✅ Hello20
```

---

## 8. String Formatting – Insert Variables into Strings 🧩

### ✅ Method 1: f-strings (Python 3.6+) – **Recommended**

```python
first_name = "Varun"
last_name = "Singla"
age = 33

print(f"My first name is {first_name}, last name is {last_name}, and age is {age}")
```

**Output:**
```
My first name is Varun, last name is Singla, and age is 33
```

> 💡 Just add `f` before the string and use `{variable_name}`.

---

### ✅ Method 2: `.format()` method (older, but still used)

```python
first_name = "Varun"
last_name = "Singla"
age = 33

print("My first name is {}, last name is {}, and age is {}".format(first_name, last_name, age))
```

**Same output as above.**

> 🔁 `.format()` automatically converts numbers to strings.

---

## 📊 Quick Comparison Table

| Concept | Code Example | Output / Effect |
|---------|--------------|------------------|
| Print string | `print("Hello")` | Hello |
| Length | `len("Hi!")` | 3 |
| Indexing | `"Hi"[1]` | `i` |
| Immutability | `s[0]='a'` | ❌ Error |
| Slicing | `"Hello"[1:4]` | `ell` |
| Concatenation | `"Hi" + " " + "Mom"` | `Hi Mom` |
| str + int | `"Hi" + str(5)` | `Hi5` |
| f-string | `f"Age {age}"` | Age 33 |
| `.format()` | `"Age {}".format(33)` | Age 33 |

---

## ✅ Final Checklist – You Should Now Know:

- [x] What is a string?  
- [x] How to print and get length  
- [x] Indexing (starts at 0)  
- [x] Strings are **immutable** (cannot change)  
- [x] Slicing `[start:end]` excludes end index  
- [x] Difference between list (mutable) and string (immutable)  
- [x] Concatenation with `+` and adding spaces  
- [x] Type casting `str()` to combine string and number  
- [x] f-strings and `.format()` for variable insertion  

---

## 🎯 Pro Tip for Exams/Interviews:

> **f-strings are the modern, clean, and preferred way** to format strings in Python 3.6+.  
> But `.format()` is still asked in interviews – know both!

---

Happy Coding! 🐍💪  
You are now execution-ready for string questions. 🚀
