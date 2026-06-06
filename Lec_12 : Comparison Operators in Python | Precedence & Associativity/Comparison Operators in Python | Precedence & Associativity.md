# 🔍 Comparison (Relational) Operators in Python
<sub>📺 <a href="https://youtu.be/ri4UgDJcwVU?si=vtvAWEzie3jSj-VX">Video Link</a></sub>

### Introduction

As the name suggests, **Comparison Operators** are used to **compare two values**. We do this daily in real life:

| Real-Life Scenario | Comparison |
| :--- | :--- |
| 🛒 Shopping | Comparing prices of two products |
| 💼 Job Selection | Comparing salary packages |
| 🏏 Sports | Comparing team scores |
| 🏠 Home Budget | Comparing income vs expenses |
| 📊 Business | Comparing revenue figures |

---

## 1. 🎯 What are Comparison Operators?

> Comparison operators compare two values and **always return a Boolean result**: either `True` or `False`.

| Comparison vs Arithmetic | |
| :--- | :--- |
| **Arithmetic** (`+`, `-`, `*`) | Returns a **numeric value** (e.g., `10 + 5 = 15`) |
| **Comparison** (`>`, `<`, `==`) | Returns a **Boolean value** (`True` or `False`) |

---

## 2. 📋 List of Comparison Operators

| Operator | Meaning | Example | Result |
| :---: | :--- | :--- | :---: |
| `==` | Equal to | `1 == 2` | `False` |
| `!=` | Not equal to | `1 != 2` | `True` |
| `>` | Greater than | `10 > 5` | `True` |
| `<` | Less than | `10 < 5` | `False` |
| `>=` | Greater than or equal to | `5 >= 5` | `True` |
| `<=` | Less than or equal to | `5 <= 5` | `True` |

---

## 3. 📝 Detailed Examples

### 3.1 Equal to (`==`)

```python
print(1 == 2)       # False ❌
print(5 == 5)       # True ✅
print(True == False)  # False ❌
```

### 3.2 Not Equal to (`!=`)

```python
print(1 != 2)       # True ✅
print(1 != 1)       # False ❌
```

### 3.3 Greater Than (`>`)

```python
print(10 > 5)       # True ✅
print(5 > 5)        # False ❌ (5 is not greater than 5, it's equal)
print(5 > 10)       # False ❌
```

### 3.4 Less Than (`<`)

```python
print(10 < 5)       # False ❌
print(5 < 10)       # True ✅
```

### 3.5 Greater Than or Equal To (`>=`)

```python
print(5 >= 5)       # True ✅ (5 is equal to 5)
print(10 >= 5)      # True ✅
print(3 >= 5)       # False ❌
```

### 3.6 Less Than or Equal To (`<=`)

```python
print(5 <= 5)       # True ✅
print(3 <= 5)       # True ✅
print(10 <= 5)      # False ❌
```

---

## 4. 📊 Precedence of Comparison Operators

When comparison operators appear with other operators, precedence matters.

| Priority | Operators |
| :---: | :--- |
| **Higher** 🔼 | `>`, `<`, `>=`, `<=` (All have **equal** precedence) |
| **Lower** 🔽 | `==`, `!=` (Both have **equal** precedence) |

> **Rule:** `>`, `<`, `>=`, `<=` are evaluated **before** `==` and `!=`.

---

## 5. 🔄 Associativity of Comparison Operators

| Operators | Associativity |
| :--- | :---: |
| All Comparison Operators | **Left to Right** ➡️ |

> No exceptions here — all comparison operators follow Left to Right.

---

## 6. 📝 Example: Solving with Precedence

### Example 1:

```python
print(4 > 6 == False)
```

### Step-by-Step Evaluation:

| Step | Operation | Explanation | Result |
| :---: | :--- | :--- | :--- |
| **1** | `4 > 6` | `>` has higher precedence than `==`, so this is evaluated first. Is 4 greater than 6? | `False` |
| **2** | Expression becomes | `False == False` | |
| **3** | `False == False` | Are both sides equal? Yes! | **`True`** ✅ |

**Final Output:** `True`

---

### Example 2: Same Operator, Multiple Times (Associativity)

```python
print(True == True == False)
```

| Step | Operation | Explanation | Result |
| :---: | :--- | :--- | :--- |
| **1** | `True == True` | Left to Right. Is True equal to True? | `True` |
| **2** | Expression becomes | `True == False` | |
| **3** | `True == False` | Is True equal to False? No! | **`False`** ❌ |

**Final Output:** `False`

---

## 7. 📊 Summary Table

| Operator | Meaning | Example | Result |
| :---: | :--- | :--- | :---: |
| `==` | Equal to | `5 == 5` | `True` |
| `!=` | Not equal to | `5 != 3` | `True` |
| `>` | Greater than | `10 > 5` | `True` |
| `<` | Less than | `3 < 5` | `True` |
| `>=` | Greater than or equal | `5 >= 5` | `True` |
| `<=` | Less than or equal | `5 <= 5` | `True` |

---

## 8. 📐 Precedence & Associativity Summary

| Operators | Precedence | Associativity |
| :--- | :---: | :---: |
| `>`, `<`, `>=`, `<=` | Higher ⬆️ | Left to Right ➡️ |
| `==`, `!=` | Lower ⬇️ | Left to Right ➡️ |

---

## 9. 📝 Key Takeaways

| Point | Details |
| :--- | :--- |
| **Returns Boolean** | Comparison operators **always** return `True` or `False` |
| **Not Arithmetic** | Unlike `+`, `-`, `*`, comparison doesn't produce a number |
| **6 Operators** | `==`, `!=`, `>`, `<`, `>=`, `<=` |
| **Precedence Rule** | `>`, `<`, `>=`, `<=` are evaluated before `==`, `!=` |
| **Associativity** | All are **Left to Right** |
| **Capitalization** | `True` and `False` must have capital first letters |
| **Exam Tip** | Questions mixing `>` with `==` test your understanding of precedence |

---

**Now you can compare any values in Python with confidence!** 🔍
