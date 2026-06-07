# ⚠️ Python Built-in Exceptions
<sub>📺 <a href="https://youtu.be/hJkZk9CKr-o?si=9nMEoI2l3UJMExS6">Video Link</a></sub>
## 🔹 What are Exceptions?

> **Exceptions** are runtime errors that occur when the program is running. Python has **predefined names** for different types of errors so programmers can understand and fix them easily.

✅ Exceptions help you identify **what went wrong** and **why**.

---

## 🔹 Common Built-in Exceptions (with Examples)

| Exception | Cause | Example |
|-----------|-------|---------|
| `SyntaxError` | Wrong Python syntax (grammar mistake) | Missing closing quote, bracket |
| `TypeError` | Operation on wrong data type | Dividing string by integer |
| `ValueError` | Correct type but invalid value | Converting "hello" to int |
| `NameError` | Variable/function not defined | Using undefined variable |
| `IndexError` | List/tuple index out of range | Accessing index 5 in list of 3 items |
| `KeyError` | Dictionary key doesn't exist | Accessing dict["invalid_key"] |
| `AttributeError` | Method/attribute doesn't exist | Using "hello".capitalize() wrong spelling |
| `ZeroDivisionError` | Division by zero | 10 / 0 |
| `ImportError` | Module not found | `import xyz` (xyz doesn't exist) |
| `MemoryError` | Out of memory | Creating huge list |
| `FileNotFoundError` | File doesn't exist | Opening missing file |

---

# 1. `SyntaxError` – Grammar Mistake 📝

**Cause:** Violating Python's grammar rules.

```python
print("Hello)   # ❌ Missing closing quote
```

**Output:**
```
SyntaxError: unterminated string literal (detected at line 1)
```

> 💡 Fix: Close all quotes, brackets, and use proper indentation.

---

# 2. `TypeError` – Wrong Data Type Operation 🔢

**Cause:** Performing an operation on incompatible data types.

```python
x = "20"   # string
y = 10     # integer
print(x / y)   # ❌ Cannot divide string by int
```

**Output:**
```
TypeError: unsupported operand type(s) for /: 'str' and 'int'
```

> 💡 Fix: Convert string to int using `int(x)` first.

---

# 3. `ValueError` – Correct Type, Invalid Value 🎯

**Cause:** Function receives argument of correct type but inappropriate value.

```python
x = int("hello")   # ❌ Cannot convert "hello" to integer
```

**Output:**
```
ValueError: invalid literal for int() with base 10: 'hello'
```

> ✅ `int("123")` works, but `int("hello")` gives ValueError.

---

# 4. `NameError` – Undefined Variable/Function 🏷️

**Cause:** Using a variable or function that hasn't been defined.

```python
a = 20
print(b)   # ❌ b is not defined
```

**Output:**
```
NameError: name 'b' is not defined
```

> 💡 Fix: Define the variable before using it.

---

# 5. `IndexError` – List Index Out of Range 📋

**Cause:** Accessing an index that doesn't exist in a list/tuple.

```python
my_list = [1, 2, 3]   # Indexes: 0,1,2
print(my_list[5])     # ❌ Index 5 doesn't exist
```

**Output:**
```
IndexError: list index out of range
```

> 💡 Fix: Check `len(list)` before accessing index.

---

# 6. `KeyError` – Dictionary Key Not Found 🔑

**Cause:** Accessing a dictionary with a key that doesn't exist.

```python
my_dict = {1: "a", 2: "b"}
print(my_dict[3])   # ❌ Key 3 doesn't exist
```

**Output:**
```
KeyError: 3
```

> 💡 Fix: Use `dict.get(key)` to avoid KeyError.

---

# 7. `AttributeError` – Invalid Method/Attribute 🧰

**Cause:** Calling a method or attribute that doesn't exist for that object.

```python
x = "hello"
print(x.capital())   # ❌ 'capital' doesn't exist (use 'capitalize')
```

**Output:**
```
AttributeError: 'str' object has no attribute 'capital'
```

> 💡 Fix: Check correct spelling – `capitalize()` is correct, `capital()` is wrong.

---

# 8. `ZeroDivisionError` – Division by Zero ➗

**Cause:** Dividing a number by zero.

```python
x = 10
y = 0
print(x / y)   # ❌ Cannot divide by zero
```

**Output:**
```
ZeroDivisionError: division by zero
```

> 💡 Fix: Ensure denominator is not zero before division.

---

# 9. `ImportError` – Module Not Found 📦

**Cause:** Trying to import a module that doesn't exist.

```python
import xyz   # ❌ Module 'xyz' doesn't exist
```

**Output:**
```
ModuleNotFoundError: No module named 'xyz'
```

> 💡 Fix: Install the module or check the spelling.

---

# 10. `MemoryError` – Out of Memory 💾

**Cause:** Creating an object that requires more memory than available.

```python
x = [0] * (10**15)   # ❌ Huge list (may cause MemoryError)
```

**Output:**
```
MemoryError
```

> 💡 Fix: Optimize memory usage or use generators.

---

# 11. `FileNotFoundError` – File Does Not Exist 📁

**Cause:** Trying to open a file that doesn't exist (in read mode).

```python
with open("nonexistent.txt", "r") as f:   # ❌ File doesn't exist
    content = f.read()
```

**Output:**
```
FileNotFoundError: [Errno 2] No such file or directory: 'nonexistent.txt'
```

> 💡 Fix: Check file path, create file first, or handle exception.

---

## 📊 Quick Reference Table

| Exception | When it happens | Example |
|-----------|----------------|---------|
| `SyntaxError` | Wrong grammar | `print("hello)` |
| `TypeError` | Wrong type operation | `"20" / 10` |
| `ValueError` | Correct type, invalid value | `int("hello")` |
| `NameError` | Undefined variable | `print(unknown_var)` |
| `IndexError` | Index out of range | `[1,2][5]` |
| `KeyError` | Key doesn't exist | `dict["invalid"]` |
| `AttributeError` | Invalid method | `"hi".capital()` |
| `ZeroDivisionError` | Divide by zero | `10 / 0` |
| `ImportError` | Module not found | `import fake_module` |
| `MemoryError` | Out of memory | Huge list/array |
| `FileNotFoundError` | File missing | `open("missing.txt")` |

---

## ✅ Important Points for Exams/Interviews

1. **SyntaxError** occurs **before** program runs (compile-time), others are runtime.
2. **TypeError vs ValueError** – TypeError is wrong type, ValueError is wrong value within correct type.
3. **KeyError** is specific to dictionaries.
4. **IndexError** is specific to sequences (list, tuple, string).
5. **AttributeError** means the object doesn't have that method/property.
6. **ZeroDivisionError** – mathematical impossibility.
7. **FileNotFoundError** is a type of `OSError` (input/output error).

---

## 🧪 Practice Examples (Try Yourself)

```python
# Identify the exception type:

# 1
print("Hello)        # ?

# 2
x = [1,2,3]
print(x[10])         # ?

# 3
d = {"a":1}
print(d["b"])        # ?

# 4
y = "123"
z = y / 2            # ?

# 5
print(age)           # ?

# 6
num = int("12.5")    # ?

# 7
10 / 0               # ?

# 8
"hello".uppercase()  # ?
```

**Answers:**
1. `SyntaxError` (unterminated string)
2. `IndexError`
3. `KeyError`
4. `TypeError`
5. `NameError`
6. `ValueError` (cannot convert "12.5" to int directly)
7. `ZeroDivisionError`
8. `AttributeError` (use `upper()` not `uppercase()`)

---

## 🎯 Final Pro Tips

| Exception type | Common fix |
|----------------|------------|
| `SyntaxError` | Check quotes, brackets, indentation |
| `TypeError` | Convert types (`int()`, `str()`, etc.) |
| `ValueError` | Validate input before conversion |
| `NameError` | Define variable before use |
| `IndexError` | Check `len()` before accessing |
| `KeyError` | Use `dict.get()` or check `in` |
| `AttributeError` | Check correct spelling of method |
| `ZeroDivisionError` | Check denominator is not zero |
| `ImportError` | Install module or fix path |
| `MemoryError` | Optimize data structures |
| `FileNotFoundError` | Verify file path exists |

---

## 🚀 Summary

> **Exceptions = Python's way of telling you exactly what went wrong.**  
> - `SyntaxError` = grammar mistake  
> - `TypeError` = wrong type operation  
> - `ValueError` = invalid value  
> - `NameError` = undefined variable  
> - `IndexError` = index out of range  
> - `KeyError` = dictionary key missing  
> - `AttributeError` = method doesn't exist  
> - `ZeroDivisionError` = divided by zero  
> - `FileNotFoundError` = missing file

---

Happy Coding! 🐍⚠️  
You are now ready to identify and explain Python exceptions in exams and interviews. 💪
