# 🔢 Bitwise Operators in Python
<sub>📺 <a href="https://youtu.be/Yk3Jwm5YuFs?si=fVJ41ok1ILKdnhdn">Video Link</a></sub>

### Introduction

As the name suggests, **Bitwise Operators** perform operations on **each individual bit** of binary numbers.

> Bitwise operators in Python are used to perform operations on **individual bits** of binary numbers.

| If you get a decimal number | Convert it to binary first |
| :--- | :--- |
| `5` (decimal) | `0101` (binary) |
| `4` (decimal) | `0100` (binary) |

> The system automatically converts numbers to binary internally. You just need to understand the bit-by-bit comparison.

---

## 1. 📋 The Six Bitwise Operators

| Operator | Name | Symbol |
| :---: | :--- | :---: |
| 1 | Bitwise AND | `&` |
| 2 | Bitwise OR | `\|` |
| 3 | Bitwise NOT (Complement) | `~` |
| 4 | Bitwise XOR | `^` |
| 5 | Bitwise Left Shift | `<<` |
| 6 | Bitwise Right Shift | `>>` |

---

## 2. 📊 Precedence & Associativity

| Priority | Operator(s) | Associativity |
| :---: | :--- | :---: |
| **Highest** 🔼 | `~` (NOT) | Left to Right |
| ⬆️ | `<<`, `>>` (Shift) | Left to Right |
| ⬆️ | `&` (AND) | Left to Right |
| ⬆️ | `^` (XOR) | Left to Right |
| **Lowest** 🔽 | `\|` (OR) | Left to Right |

> All bitwise operators have **Left to Right** associativity.

---

## 3. 📝 Binary Number Representation in Python

| Prefix | Represents | Example |
| :---: | :--- | :--- |
| `0b` | Binary | `0b1010` |
| `0o` | Octal | `0o12` |
| `0x` | Hexadecimal | `0xA` |

```python
a = 0b1010    # Binary representation of 10
b = 0b1100    # Binary representation of 12
```

---

## 4. 📝 Detailed Explanation of Each Operator

### 4.1 Bitwise AND (`&`)

**Rule:** Returns `1` only if **both bits are `1`**. Otherwise returns `0`.

| Bit 1 | Bit 2 | Result |
| :---: | :---: | :---: |
| 0 | 0 | 0 |
| 0 | 1 | 0 |
| 1 | 0 | 0 |
| 1 | 1 | **1** |

### Example:

```python
a = 0b1010    # 10
b = 0b1100    # 12
print(a & b)  # Output: 8 (0b1000)
```

### Step-by-Step:

```
  1 0 1 0   (10)
& 1 1 0 0   (12)
-----------
  1 0 0 0   (8)
```

| Bit Position | Bit from A | Bit from B | AND Result |
| :---: | :---: | :---: | :---: |
| 3rd | 1 | 1 | **1** |
| 2nd | 0 | 1 | 0 |
| 1st | 1 | 0 | 0 |
| 0th | 0 | 0 | 0 |

**Result:** `0b1000` = `8`

---

### 4.2 Bitwise OR (`|`)

**Rule:** Returns `1` if **at least one bit is `1`**. Returns `0` only if both are `0`.

| Bit 1 | Bit 2 | Result |
| :---: | :---: | :---: |
| 0 | 0 | 0 |
| 0 | 1 | **1** |
| 1 | 0 | **1** |
| 1 | 1 | **1** |

### Example:

```python
a = 0b1010    # 10
b = 0b1100    # 12
print(a | b)  # Output: 14 (0b1110)
```

### Step-by-Step:

```
  1 0 1 0   (10)
| 1 1 0 0   (12)
-----------
  1 1 1 0   (14)
```

**Result:** `0b1110` = `14`

---

### 4.3 Bitwise XOR (`^`)

**Rule:** Returns `1` if bits are **different**. Returns `0` if bits are **same**.

| Bit 1 | Bit 2 | Result |
| :---: | :---: | :---: |
| 0 | 0 | 0 |
| 0 | 1 | **1** |
| 1 | 0 | **1** |
| 1 | 1 | 0 |

### Example:

```python
a = 0b1010    # 10
b = 0b1100    # 12
print(a ^ b)  # Output: 6 (0b0110)
```

### Step-by-Step:

```
  1 0 1 0   (10)
^ 1 1 0 0   (12)
-----------
  0 1 1 0   (6)
```

**Result:** `0b0110` = `6`

---

### 4.4 Bitwise NOT (`~`) — Complement

**Rule:** Flips every bit — `0` becomes `1`, `1` becomes `0`.

> **Important:** Python uses **Two's Complement** to represent negative numbers internally.

### Example:

```python
a = 0b1010    # 10
print(~a)     # Output: -11
```

### Why does `~10` give `-11`?

| Step | Action | Result |
| :---: | :--- | :--- |
| 1 | Original number (32-bit): `0000...1010` (10) | Positive (sign bit = 0) |
| 2 | Apply NOT: Flip all bits | `1111...0101` (Negative, sign bit = 1) |
| 3 | This is in Two's Complement form | To find the value, take 2's complement again |
| 4 | 1's complement of `...0101` | `...1010` |
| 5 | Add 1 | `...1011` = 11 |
| 6 | Original sign was negative | **-11** |

### Quick Formula:

```
~n = -(n + 1)
```

| Input (n) | `~n` Result |
| :---: | :---: |
| `10` | `-11` |
| `11` | `-12` |
| `50` | `-51` |
| `0` | `-1` |

```python
print(~10)    # -11
print(~11)    # -12
print(~50)    # -51
```

---

### 4.5 Left Shift (`<<`)

**Rule:** Shifts all bits to the **left** by the specified number of positions. **Adds zeros** on the right.

> **Formula:** `n << k` = `n × 2ᵏ`

### Example: `10 << 2`

```python
a = 0b1010    # 10
print(a << 2) # Output: 40
```

### Step-by-Step:

```
Shift 1:
  1010.  → shift left
 10100   → add 0 on right
 = 20    (10 × 2)

Shift 2:
 10100.  → shift left
101000   → add 0 on right
= 40     (20 × 2)
```

| Original | After 1 Left Shift | After 2 Left Shifts |
| :---: | :---: | :---: |
| `10` | `20` (10 × 2) | `40` (20 × 2) |

> Each left shift **multiplies by 2**.

---

### 4.6 Right Shift (`>>`)

**Rule:** Shifts all bits to the **right** by the specified number of positions. Bits shifted out are lost.

> **Formula:** `n >> k` = `n ÷ 2ᵏ` (integer division)

### Example: `10 >> 1`

```python
a = 0b1010    # 10
print(a >> 1) # Output: 5
```

### Step-by-Step:

```
Original:
  1010 = 10
Shift right by 1:
  0101. → rightmost 0 falls off
  0101 = 5 (10 ÷ 2)
```

| Original | After 1 Right Shift | After 2 Right Shifts |
| :---: | :---: | :---: |
| `10` | `5` (10 ÷ 2) | `2` (5 ÷ 2) |

> Each right shift **divides by 2** (floor division).

---

## 5. 📊 Shift Operations Summary

| Operation | Symbol | Effect | Example | Result |
| :--- | :---: | :--- | :---: | :---: |
| Left Shift | `<<` | Multiply by 2ᵏ | `10 << 2` | `40` |
| Right Shift | `>>` | Divide by 2ᵏ | `10 >> 1` | `5` |

---

## 6. 🎯 Solving Mixed Bitwise Expressions (Using Precedence)

### Example:

```python
0b1010 & 0b1100 | 0b0011
```

| Step | Operation | Explanation |
| :---: | :--- | :--- |
| **1** | `&` has higher precedence than `\|` | Do `0b1010 & 0b1100` first |
| | `0b1010 & 0b1100` = `0b1000` | AND operation |
| **2** | Expression becomes `0b1000 \| 0b0011` | |
| | `0b1000 \| 0b0011` = `0b1011` | OR operation |

**Final Answer:** `0b1011` = `11`

### Visual:

```
Step 1 (AND - higher precedence):
  1 0 1 0
& 1 1 0 0
---------
  1 0 0 0

Step 2 (OR - lower precedence):
  1 0 0 0
| 0 0 1 1
---------
  1 0 1 1 = 11
```

---

## 7. 📊 Complete Bitwise Operators Summary

| Operator | Symbol | Rule | Example | Result |
| :--- | :---: | :--- | :---: | :---: |
| AND | `&` | 1 only if both 1 | `0b1010 & 0b1100` | `0b1000` (8) |
| OR | `\|` | 1 if at least one 1 | `0b1010 \| 0b1100` | `0b1110` (14) |
| XOR | `^` | 1 if bits different | `0b1010 ^ 0b1100` | `0b0110` (6) |
| NOT | `~` | Flip all bits | `~10` | `-11` |
| Left Shift | `<<` | Multiply by 2ᵏ | `10 << 2` | `40` |
| Right Shift | `>>` | Divide by 2ᵏ | `10 >> 1` | `5` |

---

## 8. 📝 Key Takeaways

| Point | Details |
| :--- | :--- |
| **Bitwise = Bit-by-Bit** | Operations performed on each individual bit |
| **6 Operators** | `&`, `\|`, `^`, `~`, `<<`, `>>` |
| **NOT Formula** | `~n = -(n + 1)` |
| **Left Shift** | `n << k = n × 2ᵏ` |
| **Right Shift** | `n >> k = n ÷ 2ᵏ` |
| **Two's Complement** | Used internally for negative numbers in NOT operation |
| **Precedence** | `~` > `<<` `>>` > `&` > `^` > `\|` |
| **Associativity** | All Left to Right |
| **Exam Tip** | NOT operation and precedence-based mixed expressions are common interview questions |

---

**Now you understand all Bitwise Operators in Python!** 🔢
