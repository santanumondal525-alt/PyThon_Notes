# 🧰 Python Built-in String Function
<sub>📺 <a href="https://youtu.be/9qqIn9OnPTg?si=JZUpA4gvhSiEPMNX">Video Link</a></sub>

## 🔹 What are Built-in String Functions?

> Built-in string functions are **pre-defined methods** in Python that help you **manipulate, search, format, and get information** about strings.

✅ Important for: Exams, College practicals, and Interviews.

---

## 1. `len()` – Length of String 📏

Returns the **total number of characters** (including spaces and punctuation).

```python
s = "Gates Makers"
print(len(s))   # Output: 12
```

> 💡 Spaces count as characters!

---

## 2. `count()` – Count Occurrences 🔢

Returns the number of times a substring appears in the string.

```python
s = "hello hello hello"
print(s.count("hello"))   # Output: 3
```

### With start and end index:
```python
s = "hello hello hello"
print(s.count("hello", 5, 15))   # Count between index 5 and 15
```

> ✅ You can specify where to start and stop searching.

---

## 3. `find()` – Find Substring Position 🔍

Returns the **lowest index** where the substring is found.  
Returns `-1` if not found (no error).

```python
s = "Gates Makers"
print(s.find("Maker"))   # Output: 6 (index where 'M' is)
print(s.find("XYZ"))     # Output: -1
```

> ⚠️ `find()` does NOT raise an error if not found – it returns `-1`.

---

## 4. `startswith()` – Check Beginning ✅

Returns `True` if string starts with the given substring.

```python
s = "Python Programming"
print(s.startswith("Python"))   # Output: True
print(s.startswith("Java"))     # Output: False
```

---

## 5. `endswith()` – Check Ending ✅

Returns `True` if string ends with the given substring.

```python
s = "hello.txt"
print(s.endswith(".txt"))   # Output: True
print(s.endswith(".pdf"))   # Output: False
```

---

## 6. `upper()` – Convert to Uppercase 🔠

```python
s = "Gates Makers"
print(s.upper())   # Output: GATES MAKERS
```

---

## 7. `lower()` – Convert to Lowercase 🔡

```python
s = "Gates Makers"
print(s.lower())   # Output: gates makers
```

---

## 8. `replace()` – Replace Substring 🔄

Replaces all occurrences of a substring with another substring.

```python
s = "Hello World"
print(s.replace("World", "Python"))   # Output: Hello Python
```

### Replace with count limit:
```python
s = "one one one"
print(s.replace("one", "two", 2))   # Output: two two one
```

---

## 9. `split()` – Split into List 🧩

Splits the string into a **list** based on a separator.

```python
s = "India is great country"
print(s.split(" "))   # Output: ['India', 'is', 'great', 'country']
```

> 💡 Default separator is space.

---

## 10. `partition()` – Partition into Tuple 📦

Splits the string into **3 parts**:  
(left, separator, right) – based on the **first** occurrence of the separator.

```python
s = "India-is-great"
print(s.partition("-"))   # Output: ('India', '-', 'is-great')
```

> ✅ Returns a **tuple** of 3 elements.

---

## 11. `strip()` – Remove Whitespace 🧹

Removes **leading and trailing** whitespace (spaces, tabs, newlines).

```python
s = "  Hello World  "
print(s.strip())   # Output: "Hello World"
```

### Remove specific characters:
```python
s = "***Hello***"
print(s.strip("*"))   # Output: "Hello"
```

- `lstrip()` – removes from left only
- `rstrip()` – removes from right only

---

## 12. `isalpha()` – Check if All Alphabets 🔤

Returns `True` if all characters are alphabets (a-z, A-Z).

```python
print("Hello".isalpha())   # True
print("Hello123".isalpha()) # False (has numbers)
print("Hello ".isalpha())   # False (has space)
```

---

## 13. `isdigit()` – Check if All Digits 🔢

```python
print("12345".isdigit())   # True
print("123a".isdigit())    # False
```

---

## 14. `isalnum()` – Check if Alphanumeric 🔤🔢

Returns `True` if all characters are alphabets or digits (no spaces/special chars).

```python
print("Hello123".isalnum())   # True
print("Hello 123".isalnum())  # False (space)
```

---

## 📊 Complete Quick Reference Table

| Function | What it does | Example | Output |
|----------|--------------|---------|--------|
| `len(s)` | Length | `len("Hi")` | 2 |
| `s.count(sub)` | Count occurrences | `"hi hi".count("hi")` | 2 |
| `s.find(sub)` | Find index (or -1) | `"abc".find("b")` | 1 |
| `s.startswith(sub)` | Checks beginning | `"Py".startswith("P")` | True |
| `s.endswith(sub)` | Checks ending | `"Py".endswith("y")` | True |
| `s.upper()` | Uppercase | `"hi".upper()` | `"HI"` |
| `s.lower()` | Lowercase | `"HI".lower()` | `"hi"` |
| `s.replace(old, new)` | Replace substring | `"a_b".replace("_","-")` | `"a-b"` |
| `s.split(sep)` | Split into list | `"a b".split(" ")` | `['a','b']` |
| `s.partition(sep)` | Split into tuple | `"a-b".partition("-")` | `('a','-','b')` |
| `s.strip()` | Remove whitespace | `" a ".strip()` | `"a"` |
| `s.isalpha()` | Only letters? | `"Ab".isalpha()` | True |
| `s.isdigit()` | Only digits? | `"12".isdigit()` | True |
| `s.isalnum()` | Letters/digits only? | `"A1".isalnum()` | True |

---

## ✅ Important Points for Exams/Interviews

1. `find()` returns `-1` if not found – **no error**.
2. `count()` can take start and end indexes.
3. `split()` returns a **list**, `partition()` returns a **tuple**.
4. `strip()` removes **leading and trailing** characters only.
5. `replace()` can take a **count** parameter to limit replacements.
6. `isalpha()`, `isdigit()`, `isalnum()` are very common in validation.

---

## 🧪 Practice Examples (Try Yourself)

```python
s = "Python is awesome"

print(len(s))                  # ?
print(s.count("is"))           # ?
print(s.find("is"))            # ?
print(s.startswith("Py"))      # ?
print(s.upper())               # ?
print(s.replace("awesome", "great"))  # ?
print(s.split(" "))            # ?
print(s.partition("is"))       # ?
print("  hello  ".strip())     # ?
print("Python123".isalnum())   # ?
```

**Answers:**
- 18
- 1
- 7
- True
- `"PYTHON IS AWESOME"`
- `"Python is great"`
- `['Python', 'is', 'awesome']`
- `('Python ', 'is', ' awesome')`
- `"hello"`
- True

---

## 🎯 Final Pro Tips

| You want to... | Use this |
|----------------|----------|
| Get string length | `len()` |
| Count a word | `count()` |
| Find position | `find()` |
| Check start/end | `startswith()` / `endswith()` |
| Change case | `upper()` / `lower()` |
| Replace text | `replace()` |
| Break into list | `split()` |
| Break into tuple | `partition()` |
| Remove extra spaces | `strip()` |
| Validate input | `isalpha()`, `isdigit()`, `isalnum()` |

---

## 🚀 Summary

> **Built-in string functions** save time and make string manipulation easy.  
> Master these – they are **frequently asked** in exams and interviews!

---

Happy Coding! 🐍💪  
You are now ready to answer any built-in string function question. 📝✨
