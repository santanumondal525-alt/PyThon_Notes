# 🔣 Logical Operators in Python
<sub>📺 <a href="https://youtu.be/M-JKYzxgHCo?si=D7McmKyU_HoOBPJG">Video Link</a></sub>

### Introduction: Logical vs Bitwise Operators

When working with Boolean values (`True` / `False`), Python provides two types of operators:

| Type | Works On | Scope |
| :--- | :--- | :--- |
| **Bitwise** 🔢 | Individual **bits** | Operates on each bit separately |
| **Logical** 🧠 | Entire **statement/expression** | Works on the overall **truth value** of the whole expression |

> **Logical Operators** check whether a complete statement returns `True` or `False`.

---

## 1. 📋 The Three Logical Operators

Python has exactly **three** logical operators:

| Operator | Keyword | Meaning |
| :---: | :--- | :--- |
| AND | `and` | Returns `True` only if **both** operands are `True` |
| OR | `or` | Returns `True` if **at least one** operand is `True` |
| NOT | `not` | Returns the **opposite** Boolean value |

---

## 2. 📊 Precedence of Logical Operators

| Priority | Operator |
| :---: | :--- |
| **Highest** 🔼 | `not` |
| ⬆️ | `and` |
| **Lowest** 🔽 | `or` |

> **`not`** is evaluated first, then **`and`**, then **`or`**.

---

## 3. 📝 Detailed Explanation with Examples

### 3.1 AND (`and`) Operator

**Rule:** Returns `True` **only if BOTH operands are `True`**. Otherwise returns `False`.

| Operand 1 | Operand 2 | Result |
| :---: | :---: | :---: |
| `True` | `True` | `True` ✅ |
| `True` | `False` | `False` ❌ |
| `False` | `True` | `False` ❌ |
| `False` | `False` | `False` ❌ |

### Example:

```python
age = 25
income = 20000

if age >= 18 and income >= 15000:
    print("Eligible for the loan")
else:
    print("Not Eligible")
```

| Age | Income | `age >= 18` | `income >= 15000` | `and` Result | Output |
| :---: | :---: | :---: | :---: | :---: | :--- |
| 15 | 20000 | `False` | `True` | **`False`** ❌ | "Not Eligible" |
| 25 | 20000 | `True` | `True` | **`True`** ✅ | "Eligible for the loan" |
| 25 | 10000 | `True` | `False` | **`False`** ❌ | "Not Eligible" |

> **Both conditions must be true** for the overall result to be `True`.

---

### 3.2 OR (`or`) Operator

**Rule:** Returns `True` if **AT LEAST ONE** operand is `True`. Returns `False` only if **both** are `False`.

| Operand 1 | Operand 2 | Result |
| :---: | :---: | :---: |
| `True` | `True` | `True` ✅ |
| `True` | `False` | `True` ✅ |
| `False` | `True` | `True` ✅ |
| `False` | `False` | `False` ❌ |

### Example:

```python
age = 15
income = 20000

if age >= 18 or income >= 15000:
    print("Eligible for the loan")
else:
    print("Not Eligible")
```

| Age | Income | `age >= 18` | `income >= 15000` | `or` Result | Output |
| :---: | :---: | :---: | :---: | :---: | :--- |
| 15 | 20000 | `False` | `True` | **`True`** ✅ | "Eligible for the loan" |
| 15 | 10000 | `False` | `False` | **`False`** ❌ | "Not Eligible" |

> **Only one condition needs to be true** for the overall result to be `True`.

---

### 3.3 NOT (`not`) Operator

**Rule:** Returns the **opposite** Boolean value of the operand.

| Operand | `not` Result |
| :---: | :---: |
| `True` | `False` ❌ |
| `False` | `True` ✅ |

### Example:

```python
a = True
b = False

if not a:
    print("This statement will NOT be executed")
else:
    print("a is True, so not a is False")

if not b:
    print("My name is B")    # This will execute
else:
    print("b is False, so not b is True")
```

| Variable | Value | `not` Result | Which Block Executes? |
| :---: | :---: | :---: | :--- |
| `a` | `True` | `False` | `else` block |
| `b` | `False` | `True` | `if` block → "My name is B" |

---

## 4. 📊 AND vs OR — Quick Comparison

| Feature | `and` | `or` |
| :--- | :--- | :--- |
| Returns `True` when | **Both** are `True` | **At least one** is `True` |
| Returns `False` when | **Any one** is `False` | **Both** are `False` |
| Use Case | All conditions must be met | Any one condition is enough |

---

## 5. 🎯 Where Are Logical Operators Used?

Logical operators are mainly used in:

| Area | Example |
| :--- | :--- |
| **Control Statements** | `if`, `elif`, `else` |
| **Loops** | `while` conditions |
| **Complex Conditions** | Combining multiple comparisons |

---

## 6. 📝 Truth Table Summary

### AND Truth Table:

| A | B | A `and` B |
| :---: | :---: | :---: |
| T | T | **T** |
| T | F | F |
| F | T | F |
| F | F | F |

### OR Truth Table:

| A | B | A `or` B |
| :---: | :---: | :---: |
| T | T | **T** |
| T | F | **T** |
| F | T | **T** |
| F | F | F |

### NOT Truth Table:

| A | `not` A |
| :---: | :---: |
| T | F |
| F | T |

---

## 7. 📝 Key Takeaways

| Point | Details |
| :--- | :--- |
| **3 Logical Operators** | `and`, `or`, `not` |
| **`and`** | True only if **both** are True |
| **`or`** | True if **at least one** is True |
| **`not`** | Flips the Boolean value |
| **Precedence** | `not` > `and` > `or` |
| **Scope** | Works on **entire expression's truth value**, not individual bits |
| **Use Cases** | `if` conditions, `while` loops, combining multiple conditions |
| **Exam Tip** | Know the difference between Bitwise (`&`, `|`) and Logical (`and`, `or`) operators |

---

**Now you understand all three Logical Operators in Python!** 🔣
