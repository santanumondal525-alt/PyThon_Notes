# 🚦 Python `Break`, `Continue`, `Pass`
<sub>📺 <a href="https://youtu.be/8d8bmm4qPro?si=-pzSjXETViGzI438">Video Link</a></sub>
## 🔹 What are These Keywords?

> `break`, `continue`, and `pass` are **control flow statements** used inside loops (`for` and `while`) to alter the normal execution.

| Keyword | Purpose |
|---------|---------|
| `break` | **Exit** the loop immediately (terminates completely) |
| `continue` | **Skip** the current iteration and move to the next |
| `pass` | **Do nothing** (placeholder – no operation) |

---

# 1. `break` – Exit the Loop Completely 🛑

> When `break` is encountered, the loop **stops immediately** and control moves to the next statement after the loop.

### Example – Stop when value equals 4:
```python
for x in range(8):   # 0,1,2,3,4,5,6,7
    if x == 4:
        break
    print(x)
```

**Output:**
```
0
1
2
3
```

### Step-by-step:

| x value | x == 4? | Action |
|---------|---------|--------|
| 0 | False | Print 0 |
| 1 | False | Print 1 |
| 2 | False | Print 2 |
| 3 | False | Print 3 |
| 4 | True | **break** → exit loop (5,6,7 not printed) |

> 💡 `break` completely terminates the loop.

---

# 2. `continue` – Skip Current Iteration ⏭️

> When `continue` is encountered, the **current iteration stops** and the loop jumps to the **next iteration**.

### Example – Skip value 4:
```python
for x in range(8):   # 0,1,2,3,4,5,6,7
    if x == 4:
        continue
    print(x)
```

**Output:**
```
0
1
2
3
5
6
7
```

### Step-by-step:

| x value | x == 4? | Action |
|---------|---------|--------|
| 0 | False | Print 0 |
| 1 | False | Print 1 |
| 2 | False | Print 2 |
| 3 | False | Print 3 |
| 4 | True | **continue** → skip print, go to next (5) |
| 5 | False | Print 5 |
| 6 | False | Print 6 |
| 7 | False | Print 7 |

> 💡 `continue` skips only the current iteration – loop continues.

---

# 3. Difference Between `break` and `continue`

| Feature | `break` | `continue` |
|---------|---------|-------------|
| Effect | **Exits** the loop completely | **Skips** only current iteration |
| Loop afterwards | Loop stops | Loop continues with next value |
| Analogy | Stop the game | Skip your turn (like Uno Skip card) |
| Use case | Found what you're searching for | Want to ignore specific values |

---

# 4. Real-Life Example 1 – Linear Search (Using `break`)

**Problem:** Find if target (3) exists in a list, but don't waste time searching after finding it.

```python
items = [1, 2, 3, 4, 5, 6, 7]
target = 3

for item in items:
    if item == target:
        print("Found:", item)
        break   # Stop searching once found
```

**Advantage:** Saves time – doesn't scan remaining elements.

> ✅ Without `break`, the loop would continue checking 4,5,6,7 unnecessarily.

---

# 5. Real-Life Example 2 – Extract First Name (Using `break`)

**Problem:** From a full name "Varun Singla", extract only the first name (stop at space).

```python
name = input("Enter full name: ")
first_name = ""

for char in name:
    if char == " ":
        break
    first_name += char

print("First name:", first_name)
```

**Input:** `Varun Singla`  
**Output:** `First name: Varun`

> ✅ `break` stops at the space, so last name is not added.

---

# 6. `continue` Example – Skip Spaces

**Problem:** Print all characters except spaces.

```python
name = input("Enter full name: ")

for char in name:
    if char == " ":
        continue
    print(char)
```

**Input:** `Varun Singla`  
**Output:** `V a r u n S i n g l a` (space skipped)

> ✅ `continue` skips the space and moves to next character.

---

# 7. `pass` – Do Nothing (Placeholder) 🚫

> `pass` is a **null operation** – nothing happens when executed. Used as a **placeholder** where syntax requires a statement but you don't want to do anything yet.

### Syntax:
```python
if condition:
    pass   # TODO: implement later
```

### Example – Age validation (placeholder for future logic):
```python
age = int(input("Enter age: "))

if age > 18 and age < 28:
    print("You are welcome")
else:
    pass   # Will decide later what to do here
```

**Why use `pass`?**  
Without `pass`, an empty `else` block would cause an **IndentationError**.

| Without pass (❌ Error) | With pass (✅ Works) |
|------------------------|---------------------|
| `else:` (nothing) → Error | `else: pass` → No error |

> 💡 `pass` is also used in functions, classes, and loops that you plan to implement later.

---

## 📊 Comparison Table

| Keyword | Effect | Loop continues? | Used for |
|---------|--------|-----------------|----------|
| `break` | Exits loop completely | No | Stop searching, early exit |
| `continue` | Skips current iteration | Yes | Skip unwanted values |
| `pass` | Does nothing | Yes (no effect) | Placeholder for future code |

---

## ✅ Important Points for Exams/Interviews

1. **`break`** – terminates the loop immediately (like emergency stop).
2. **`continue`** – skips the rest of the current iteration and moves to next.
3. **`pass`** – does absolutely nothing; used where code is required but not yet written.
4. Python does **not** have a `do-while` loop, but `while True` with `break` can simulate it.
5. **Use `break`** to save time in search operations.
6. **Use `continue`** to filter out specific values.
7. **Use `pass`** as a placeholder to avoid syntax errors.

---

## 🧪 Practice Examples (Try Yourself)

```python
# Example 1: break
for i in range(1, 10):
    if i == 5:
        break
    print(i)   # Output: 1 2 3 4

# Example 2: continue
for i in range(1, 6):
    if i == 3:
        continue
    print(i)   # Output: 1 2 4 5

# Example 3: pass
num = 10
if num > 5:
    pass   # Nothing happens
else:
    print("Less than 5")
# No error, just does nothing
```

---

## 🎯 Final Pro Tips

| You want to... | Use this |
|----------------|----------|
| Stop loop completely when condition met | `break` |
| Skip certain values but keep looping | `continue` |
| Write incomplete code (syntax placeholder) | `pass` |
| Exit after finding an item | `break` |
| Ignore specific elements | `continue` |

---

## 🚀 Summary

> **`break`** = exit loop entirely  
> **`continue`** = skip current iteration, go to next  
> **`pass`** = do nothing (placeholder)  

```python
# Quick visual
for i in range(5):
    if i == 2:
        break    # stops at 2 → 0,1
    if i == 2:
        continue # skips 2 → 0,1,3,4
    if i == 2:
        pass     # does nothing → 0,1,2,3,4
```

---

Happy Coding! 🐍🚦  
You are now ready to answer any question on `break`, `continue`, and `pass` in exams and interviews. 💪
