# 📊 NumPy Statistical Functions
<sub>📺 <a href="https://youtu.be/mAqR1Hlh9yY?si=JR2SI2557k16Oc78">Video Link</a></sub>
## 🔹 Why Use NumPy for Statistics?

> NumPy provides **built-in statistical functions** that make it very easy to perform mathematical and statistical operations on numerical data without writing loops.

✅ These functions are **fast, efficient, and simple** to use.

---

## 🔹 Example Array Used

```python
import numpy as np

X = np.array([4, 2, 3, 9, 7])
```

**Array:** `[4, 2, 3, 9, 7]`
- Total elements = 5

---

# 1. `max()` – Maximum Value 📈

Returns the **largest** element in the array.

```python
max_value = np.max(X)
print(max_value)   # Output: 9
```

**How it works:** Scans the entire array and finds the maximum value.

---

# 2. `min()` – Minimum Value 📉

Returns the **smallest** element in the array.

```python
min_value = np.min(X)
print(min_value)   # Output: 2
```

---

# 3. `sum()` – Sum of All Elements ➕

Returns the **total** of all elements in the array.

```python
total = np.sum(X)
print(total)   # Output: 4 + 2 + 3 + 9 + 7 = 25
```

---

# 4. `mean()` – Average Value 📊

Returns the **mean** (average) of all elements.

**Formula:** `mean = sum of all elements / number of elements`

```python
average = np.mean(X)
print(average)   # Output: 25 / 5 = 5.0
```

---

# 5. `median()` – Middle Value 🎯

Returns the **middle value** after sorting the array.

```python
median_value = np.median(X)
print(median_value)   # Output: 4.0
```

### How median is calculated:

**Step 1:** Sort the array → `[2, 3, 4, 7, 9]`  
**Step 2:** Find the middle element → index 2 → value `4`

### For even number of elements:
If array has even number of elements (e.g., `[2, 3, 4, 7]`):
- Take the two middle values: `3` and `4`
- Median = `(3 + 4) / 2 = 3.5`

> 💡 `np.median()` automatically handles both odd and even counts.

---

# 6. `prod()` – Product of All Elements ✖️

Returns the **product** (multiplication) of all elements.

```python
product = np.prod(X)
print(product)   # Output: 4 × 2 × 3 × 9 × 7 = 1512
```

---

# 7. `var()` – Variance 📐

Returns the **variance** – measures how spread out the numbers are.

```python
variance = np.var(X)
print(variance)   # Output: 6.8
```

### Variance Formula (for population):

```
Variance = Σ (xᵢ - mean)² / N
```

Where:
- `xᵢ` = each element
- `mean` = average of all elements
- `N` = total number of elements

### Step-by-step calculation for `[4, 2, 3, 9, 7]` (mean = 5):

| Element (x) | x - mean | (x - mean)² |
|-------------|----------|-------------|
| 4 | 4 - 5 = -1 | 1 |
| 2 | 2 - 5 = -3 | 9 |
| 3 | 3 - 5 = -2 | 4 |
| 9 | 9 - 5 = 4 | 16 |
| 7 | 7 - 5 = 2 | 4 |

**Sum of squares** = 1 + 9 + 4 + 16 + 4 = 34

**Variance** = 34 / 5 = **6.8**

> 💡 Variance tells you how much the data deviates from the mean.

---

# 8. `std()` – Standard Deviation 📏

Returns the **standard deviation** – the square root of variance.

```python
std_dev = np.std(X)
print(std_dev)   # Output: √6.8 ≈ 2.607
```

**Formula:** `Standard Deviation = √Variance`

> 💡 Standard deviation is more interpretable than variance because it's in the same units as the original data.

---

## 📊 Complete Reference Table

| Function | What it does | Formula | Example (X = [4,2,3,9,7]) |
|----------|--------------|---------|---------------------------|
| `np.max(X)` | Maximum value | – | 9 |
| `np.min(X)` | Minimum value | – | 2 |
| `np.sum(X)` | Sum of all elements | Σx | 25 |
| `np.mean(X)` | Average | Σx / N | 5.0 |
| `np.median(X)` | Middle value | Sorted middle | 4.0 |
| `np.prod(X)` | Product of all elements | Πx | 1512 |
| `np.var(X)` | Variance | Σ(x - mean)² / N | 6.8 |
| `np.std(X)` | Standard deviation | √Variance | ≈ 2.607 |

---

## ✅ Important Points for Exams/Interviews

1. **`np.max()` and `np.min()`** – find extreme values in the array.
2. **`np.sum()`** – total of all elements.
3. **`np.mean()`** = sum / number of elements.
4. **`np.median()`** – middle value after sorting; works for both odd/even counts.
5. **`np.prod()`** – product (multiplication) of all elements.
6. **Variance** measures **spread** – how far numbers are from the mean.
7. **Standard deviation** = square root of variance – easier to interpret.
8. All these functions scan the **entire array** – they are O(n) operations.

---

## 🧪 Practice Examples (Try Yourself)

```python
import numpy as np

data = np.array([10, 20, 30, 40, 50])

print(np.max(data))     # ?
print(np.min(data))     # ?
print(np.sum(data))     # ?
print(np.mean(data))    # ?
print(np.median(data))  # ?
print(np.prod(data))    # ?
print(np.var(data))     # ?
print(np.std(data))     # ?
```

**Answers:**
- `50`
- `10`
- `150`
- `30.0`
- `30.0`
- `10 × 20 × 30 × 40 × 50 = 12,000,000`
- Variance = 200.0
- Standard deviation ≈ 14.14

---

## 🎯 Final Pro Tips

| You want to... | Use this |
|----------------|----------|
| Find largest number | `np.max()` |
| Find smallest number | `np.min()` |
| Add all numbers | `np.sum()` |
| Find average | `np.mean()` |
| Find middle value | `np.median()` |
| Multiply all numbers | `np.prod()` |
| Measure spread (squared units) | `np.var()` |
| Measure spread (original units) | `np.std()` |

---

## 🚀 Summary

> **NumPy Statistical Functions = Fast, built-in statistical calculations**
> - `max` / `min` → extreme values
> - `sum` → total
> - `mean` → average
> - `median` → middle value
> - `prod` → product of all
> - `var` → variance (spread)
> - `std` → standard deviation (√variance)

```python
# Quick visual
import numpy as np

data = np.array([4, 2, 3, 9, 7])

print(f"Max: {np.max(data)}")      # 9
print(f"Min: {np.min(data)}")      # 2
print(f"Sum: {np.sum(data)}")      # 25
print(f"Mean: {np.mean(data)}")    # 5.0
print(f"Median: {np.median(data)}")# 4.0
print(f"Product: {np.prod(data)}") # 1512
print(f"Variance: {np.var(data)}") # 6.8
print(f"Std Dev: {np.std(data)}")  # 2.607
```

---

Happy Coding! 🐍📊  
You are now ready to answer any question on NumPy statistical functions in exams and interviews. 💪
