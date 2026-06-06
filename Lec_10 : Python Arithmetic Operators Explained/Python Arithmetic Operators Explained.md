# ➕ Arithmetic Operators in Python
<sub>📺 <a href="https://youtu.be/LEhXy-oBn6U?si=ze6OwbNO5XuhWqjD">Video Link</a></sub>

### Introduction

Arithmetic operators are the most basic operators we use **daily** — in math and in programming. Every programming language (C, C++, Java, Python) supports them.

---

## 1. 📋 List of Arithmetic Operators

| Operator | Name | Example | Result |
| :---: | :--- | :--- | :---: |
| `+` | Addition | `5 + 4` | `9` |
| `-` | Subtraction | `10 - 3` | `7` |
| `*` | Multiplication | `5 * 4` | `20` |
| `/` | Division (Float) | `15 / 4` | `3.75` |
| `//` | Floor Division | `15 // 4` | `3` |
| `%` | Modulus (Remainder) | `10 % 3` | `1` |
| `**` | Exponentiation (Power) | `2 ** 3` | `8` |

> These are **binary operators** — they need **two operands** (one on the left, one on the right).

---

## 2. 📝 Detailed Explanation of Each Operator

### 2.1 Addition (`+`)

```python
print(5 + 4)    # Output: 9
```

---

### 2.2 Subtraction (`-`)

```python
print(10 - 3)    # Output: 7
```

---

### 2.3 Multiplication (`*`)

```python
print(5 * 4)    # Output: 20
```

---

### 2.4 Division (`/`) — Always Returns Float

```python
print(15 / 4)    # Output: 3.75
```

> Normal division **always returns a float value**, even if the numbers divide perfectly.

---

### 2.5 Floor Division (`//`)

Floor division gives the **lower integer** value, cutting off everything after the decimal point.

```python
print(15 // 4)    # Output: 3
```

| Expression | Normal Division | Floor Division |
| :--- | :---: | :---: |
| `15 / 4` | `3.75` | `3` |
| `10 / 3` | `3.33` | `3` |
| `20 / 3` | `6.67` | `6` |

> **Rule:** Floor division always returns the **floor value** (the nearest lower integer). It simply **removes the decimal part**.

---

### 2.6 Modulus (`%`) — Remainder

Modulus gives the **remainder** after division.

```python
print(10 % 2)    # Output: 0   (10 is perfectly divisible by 2)
print(10 % 3)    # Output: 1   (3 × 3 = 9, remainder = 1)
```

### Special Cases of Modulus:

| Expression | Result | Rule |
| :--- | :---: | :--- |
| `Any Number % 1` | `0` | Dividing by 1 always leaves remainder 0 |
| `Any Number % 0` | **Error** ❌ | Division by zero is **ZeroDivisionError** — not allowed |

```python
print(10 % 1)     # Output: 0
print(10 % 0)     # ZeroDivisionError ❌
```

---

### 2.7 Exponentiation (`**`) — Power

```python
print(2 ** 3)    # Output: 8  (2³ = 2 × 2 × 2)
print(3 ** 2)    # Output: 9  (3² = 3 × 3)
```

---

## 3. 📊 Precedence of Arithmetic Operators

When multiple operators appear in one expression, **precedence** decides which is evaluated first.

| Priority | Operator(s) | 
| :---: | :--- |
| **Highest** 🔼 | `**` (Exponentiation) |
| ⬆️ | `*`, `/`, `//`, `%` (All have **equal** precedence) |
| **Lowest** 🔽 | `+`, `-` (Both have **equal** precedence) |

---

## 4. 🔄 Associativity of Arithmetic Operators

When operators have the **same precedence**, associativity decides the direction.

| Operator | Associativity |
| :--- | :---: |
| `**` (Exponentiation) | **Right to Left** ⬅️ |
| `*`, `/`, `//`, `%` | Left to Right ➡️ |
| `+`, `-` | Left to Right ➡️ |

> **Exception to remember:** Only `**` is **Right to Left**. Everything else is **Left to Right**.

---

## 5. 📝 Full Expression Example (Step-by-Step)

**Expression:**
```python
2 ** 4 // 3 * 2 + 3 - 5
```

### Step-by-Step Evaluation:

| Step | Operator | Expression | Result So Far |
| :---: | :--- | :--- | :--- |
| **1** | `**` (highest precedence) | `2 ** 4` | `16` |
| | Expression becomes | `16 // 3 * 2 + 3 - 5` | |
| **2** | `//` and `*` (equal precedence, Left → Right) | `16 // 3` | `5` |
| | Expression becomes | `5 * 2 + 3 - 5` | |
| **3** | `*` (next in Left → Right) | `5 * 2` | `10` |
| | Expression becomes | `10 + 3 - 5` | |
| **4** | `+` and `-` (equal precedence, Left → Right) | `10 + 3` | `13` |
| | Expression becomes | `13 - 5` | |
| **5** | `-` | `13 - 5` | **`8`** ✅ |

---

### Visual Breakdown:

```
2 ** 4 // 3 * 2 + 3 - 5
   ↓
 16 // 3 * 2 + 3 - 5
      ↓
   5 * 2 + 3 - 5
        ↓
    10 + 3 - 5
         ↓
      13 - 5
          ↓
        8 ✅
```

---

## 6. 📊 Summary Table

| Operator | Name | Precedence | Associativity |
| :---: | :--- | :---: | :---: |
| `**` | Exponentiation | Highest | Right to Left ⬅️ |
| `*` | Multiplication | Medium | Left to Right ➡️ |
| `/` | Division | Medium | Left to Right ➡️ |
| `//` | Floor Division | Medium | Left to Right ➡️ |
| `%` | Modulus | Medium | Left to Right ➡️ |
| `+` | Addition | Lowest | Left to Right ➡️ |
| `-` | Subtraction | Lowest | Left to Right ➡️ |

---

## 7. 📝 Key Takeaways

| Point | Details |
| :--- | :--- |
| **Binary Operators** | Need two operands (one on each side) |
| **Normal Division `/`** | Always returns float |
| **Floor Division `//`** | Removes decimal, gives lower integer |
| **Modulus `%`** | Gives remainder after division |
| **Modulus with 1** | Always returns 0 |
| **Modulus with 0** | ZeroDivisionError ❌ |
| **`**` is Right to Left** | Only arithmetic operator with Right to Left associativity |
| **All others** | Left to Right |
| **Exam Tip** | Questions mixing `**`, `//`, `*`, `+`, `-` test both precedence and associativity |

---

**Now you can solve any arithmetic operator question easily!** ➕
