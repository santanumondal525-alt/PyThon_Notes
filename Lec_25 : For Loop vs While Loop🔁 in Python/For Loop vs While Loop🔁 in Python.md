# 🔄 Python Loops
<sub>📺 <a href="https://youtu.be/_Li18QM_9U4?si=bZKLkVShBkJa4Awj">Video Link</a></sub>
## 🔹 What are Loops?

> Loops allow you to **execute a block of code repeatedly** based on a condition or over a sequence.

Python has **two types of loops**:
1. **`for` loop** – used for iterating over a sequence
2. **`while` loop** – used for repeated execution until a condition becomes false

---

# 1. `for` Loop – Iterate Over a Sequence

## When to use?
> When you **know in advance** how many times you want to iterate (or you have a fixed sequence).

## Syntax:
```python
for variable in sequence:
    # code to execute
```

## Example 1 – Iterating over a List:
```python
colors = ["Blue", "Black", "Green", "Grey"]
for color in colors:
    print(color)
```

**Output:**
```
Blue
Black
Green
Grey
```

## Example 2 – Using `range()`:
```python
for i in range(1, 10):
    print(i)
```

**Output:** `1 2 3 4 5 6 7 8 9` (1 to 9, 10 is excluded)

> 💡 `range(start, stop)` → stop is **excluded**.

---

# 2. `while` Loop – Repeat Until Condition is False

## When to use?
> When you **do NOT know** in advance how many times the loop will run. It runs **as long as** the condition is `True`.

## Syntax:
```python
while condition:
    # code to execute
    # update condition (to avoid infinite loop)
```

## Example – Print numbers 1 to 4:
```python
i = 1
while i < 5:
    print(i)
    i = i + 1   # increment (important!)
```

**Output:**
```
1
2
3
4
```

### Step-by-step execution:

| Iteration | i value | Condition (i < 5) | Action |
|-----------|---------|-------------------|--------|
| 1 | 1 | True | Print 1, i becomes 2 |
| 2 | 2 | True | Print 2, i becomes 3 |
| 3 | 3 | True | Print 3, i becomes 4 |
| 4 | 4 | True | Print 4, i becomes 5 |
| 5 | 5 | False | Exit loop |

> ⚠️ **Important:** Always update the condition variable inside the loop (like `i = i + 1`). Otherwise, you'll get an **infinite loop**!

---

# 3. Key Difference – `for` vs `while` Loop

| Feature | `for` loop | `while` loop |
|---------|------------|---------------|
| **When to use** | When number of iterations is **known** | When number of iterations is **unknown** |
| **Based on** | Sequence (list, string, range, etc.) | Condition |
| **Initialization** | Not required separately | Required before loop |
| **Increment/Update** | Automatic (from sequence) | Manual (inside loop) |
| **Infinite loop risk** | Low | High (if condition never becomes false) |
| **Best for** | Iterating over arrays, strings, ranges | Waiting for user input, validation loops |

---

# 4. Real-Life Example – Validating User Input (while loop)

## Problem: Keep asking user for a number between 1 and 100 until they enter a valid number.

```python
x = 0   # initial dummy value

while not (x > 1 and x < 100):
    x = int(input("Enter number between 1 and 100: "))

print("Valid number:", x)
```

### How it works:
- Condition: `not (x > 1 and x < 100)`
- If user enters **10** → (10 > 1 and 10 < 100) = True → not True = False → **exit loop**
- If user enters **1000** → (1000 > 1 and 1000 < 100) = False → not False = True → **stay in loop, ask again**

> ✅ This is perfect for `while` loop because we don't know how many attempts the user will take.

---

# 5. Same Example Using `for` Loop (With Limitation)

```python
for i in range(4):   # only 4 attempts allowed
    x = int(input("Enter number between 1 and 100: "))
    if x > 1 and x < 100:
        print("Valid number:", x)
        break
    else:
        print("Invalid number, try again")
else:
    print("Too many invalid attempts")
```

### Limitation:
- You must **predefine** the number of attempts (here 4).
- After 4 attempts, the loop stops even if the user didn't enter a valid number.

> 🎯 This shows the key difference: `while` loop has **no fixed limit** – it runs until condition is satisfied.

---

# 6. `for` Loop with `break` and `else`

You can use `break` to exit early, and `else` runs only if loop completes without `break`.

```python
for i in range(1, 6):
    if i == 3:
        break
    print(i)
else:
    print("Loop completed")   # This will NOT run because of break
```

**Output:** `1 2`

---

## 📊 Quick Reference Table

| Task | `for` loop | `while` loop |
|------|------------|---------------|
| Iterate over list | `for item in list:` | Possible but needs index |
| Run 10 times | `for i in range(10):` | `i=0; while i<10: i+=1` |
| Unknown iterations | Not ideal | ✅ Best choice |
| User validation | Needs max attempts | ✅ Best choice |
| Risk of infinite loop | Low | Medium (if condition never false) |

---

## ✅ Important Points for Exams/Interviews

1. **`for` loop** is used when you know the number of iterations or have a sequence.
2. **`while` loop** is used when iterations depend on a condition (unknown count).
3. **`range(start, stop, step)`** – stop is **excluded**.
4. **Always update** the condition variable in `while` loop to avoid infinite loops.
5. **`break`** – exits the loop immediately.
6. **`continue`** – skips the rest of the current iteration.
7. **`else` with loops** – executes only if loop completes normally (without `break`).

---

## 🧪 Practice Examples (Try Yourself)

```python
# Example 1: for loop with list
fruits = ["apple", "banana", "mango"]
for fruit in fruits:
    print(fruit)

# Example 2: for loop with range
for i in range(2, 10, 2):
    print(i)   # even numbers from 2 to 8

# Example 3: while loop
count = 5
while count > 0:
    print(count)
    count -= 1

# Example 4: while loop for validation
num = 0
while num <= 0:
    num = int(input("Enter a positive number: "))
print("Thanks!")
```

**Outputs:**
- `apple banana mango`
- `2 4 6 8`
- `5 4 3 2 1`
- Keeps asking until positive number is entered.

---

## 🎯 Final Pro Tips

| You want to... | Use this loop |
|----------------|---------------|
| Iterate over list/tuple/string | `for` loop |
| Run code fixed number of times | `for` loop with `range()` |
| Keep asking until valid input | `while` loop |
| Wait for a condition to become true | `while` loop |
| Traverse a file until end | `while` loop |

---

## 🚀 Summary

> **`for` loop** = known number of iterations, iterates over sequences  
> **`while` loop** = unknown number of iterations, runs until condition becomes false  
> **Difference** = `for` needs a sequence/range, `while` needs a condition and manual update

---

Happy Coding! 🐍🔄  
You are now ready to answer any loop-related question in exams and interviews. 💪
