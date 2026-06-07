# ✂️ Python String Slicing
<sub>📺 <a href="https://youtu.be/ErgSKwpEEDs?si=oAR37l2p8WZM9Pmw">Video Link</a></sub>

## 🔹 What is Slicing?

> Slicing means **extracting a substring** (a part of the string) from an existing string.

📌 *Example:* From `"Gates Makers"`, you can extract `"tes"`, `"Maker"`, etc.

---

## 🔹 String Indexing – Two Ways

### 1. Positive Indexing (starts from 0)

| Character | G | a | t | e | s | space | M | a | k | e | r | s |
|-----------|---|---|---|---|---|-------|---|---|---|---|---|---|
| Index     | 0 | 1 | 2 | 3 | 4 | 5     | 6 | 7 | 8 | 9 | 10| 11 |

✅ Length = 12 (index 0 to 11)

### 2. Negative Indexing (starts from -1)

| Character | G | a | t | e | s | space | M | a | k | e | r | s |
|-----------|---|---|---|---|---|-------|---|---|---|---|---|---|
| Index     |-12|-11|-10|-9|-8| -7    |-6 |-5 |-4 |-3 |-2 |-1 |

> ⚠️ There is no **negative zero**. Negative indexing always starts from `-1`.

---

## 🔹 Slicing Syntax – The Main Formula

```python
string[start : stop : step]
```

| Parameter | Meaning | Default |
|-----------|---------|---------|
| `start` | Index to begin from (included) | 0 |
| `stop` | Index to stop at (**excluded**) | end of string |
| `step` | Jump size | 1 |

> 🔥 **Most Important Rule:**  
> **`stop` index is always excluded** – the character at `stop` is **NOT** included.

---

## 🔹 Slicing Examples (Positive Indexing)

Let `s = "Gates Makers"`

### 1. `s[5:10]`

- Start at index `5` (space)
- Stop at index `10` (excluded) → goes up to index `9` (e)
- Step = 1 (default)

**Output:** `" Make"` (space + Make)

### 2. `s[:10]` (omit start)

- Start = default `0`
- Stop = `10` (excluded)
- Output: `"Gates Mak"`

### 3. `s[5:]` (omit stop)

- Start = `5` (space)
- Stop = end of string
- Output: `" Makers"`

### 4. `s[:]` (omit both)

- Start = `0`, Stop = end
- Output: `"Gates Makers"` (full string)

---

## 🔹 Slicing with Negative Indexing

### Example: `s[-8:-3]`

- Start = `-8` (character `'M'`)
- Stop = `-3` (character `'e'` – excluded)
- Step = 1

**Output:** `"Make"` (because stop at -3 means stop before `'e'`)

> ✅ `-8` to `-4` → `M a k e`

---

## 🔹 Step Parameter – Jumping Over Characters

### Example: `s[5::2]`

- Start = `5` (space)
- Stop = end (default)
- Step = 2 (take one, skip one)

**Process:**  
Index 5 (space) → skip index 6 → take index 7 (`a`) → skip index 8 → take index 9 (`e`) → skip index 10 → take index 11 (`s`)

**Output:** `" a e s"` (space, a, e, s)

> 💡 Step = 2 means: **take character → skip next → take next → skip next**

---

## 🔹 Reverse a String – The Magic Trick 🎩

### Syntax: `[::-1]`

```python
s = "Gates Makers"
print(s[::-1])   # Output: "srekaM setaG"
```

> ✅ `[::-1]` reverses the entire string. Very important for interviews!

---

## 🔹 Slicing with String Methods

You can chain methods after slicing.

### Example: `s[5:12].upper()`

- Slice from index `5` to `11` (since index 12 excluded) → `" Makers"`
- Apply `.upper()` → `" MAKERS"`

### Example: `s[5:12].lower()`

- Output: `" makers"`

---

## 🔹 Length with Slicing

```python
s = "Gates Makers"
print(len(s))        # 12
print(len(s[5:10]))  # 5 (characters from index 5 to 9)
```

---

## 📊 Quick Reference Table

| Slice | Meaning | Example (s="Gates Makers") | Output |
|-------|---------|----------------------------|--------|
| `s[start:stop]` | start to stop-1 | `s[0:5]` | `Gates` |
| `s[:stop]` | 0 to stop-1 | `s[:4]` | `Gate` |
| `s[start:]` | start to end | `s[6:]` | `Makers` |
| `s[:]` | full string | `s[:]` | `Gates Makers` |
| `s[start:stop:step]` | with jump | `s[::2]` | `Gt akr` |
| `s[::-1]` | reverse | `s[::-1]` | `srekaM setaG` |
| `s[stop:start]` | empty (if start>stop) | `s[10:5]` | `''` |

---

## ✅ Important Interview / Exam Points

1. **Stop index is always excluded** – most common mistake!
2. **Negative indexing starts at -1** (not -0)
3. **Empty start or stop** – uses default values
4. **Reverse string** = `[::-1]`
5. **Step value** can skip characters
6. **Slicing never gives an error** if out of range – it just returns empty string or shorter string.

---

## 🧪 Practice Examples (Try Yourself)

```python
s = "PythonProgramming"

print(s[0:6])     # ? 
print(s[6:])      # ?
print(s[::2])     # ?
print(s[::-1])    # ?
print(s[-6:-2])   # ?
print(s[2:8:2])   # ?
```

**Answers:**
- `Python`
- `Programming`
- `Pto rgamn` (every 2nd char)
- `gnimmargorPnohtyP`
- `rami` (from -6 to -3)
- `to` (index 2=t, step 2 → index 4=h → index 6=r → but stop at 8 excluded? Wait, check carefully)

> 💡 Always verify by running code!

---

## 🎯 Final Pro Tips

| You want to... | Use this |
|----------------|----------|
| Get first 3 chars | `s[:3]` |
| Get last 3 chars | `s[-3:]` |
| Skip first 3 chars | `s[3:]` |
| Get every 2nd char | `s[::2]` |
| Reverse string | `s[::-1]` |
| Get middle (index 2 to 6) | `s[2:7]` (since stop excluded) |

---

## 🚀 Summary

> **Slicing = [start : stop : step]**  
> - start included, stop excluded  
> - default start = 0, default stop = end, default step = 1  
> - negative index = count from right (-1 is last char)  
> - `[::-1]` = reverse string

---

Happy Slicing! 🍰🐍  
You're now ready for any string slicing question in exams and interviews. 💪
