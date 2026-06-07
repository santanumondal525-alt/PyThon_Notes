# 📊 Arithmetic Operations on NumPy Arrays
<sub>📺 <a href="https://youtu.be/NEF-AxaLAvI?si=Nm2a6ggfw9QaHKwI">Video Link</a></sub>
## 🔹 Why Use NumPy for Mathematical Operations?

> NumPy allows you to perform **element-wise mathematical operations** on arrays very efficiently, without writing explicit loops.

✅ **Important Rule:** For element-wise arithmetic operations, both arrays must have the **same shape** (same number of rows and columns).

---

## 🔹 Example Arrays Used

```python
import numpy as np

# Two 2x2 matrices
X = np.array([[1, 2],
              [3, 4]])

Y = np.array([[11, 12],
              [13, 14]])
```

**X:**
| 1 | 2 |
|---|---|
| 3 | 4 |

**Y:**
| 11 | 12 |
|----|----|
| 13 | 14 |

---

# 1. Addition (`+`)

Adds corresponding elements (element-wise).

```python
result = X + Y
print(result)
```

**Calculation:**
| Position | X | Y | Sum |
|----------|---|---|-----|
| (0,0) | 1 | 11 | 12 |
| (0,1) | 2 | 12 | 14 |
| (1,0) | 3 | 13 | 16 |
| (1,1) | 4 | 14 | 18 |

**Output:**
```
[[12, 14],
 [16, 18]]
```

> ✅ Addition is **commutative**: `X + Y` = `Y + X`

---

# 2. Subtraction (`-`)

Subtracts corresponding elements (element-wise).

```python
result = X - Y
print(result)
```

**Calculation (X - Y):**
| Position | X | Y | Difference |
|----------|---|---|------------|
| (0,0) | 1 | 11 | -10 |
| (0,1) | 2 | 12 | -10 |
| (1,0) | 3 | 13 | -10 |
| (1,1) | 4 | 14 | -10 |

**Output:**
```
[[-10, -10],
 [-10, -10]]
```

> ⚠️ Subtraction is **NOT commutative**: `X - Y` ≠ `Y - X`

```python
result = Y - X
print(result)   # [[10, 10], [10, 10]]
```

---

# 3. Multiplication (`*`) – Element-wise

Multiplies corresponding elements (element-wise, **NOT** matrix multiplication).

```python
result = X * Y
print(result)
```

**Calculation:**
| Position | X | Y | Product |
|----------|---|---|---------|
| (0,0) | 1 × 11 | = 11 |
| (0,1) | 2 × 12 | = 24 |
| (1,0) | 3 × 13 | = 39 |
| (1,1) | 4 × 14 | = 56 |

**Output:**
```
[[11, 24],
 [39, 56]]
```

> ✅ Element-wise multiplication is **commutative**: `X * Y` = `Y * X`

---

# 4. Matrix Multiplication (`@` or `np.matmul()`)

Performs **actual matrix multiplication** (dot product), NOT element-wise.

```python
result = X @ Y   # or np.matmul(X, Y)
print(result)
```

### How Matrix Multiplication Works:

For a 2×2 matrix:
```
X = [[a, b],    Y = [[e, f],
     [c, d]]         [g, h]]

X @ Y = [[a*e + b*g,  a*f + b*h],
         [c*e + d*g,  c*f + d*h]]
```

**Calculation with our values:**

| Output Position | Calculation | Result |
|----------------|-------------|--------|
| (0,0) | 1×11 + 2×13 = 11 + 26 | 37 |
| (0,1) | 1×12 + 2×14 = 12 + 28 | 40 |
| (1,0) | 3×11 + 4×13 = 33 + 52 | 85 |
| (1,1) | 3×12 + 4×14 = 36 + 56 | 92 |

**Output:**
```
[[37, 40],
 [85, 92]]
```

> ⚠️ Matrix multiplication is **NOT** the same as element-wise multiplication (`*`).

---

# 5. Division (`/`)

Divides corresponding elements (element-wise). Result is always **float**.

```python
result = Y / X
print(result)
```

**Calculation:**
| Position | Y | X | Quotient |
|----------|---|---|----------|
| (0,0) | 11 ÷ 1 | = 11.0 |
| (0,1) | 12 ÷ 2 | = 6.0 |
| (1,0) | 13 ÷ 3 | ≈ 4.333... |
| (1,1) | 14 ÷ 4 | = 3.5 |

**Output:**
```
[[11.0, 6.0],
 [4.333..., 3.5]]
```

> ⚠️ Division is **NOT commutative**: `X / Y` ≠ `Y / X`

---

# 6. Floor Division (`//`)

Divides and rounds **down** to the nearest integer.

```python
result = Y // X
print(result)
```

**Calculation:**
| Position | Y ÷ X | Floor | Standard Division |
|----------|-------|-------|-------------------|
| (0,0) | 11 ÷ 1 | 11 | 11.0 |
| (0,1) | 12 ÷ 2 | 6 | 6.0 |
| (1,0) | 13 ÷ 3 | 4 | 4.333... |
| (1,1) | 14 ÷ 4 | 3 | 3.5 |

**Output:**
```
[[11, 6],
 [4, 3]]
```

> 💡 Floor division removes the decimal part (always rounds down).

---

# 7. Exponentiation (`**`)

Raises each element to the given power.

```python
result = X ** 2
print(result)   # Square each element
```

**Calculation:**
- 1² = 1
- 2² = 4
- 3² = 9
- 4² = 16

**Output:** `[[1, 4], [9, 16]]`

### Exponentiation between two arrays:
```python
result = X ** Y   # Element-wise: X[i] raised to power Y[i]
print(result)
```

**Calculation:**
- 1¹¹ = 1
- 2¹² = 4096
- 3¹³ = 1594323
- 4¹⁴ = 268435456

---

# 8. Modulo (`%`) – Remainder

Returns the **remainder** after division (element-wise).

```python
result = Y % X
print(result)
```

**Calculation:**
| Position | Y ÷ X | Quotient | Remainder |
|----------|-------|----------|-----------|
| (0,0) | 11 ÷ 1 | 11 | 0 |
| (0,1) | 12 ÷ 2 | 6 | 0 |
| (1,0) | 13 ÷ 3 | 4 | 1 (13 - 12 = 1) |
| (1,1) | 14 ÷ 4 | 3 | 2 (14 - 12 = 2) |

**Output:**
```
[[0, 0],
 [1, 2]]
```

---

# 9. Transpose (`.T`)

Swaps rows and columns.

```python
result = X.T
print(result)
```

**Original X:**
| 1 | 2 |
|---|---|
| 3 | 4 |

**Transpose X.T:**
| 1 | 3 |
|---|---|
| 2 | 4 |

> 💡 `(m × n)` matrix becomes `(n × m)` after transpose.

---

## 📊 Complete Reference Table

| Operation | Operator/Method | Description | Commutative? |
|-----------|----------------|-------------|--------------|
| Addition | `X + Y` | Element-wise sum | ✅ Yes |
| Subtraction | `X - Y` | Element-wise difference | ❌ No |
| Multiplication | `X * Y` | Element-wise product | ✅ Yes |
| Matrix Multiplication | `X @ Y` or `np.matmul(X,Y)` | Dot product | ❌ No |
| Division | `X / Y` | Element-wise quotient (float) | ❌ No |
| Floor Division | `X // Y` | Integer division (rounds down) | ❌ No |
| Exponentiation | `X ** Y` | Power (element-wise) | ❌ No |
| Modulo | `X % Y` | Remainder after division | ❌ No |
| Transpose | `X.T` | Swap rows and columns | N/A |

---

## ✅ Important Points for Exams/Interviews

1. **Element-wise operations** require arrays of **same shape**.
2. **`*`** does element-wise multiplication, **NOT** matrix multiplication.
3. **`@`** or `np.matmul()` is used for **matrix multiplication**.
4. **Division (`/`)** always returns **float** numbers.
5. **Floor division (`//`)** returns integer (rounds down).
6. **Transpose (`.T`)** swaps rows ↔ columns.
7. Matrix multiplication is **NOT commutative**.
8. Exponentiation (`**`) raises each element to a power.

---

## 🧪 Practice Examples (Try Yourself)

```python
import numpy as np

A = np.array([[1, 2],
              [3, 4]])

B = np.array([[5, 6],
              [7, 8]])

# Try these:
print(A + B)      # ?
print(A - B)      # ?
print(A * B)      # ?
print(A @ B)      # ?
print(A / B)      # ?
print(B // A)     # ?
print(A ** 2)     # ?
print(A % B)      # ?
print(A.T)        # ?
```

**Answers:**
- `[[6,8], [10,12]]`
- `[[-4,-4], [-4,-4]]`
- `[[5,12], [21,32]]`
- `[[19,22], [43,50]]`
- `[[0.2, 0.333], [0.428, 0.5]]`
- `[[5,3], [2,2]]`
- `[[1,4], [9,16]]`
- `[[1,2], [3,4]]`
- `[[1,3], [2,4]]`

---

## 🎯 Final Pro Tips

| You want to... | Use this |
|----------------|----------|
| Add two arrays element-wise | `+` |
| Subtract arrays | `-` |
| Multiply element-wise | `*` |
| Matrix multiplication | `@` or `np.matmul()` |
| Divide (float result) | `/` |
| Integer division (floor) | `//` |
| Remainder after division | `%` |
| Power/exponentiation | `**` |
| Swap rows and columns | `.T` |

---

## 🚀 Summary

> **NumPy Arithmetic Operations = Fast, element-wise calculations without loops**
> - `+` = addition
> - `-` = subtraction
> - `*` = element-wise multiplication
> - `@` = matrix multiplication (dot product)
> - `/` = division (float)
> - `//` = floor division (integer)
> - `**` = exponentiation
> - `%` = modulo (remainder)
> - `.T` = transpose

```python
# Quick visual
import numpy as np

A = np.array([[1, 2], [3, 4]])
B = np.array([[5, 6], [7, 8]])

print(A + B)   # [[6,8], [10,12]]
print(A * B)   # [[5,12], [21,32]] (element-wise)
print(A @ B)   # [[19,22], [43,50]] (matrix multiplication)
print(A.T)     # [[1,3], [2,4]]
```

---

Happy Coding! 🐍📊  
You are now ready to answer any question on NumPy array arithmetic operations in exams and interviews. 💪
