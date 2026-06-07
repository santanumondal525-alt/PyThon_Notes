# 🔀 Python Conditional Statements
<sub>📺 <a href="https://youtu.be/9xiFcK3MRYA?si=6qx2O6rMtcdxkJuh">Video Link</a></sub>
## 🔹 What are Conditional Statements?

> Conditional statements allow your program to **make decisions** and execute different code blocks based on certain conditions.

✅ They control the **flow of execution** – also called **Flow of Control**.

---

## 🔹 Four Types of Conditional Statements in Python

| # | Type | Syntax Keyword |
|---|------|----------------|
| 1 | Simple `if` | `if` |
| 2 | `if-else` | `if` ... `else` |
| 3 | `if-elif-else` | `if` ... `elif` ... `else` |
| 4 | Nested `if` | `if` inside another `if` |

---

# 1. Simple `if` Statement

Executes a block of code **only if** the condition is `True`.

### Syntax:
```python
if condition:
    # code to execute if condition is True
# code outside if (executes always)
```

### Example – Driving License Eligibility:
```python
age = int(input("Enter your age: "))

if age > 18:
    print("You can apply for the license")

print("Thank you")   # This runs always
```

### Output Scenarios:

| Input Age | Output |
|-----------|--------|
| 19 | `You can apply for the license` + `Thank you` |
| 12 | `Thank you` (only) |

> ⚠️ **Important:** `input()` always returns a **string**. Use `int()` or `float()` for type casting.

---

# 2. `if-else` Statement

Executes one block if condition is `True`, another block if `False`.

### Syntax:
```python
if condition:
    # runs when True
else:
    # runs when False
```

### Example:
```python
age = int(input("Enter your age: "))

if age >= 18:
    print("You can apply for the license")
else:
    print("Wait until you turn 18")
```

| Input | Output |
|-------|--------|
| 20 | `You can apply for the license` |
| 15 | `Wait until you turn 18` |

> ✅ Either `if` block OR `else` block runs – never both.

---

# 3. `if-elif-else` Statement (Ladder)

Used when you have **multiple conditions** to check.

### Syntax:
```python
if condition1:
    # block1
elif condition2:
    # block2
elif condition3:
    # block3
else:
    # runs if all conditions are False
```

### Example – Marriage Eligibility (Fun Example 😄):
```python
handsome = True
good_salary = True

if handsome == True and good_salary == True:
    print("You will marry a supermodel")
elif handsome == True and good_salary == False:
    print("You will marry a beautiful girl")
elif handsome == False and good_salary == True:
    print("Chances are high (money matters!)")
else:
    print("Leave it to God (Bhagwan bharose)")
```

> 💡 **`elif`** is short for **else if**. You can have multiple `elif` blocks.

---

# 4. Nested `if` Statement

When an `if` statement is placed **inside another `if` statement**.

### Syntax:
```python
if outer_condition:
    # outer if code
    if inner_condition:
        # runs when both are True
    else:
        # runs when outer True, inner False
else:
    # runs when outer is False
```

### Example – License with Car Ownership:
```python
age = int(input("Enter age: "))

if age > 18:
    print("You can apply for license")
    car = True   # or False
    if car == True:
        print("Drive your car")
    else:
        print("Work hard and purchase a new car")
else:
    print("First turn 18, then apply")
```

### Flow Explanation:

| Age | Car | Output |
|-----|-----|--------|
| 20 | True | `You can apply` + `Drive your car` |
| 20 | False | `You can apply` + `Work hard and purchase a new car` |
| 15 | - | `First turn 18, then apply` |

---

## 🔹 Important: Indentation in Python 🎯

> **Python uses indentation (spaces/tabs) to define code blocks, NOT curly braces `{}` like C/Java.**

```python
if condition:
    print("This is inside if")    # 4 spaces indentation
print("This is outside if")       # No indentation
```

✅ **Rule:** All statements with the same indentation level belong to the same block.

❌ Wrong indentation → `IndentationError`

---

## 🔹 Taking User Input – Type Casting Reminder

```python
# input() always returns a STRING
age = input("Enter age: ")   # age is a string
print(type(age))             # <class 'str'>

# Convert to integer for comparison
age = int(input("Enter age: "))   # ✅ Correct
```

> ⚠️ Without `int()`, comparing string with number may give unexpected results.

---

## 📊 Quick Reference Table

| Statement | When to use | Example |
|-----------|-------------|---------|
| `if` | One optional block | Check eligibility |
| `if-else` | Two mutually exclusive blocks | Pass/Fail |
| `if-elif-else` | Multiple conditions | Grade calculation (A/B/C/D) |
| Nested `if` | Condition inside condition | License + car ownership |

---

## 🔹 Flow of Control – How Execution Moves

- Program runs **top to bottom**.
- When a condition is `True`, its block executes.
- After that block, control **skips** remaining conditions in that ladder.
- Then moves to code **outside** the conditional block.

```
Start → Check Condition → True → Execute Block → Continue
                      ↓
                    False → Skip Block → Continue
```

---

## ✅ Important Points for Exams/Interviews

1. **Indentation is mandatory** in Python – no curly braces.
2. **`elif`** (not `else if`) – Python uses `elif`.
3. **`else`** is optional and must be at the end.
4. **Nested if** – if inside another if, pay attention to indentation levels.
5. **`input()`** returns string – always type cast numbers.
6. **Comparison operators:** `>`, `<`, `>=`, `<=`, `==`, `!=`
7. **Logical operators:** `and`, `or`, `not` for combining conditions.

---

## 🧪 Practice Examples (Try Yourself)

```python
# Example 1: Simple if
marks = 85
if marks >= 90:
    print("Grade A")

# Example 2: if-else
num = 7
if num % 2 == 0:
    print("Even")
else:
    print("Odd")

# Example 3: if-elif-else
score = 75
if score >= 80:
    print("Distinction")
elif score >= 60:
    print("First Class")
elif score >= 40:
    print("Pass")
else:
    print("Fail")

# Example 4: Nested if
x = 10
if x > 0:
    if x % 2 == 0:
        print("Positive even number")
    else:
        print("Positive odd number")
```

**Outputs:**
- (Nothing – marks 85 < 90)
- `Odd`
- `First Class`
- `Positive even number`

---

## 🎯 Final Pro Tips

| You want to... | Use this |
|----------------|----------|
| Check one condition | `if` |
| Choose between two options | `if-else` |
| Choose among multiple options | `if-elif-else` |
| Check condition inside condition | Nested `if` |
| Get user input as number | `int(input())` |
| Compare two values | `==` (double equals) |

---

## 🚀 Summary

> **Conditional statements = Decision making in Python**  
> - `if` → one-way decision  
> - `if-else` → two-way decision  
> - `if-elif-else` → multi-way decision  
> - Nested `if` → hierarchical decision  
> - **Indentation** replaces curly braces  
> - **`input()`** always returns string → use type casting

---

Happy Coding! 🐍🔀  
You are now ready to answer any conditional statement question in exams and interviews. 💪
