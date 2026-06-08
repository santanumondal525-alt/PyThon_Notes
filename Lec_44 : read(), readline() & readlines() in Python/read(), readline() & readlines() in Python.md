# 📖 Python File Reading Methods
<sub>📺 <a href="https://youtu.be/5xEUDOA5PJA?si=07sIALmmCzKeYPRo">Video Link</a></sub>
## 🔹 Three Main File Reading Functions

| Function | What it does | Return Type |
|----------|--------------|-------------|
| `read()` | Reads the **entire file** or specified number of characters | String |
| `readline()` | Reads **one line** at a time | String |
| `readlines()` | Reads **all lines** into a list | List of strings |

---

# 1. `read()` – Read Entire File or Specific Characters

> Reads the whole file content (or a specific number of characters) as a **single string**.

### Syntax:
```python
file.read()        # Reads entire file
file.read(n)       # Reads n characters (bytes)
```

### Example 1: Read Entire File

```python
with open("new.txt", "r") as f:
    content = f.read()
    print(content)
```

**Output:** Entire content of the file as a single string.

### Example 2: Read Specific Number of Characters

```python
with open("new.txt", "r") as f:
    first_5_chars = f.read(5)
    print(first_5_chars)   # First 5 characters
```

> 💡 If you specify a number, it reads exactly that many characters (or less if file ends).

---

## 🔹 Understanding the File Pointer (Cursor)

> When you open a file, a **file pointer** (cursor) keeps track of your current position in the file.

| Operation | Effect on File Pointer |
|-----------|------------------------|
| Open file | Pointer starts at **position 0** (beginning) |
| `read(n)` | Pointer moves forward by **n** characters |
| `readline()` | Pointer moves to **next line** |
| `seek(position)` | Pointer jumps to **specific position** |
| `tell()` | Returns **current position** of pointer |

### Example – Pointer Movement:

```python
with open("new.txt", "r") as f:
    print(f.read(5))    # Reads first 5 chars → pointer at position 5
    print(f.read(5))    # Reads next 5 chars → pointer at position 10
    print(f.tell())     # Shows current position: 10
```

> 🔥 **Important:** The file pointer **remembers its position** between reads!

---

# 2. `tell()` – Get Current File Pointer Position

> Returns the current position of the file pointer (in bytes from the beginning).

```python
with open("new.txt", "r") as f:
    print(f.tell())      # Position 0 (start)
    f.read(5)
    print(f.tell())      # Position 5
    f.read(5)
    print(f.tell())      # Position 10
```

---

# 3. `seek()` – Move File Pointer to Specific Position

> Moves the file pointer to a specified position (in bytes).

### Syntax:
```python
file.seek(offset)        # Move to 'offset' bytes from beginning
```

### Example – Move to Beginning:

```python
with open("new.txt", "r") as f:
    f.read(10)                     # Read first 10 chars
    print(f.tell())                # Position 10
    f.seek(0)                      # Move back to beginning
    print(f.tell())                # Position 0
    print(f.read(5))               # Reads first 5 chars again
```

### Example – Move to Specific Position:

```python
with open("new.txt", "r") as f:
    f.seek(15)                     # Move to position 15
    print(f.read(5))               # Reads 5 chars starting from position 15
```

> 💡 `seek(0)` takes you back to the **beginning** of the file.

---

# 4. `readline()` – Read One Line at a Time

> Reads a **single line** from the file (including the newline character). Each call reads the next line.

### Example – Reading Line by Line:

```python
with open("new.txt", "r") as f:
    line1 = f.readline()    # First line
    line2 = f.readline()    # Second line
    line3 = f.readline()    # Third line
    print(line1)
    print(line2)
    print(line3)
```

### Example – Using Loop to Read All Lines:

```python
with open("new.txt", "r") as f:
    for line in f:
        print(line)         # Prints each line one by one
```

> 💡 `readline()` includes the newline character `\n` at the end of each line.

### `readline(n)` – Read n Characters from Current Line:

```python
with open("new.txt", "r") as f:
    first_20_of_line1 = f.readline(20)   # Reads first 20 chars of line 1 only
    print(first_20_of_line1)
```

> ⚠️ Even if you specify a large number (like 200), `readline()` will **only read the current line** – it won't go to the next line.

---

# 5. `readlines()` – Read All Lines into a List

> Reads the **entire file** and returns a **list of strings**, where each element is one line.

### Syntax:
```python
lines_list = file.readlines()
```

### Example:

```python
with open("new.txt", "r") as f:
    all_lines = f.readlines()
    print(all_lines)
    # Output: ['First line\n', 'Second line\n', 'Third line']
```

> 💡 Each line ends with `\n` except possibly the last line.

### Accessing Specific Lines:

```python
with open("new.txt", "r") as f:
    lines = f.readlines()
    print(lines[0])    # First line
    print(lines[1])    # Second line
    print(lines[2])    # Third line
```

---

## 📊 Comparison Table

| Function | Reads | Returns | Pointer movement | Best for |
|----------|-------|---------|------------------|----------|
| `read()` | Entire file or N chars | Single string | Moves to end | Small files |
| `read(n)` | N characters | Single string | Moves N chars | Reading specific amount |
| `readline()` | One line | String (with `\n`) | Moves to next line | Reading line by line |
| `readlines()` | Entire file | List of strings | Moves to end | When you need lines as list |

---

## 🔹 Complete Example – All Functions in Action

```python
# Sample file "new.txt" content:
# Hello World
# Python Programming
# File Handling

with open("new.txt", "r") as f:
    # read() - entire file
    f.seek(0)
    print("read():", f.read())
    
    # read(5) - first 5 chars
    f.seek(0)
    print("read(5):", f.read(5))
    
    # readline() - first line
    f.seek(0)
    print("readline():", f.readline())
    
    # readlines() - all lines as list
    f.seek(0)
    print("readlines():", f.readlines())
```

---

## ✅ Important Points for Exams/Interviews

1. **`read()`** without arguments reads the **entire file** as a single string.
2. **`read(n)`** reads exactly **n characters** (or less if file ends).
3. **`readline()`** reads **one line** including the newline character `\n`.
4. **`readlines()`** reads **all lines** and returns a **list**.
5. **File pointer** (cursor) moves automatically after each read operation.
6. **`tell()`** returns the current position of the file pointer.
7. **`seek(position)`** moves the file pointer to a specific position.
8. **`seek(0)`** moves pointer to the **beginning** of the file.
9. `readline(n)` only reads from the **current line** – won't go to next line even if n is large.
10. Use **loops** with `readline()` for memory-efficient processing of large files.

---

## 🧪 Practice Examples (Try Yourself)

```python
# Create a sample file
with open("sample.txt", "w") as f:
    f.write("Line 1: Apple\nLine 2: Banana\nLine 3: Cherry")

# 1. read() - entire file
with open("sample.txt", "r") as f:
    print(f.read())   # Whole file as string

# 2. read(10) - first 10 chars
with open("sample.txt", "r") as f:
    print(f.read(10)) # First 10 characters

# 3. tell() and seek()
with open("sample.txt", "r") as f:
    print(f.tell())   # 0
    f.read(5)
    print(f.tell())   # 5
    f.seek(0)
    print(f.tell())   # 0

# 4. readline() - line by line
with open("sample.txt", "r") as f:
    print(f.readline())   # Line 1
    print(f.readline())   # Line 2
    print(f.readline())   # Line 3

# 5. readlines() - list of lines
with open("sample.txt", "r") as f:
    lines = f.readlines()
    print(lines[0])   # First line
    print(lines[1])   # Second line
```

---

## 🎯 Final Pro Tips

| You want to... | Use this |
|----------------|----------|
| Read entire small file | `read()` |
| Read specific number of characters | `read(n)` |
| Read line by line (memory efficient) | `readline()` in a loop |
| Get all lines as a list | `readlines()` |
| Check current position | `tell()` |
| Move to beginning | `seek(0)` |
| Move to specific position | `seek(n)` |

---

## 🚀 Summary

> **File Reading Methods in Python:**
> - `read()` → whole file as **string**
> - `read(n)` → **n characters** as string
> - `readline()` → **one line** as string
> - `readlines()` → **all lines** as list
> - `tell()` → current **pointer position**
> - `seek(n)` → move pointer to **position n**

```python
# Quick visual
with open("file.txt", "r") as f:
    all_text = f.read()           # Entire file
    f.seek(0)                     # Go back to start
    first_line = f.readline()     # First line
    f.seek(0)                     # Go back to start
    all_lines = f.readlines()     # List of all lines
```

---

Happy Coding! 🐍📁  
You are now ready to answer any question on `read()`, `readline()`, and `readlines()` in exams and interviews. 💪
