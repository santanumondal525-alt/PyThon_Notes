# 📐 Operator Precedence & Associativity in Python
<sub>📺 <a href="https://youtu.be/3HKdkws6YxQ?si=1sQXKJDsEj1sdUSN">Video Link</a></sub>

### Why Is This Important?

When we solve expressions in Python with multiple operators, we must know:
1. **Precedence** — Which operator is evaluated first?
2. **Associativity** — If operators have the same precedence, in which direction do we evaluate?

> Questions on this topic are frequently asked in **interviews, college exams, and competitive exams**.

---

## 1. 🎯 What is Operator Precedence?

**Precedence** defines the priority of operators. Higher precedence operators are evaluated **first**.

### Precedence Table (Highest to Lowest)

| Priority | Operator Type | Operators |
| :---: | :--- | :--- |
| **Highest** 🔼 | Parentheses | `()` |
| | Exponentiation | `**` |
| | Unary Operators | `+x`, `-x`, `~x` |
| | Multiplication, Division, Floor Div, Modulus | `*`, `/`, `//`, `%` |
| | Addition, Subtraction | `+`, `-` |
| | Bitwise Shift | `<<`, `>>` |
| | Bitwise AND | `&` |
| | Bitwise XOR | `^` |
| | Bitwise OR | `\|` |
| | Comparison | `==`, `!=`, `>`, `<`, `>=`, `<=` |
| | Logical NOT | `not` |
| | Logical AND | `and` |
| **Lowest** 🔽 | Logical OR | `or` |

> **Rule:** As you go **down** the table, precedence **decreases**. Higher in the table = higher priority.

---

## 2. 📝 Example 1: Arithmetic Precedence

**Expression:**
```python
2 + 3 * 4
```

| Approach | Steps | Result |
| :--- | :--- | :---: |
| **Wrong Way** ❌ | `(2 + 3) * 4` = `5 * 4` | `20` |
| **Right Way** ✅ | `2 + (3 * 4)` = `2 + 12` | `14` |

### Why?

| Operator | Precedence |
| :--- | :---: |
| `*` (Multiplication) | Higher ⬆️ |
| `+` (Addition) | Lower ⬇️ |

> `*` has higher precedence than `+`, so `3 * 4` is evaluated **first**.

**Correct Answer: `14`** ✅

---

## 3. 📝 Example 2: Logical Operators Precedence

**Expression:**
```python
False and False or True
```

### Scenario A (Wrong — evaluates `and` first incorrectly):
```
False and False = False
False or True = True    → Output: True
```

### Scenario B (Wrong — evaluates `or` first):
```
False or True = True
False and True = False    → Output: False
```

### Which is Correct?

| Operator | Precedence |
| :--- | :---: |
| `and` | Higher ⬆️ |
| `or` | Lower ⬇️ |

> `and` has higher precedence than `or`, so `False and False` is evaluated **first**.

### Correct Evaluation:
```
Step 1: False and False → False
Step 2: False or True    → True
```

**Correct Answer: `True`** ✅

---

## 4. 🔄 What is Associativity?

When two operators have the **same precedence**, **associativity** decides the direction of evaluation.

| Associativity | Direction | Operators |
| :--- | :---: | :--- |
| **Left to Right** ➡️ | Evaluate from left | Almost **all operators** except the two below |
| **Right to Left** ⬅️ | Evaluate from right | `**` (Exponentiation) and `=` (Assignment) |

> **You ONLY need to remember 2 exceptions:**
> 1. `**` (Exponentiation) — Right to Left
> 2. `=` (Assignment) — Right to Left
> 
> **All other operators are Left to Right.**

---

## 5. 📝 Example 3: Exponentiation Associativity (`**`)

**Expression:**
```python
2 ** 3 ** 2
```

### This is interpreted as:
```
2 ** (3 ** 2)     ← Right to Left
```

| Approach | Steps | Result |
| :--- | :--- | :---: |
| **Right to Left** ✅ | `3 ** 2 = 9` → `2 ** 9` | `512` |
| **Left to Right** ❌ | `2 ** 3 = 8` → `8 ** 2` | `64` |

> `**` is **Right to Left**, so the rightmost exponentiation is done first.

**Correct Answer: `512`** ✅

---

## 6. 📝 Example 4: Assignment Associativity (`=`)

**Expression:**
```python
a = b += c
```

Let's assume:
```python
a = 5
b = 2
c = 3
```

### How It Works (Right to Left):

| Step | Explanation |
| :--- | :--- |
| 1 | `b += c` means `b = b + c` |
| 2 | `b = 2 + 3` → `b = 5` |
| 3 | `a = b` → `a = 5` |

> Assignment evaluates from **Right to Left**. First the right side is computed, then assigned to the left.

---

## 7. 📊 Complete Summary Table

| Category | Operators | Precedence | Associativity |
| :--- | :--- | :---: | :---: |
| Parentheses | `()` | **Highest** 🔼 | Left to Right |
| Exponentiation | `**` | ⬆️ | **Right to Left** ⬅️ |
| Unary | `+`, `-`, `~` | ⬆️ | Right to Left |
| Mul/Div/Mod | `*`, `/`, `//`, `%` | ⬆️ | Left to Right |
| Add/Sub | `+`, `-` | ⬆️ | Left to Right |
| Bitwise Shift | `<<`, `>>` | ⬆️ | Left to Right |
| Bitwise AND | `&` | ⬆️ | Left to Right |
| Bitwise XOR | `^` | ⬆️ | Left to Right |
| Bitwise OR | `\|` | ⬆️ | Left to Right |
| Comparison | `==`, `!=`, `<`, `>`, etc. | ⬆️ | Left to Right |
| Logical NOT | `not` | ⬆️ | Left to Right |
| Logical AND | `and` | ⬆️ | Left to Right |
| Logical OR | `or` | **Lowest** 🔽 | Left to Right |
| Assignment | `=`, `+=`, `-=`, etc. | Lowest | **Right to Left** ⬅️ |

---

## 8. 🧠 Quick Memory Trick

| Rule | Details |
| :--- | :--- |
| **All Left to Right** ➡️ | Almost every operator — no need to memorize a list |
| **ONLY 2 Right to Left** ⬅️ | `**` (Exponentiation) and `=` (Assignment) |
| **Higher in Table** | Higher precedence — evaluated first |

> **Don't memorize the whole table.** Just remember: everything is **Left to Right** except `**` and `=` which are **Right to Left**.

---

## 9. 📝 Key Takeaways

| Point | Details |
| :--- | :--- |
| **Precedence** | Determines which operator is evaluated first in an expression |
| **Associativity** | Determines direction when operators have same precedence |
| **`**` Associativity** | Right to Left (unique in Python among arithmetic operators) |
| **Assignment Associativity** | Right to Left |
| **All Other Operators** | Left to Right |
| **Exam Tip** | Questions mixing `**` with other operators are very common — always remember Right to Left for `**` |

---

**Now you can solve any operator precedence question easily!** 📐
