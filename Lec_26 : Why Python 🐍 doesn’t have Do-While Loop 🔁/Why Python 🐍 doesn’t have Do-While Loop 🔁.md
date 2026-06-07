# 🔁 Do-While Loop Concept in Python
<sub>📺 <a href="https://youtu.be/D-ZSTjn_TrM?si=aMRCj6VNX9KlPkdX">Video Link</a></sub>
## 🔹 What is a Do-While Loop?

> A **do-while loop** executes the loop body **at least once**, then checks the condition at the end.

**Key Feature:** The code runs **first**, condition is checked **afterwards**.

### Traditional Syntax (C/Java):
```c
do {
    // code executes at least once
} while (condition);
```

---

## 🔹 Do-While vs While – The Difference

| Feature | `while` loop | `do-while` loop |
|---------|--------------|------------------|
| Condition check | **At the beginning** | **At the end** |
| Minimum executions | **0 times** (if condition false) | **1 time** (always runs once) |
| Example output (i=0, condition i<0) | No output | Runs once then exits |

### Example in C (for understanding):
```c
int i = 0;
do {
    printf("%d", i);  // Prints 0 (runs once)
    i++;
} while (i < 0);      // Condition false, exit
```
**Output:** `0`

Same thing in `while` loop:
```c
int i = 0;
while (i < 0) {       // Condition false from start
    printf("%d", i);  // Never runs
    i++;
}
```
**Output:** (nothing)

---

## 🔹 Why Doesn't Python Have a Do-While Loop?

> Python does **not** have a built-in `do-while` loop because the same functionality can be achieved using a `while True` loop with a `break` statement.

**Reason:** Adding a separate `do-while` loop would increase complexity without adding new functionality. Python emphasizes **simplicity** and **readability** – one way to do things.

---

## 🔹 How to Simulate Do-While in Python ✅

### Method: `while True` + `break`

```python
i = 0
while True:
    print(i)          # Runs at least once
    i += 1
    if not (i < 0):   # Check condition (opposite of do-while condition)
        break
```

### Step-by-step execution:

| Step | i value | Action |
|------|---------|--------|
| 1 | 0 | Print `0` |
| 2 | 0 → 1 | Increment i to 1 |
| 3 | 1 | Check `if not (1 < 0)` → `if not False` → `if True` → `break` |

**Output:** `0` (runs exactly once, then exits)

> 💡 This perfectly mimics the `do-while` behavior: **run once, then check condition**.

---

## 🔹 General Template for Do-While in Python

```python
while True:
    # code block (runs at least once)
    
    if not (condition):   # Exit when condition becomes false
        break
```

### Example – Keep asking until valid input (at least once):
```python
while True:
    num = int(input("Enter a positive number: "))
    if num > 0:
        break
    print("Invalid, try again")
```

> This runs **at least once**, then repeats only if condition fails.

---

## 📊 Comparison Table

| Aspect | Traditional Do-While (C/Java) | Python Simulation |
|--------|-------------------------------|-------------------|
| Syntax | `do { } while (condition);` | `while True: ... if not condition: break` |
| Runs at least once? | ✅ Yes | ✅ Yes |
| Built-in? | Yes | No (simulated) |
| Why not in Python? | – | Can be done with `while` + `break` |

---

## ✅ Important Points for Exams/Interviews

1. **Python does NOT have a built-in `do-while` loop.**
2. **Reason:** The same behavior can be achieved with `while True` and `break`.
3. **Do-while guarantees** at least one execution of the loop body.
4. **While loop** may execute 0 times if the condition is initially false.
5. To simulate do-while in Python:
   ```python
   while True:
       # loop body
       if not (condition):
           break
   ```

---

## 🧪 Practice Example (Try Yourself)

**Problem:** Simulate do-while to print numbers 1 to 3.

```python
i = 1
while True:
    print(i)
    i += 1
    if i > 3:
        break
```

**Output:** `1 2 3`

---

## 🎯 Final Pro Tips

| You want to... | Use this |
|----------------|----------|
| Run code at least once, then check condition | `while True` + `break` |
| Run code 0 or more times | Normal `while` loop |
| Run code fixed number of times | `for` loop |

---

## 🚀 Summary

> **Do-while loop** = execute first, check condition later (at least once).  
> **Python doesn't have it** because `while True` + `break` does the same job.  
> **Interview answer:** "Python follows simplicity – do-while can be simulated using an infinite while loop with a break condition."

---

Happy Coding! 🐍🔄  
You are now ready to answer why Python doesn't have a do-while loop and how to simulate it. 💪
