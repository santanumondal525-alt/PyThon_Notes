# 📊 Sorting in NumPy Arrays (1D)
<sub>📺 <a href="https://youtu.be/O1Tpvs-z_Do?si=um8Bq6PsUJ1dU8GM">Video Link</a></sub>
## 🔹 What is Sorting?

> Sorting arranges the elements of an array in a specific order – **ascending** (default) or **descending**.

✅ NumPy provides multiple ways to sort arrays, each with different use cases.

---

## 🔹 Three Ways to Sort in NumPy

| Method | What it does | Returns | Modifies Original? |
|--------|--------------|---------|--------------------|
| `np.sort(array)` | Returns a sorted **copy** | New sorted array | ❌ No (original unchanged) |
| `np.argsort(array)` | Returns **indices** that would sort the array | Array of indices | ❌ No |
| `array.sort()` | Sorts **in-place** | None | ✅ Yes (original modified) |

---

# 1. `np.sort()` – Returns a Sorted Copy

> Creates a **new sorted array** without changing the original.

### Example:

```python
import numpy as np

X = np.array([6, 3, 9, 2, 7])

# Create a sorted copy
sorted_copy = np.sort(X)
print(sorted_copy)   # Output: [2, 3, 6, 7, 9]

# Original remains unchanged
print(X)             # Output: [6, 3, 9, 2, 7]
```

> 💡 **Default order:** Ascending (smallest to largest)

---

## How to Sort in Descending Order using `np.sort()`

Since `np.sort()` only sorts in ascending order, you can **reverse** the result:

```python
X = np.array([6, 3, 9, 2, 7])

# Ascending first, then reverse
descending = np.sort(X)[::-1]
print(descending)   # Output: [9, 7, 6, 3, 2]
```

> ✅ Logic: `np.sort(X)` = ascending → `[::-1]` = reverse → descending

---

# 2. `np.argsort()` – Returns Sorted Indices

> `argsort()` returns the **indices** (positions) of the elements if they were sorted, not the values themselves.

### Example:

```python
X = np.array([6, 3, 9, 2, 7])
indices = np.argsort(X)
print(indices)   # Output: [3, 1, 0, 4, 2]
```

### How to Interpret:

| Index | Value | Sorted Order | Original Index |
|-------|-------|--------------|----------------|
| 0 | 6 | 2 (smallest) | Index 3 |
| 1 | 3 | 3 | Index 1 |
| 2 | 9 | 6 | Index 0 |
| 3 | 2 | 7 | Index 4 |
| 4 | 7 | 9 (largest) | Index 2 |

**Step-by-step:**
1. Sort the values: `[2, 3, 6, 7, 9]`
2. Find where each sorted value came from in the original array:
   - `2` was at index `3`
   - `3` was at index `1`
   - `6` was at index `0`
   - `7` was at index `4`
   - `9` was at index `2`
3. Result: `[3, 1, 0, 4, 2]`

> 💡 `argsort()` is useful when you need the original positions after sorting.

### Using argsort to get sorted values:
```python
X = np.array([6, 3, 9, 2, 7])
indices = np.argsort(X)
sorted_values = X[indices]
print(sorted_values)   # [2, 3, 6, 7, 9]
```

---

# 3. `array.sort()` – In-Place Sorting

> Sorts the array **directly** – no copy is created, original array is modified.

### Example:

```python
X = np.array([6, 3, 9, 2, 7])
X.sort()              # Sorts in-place (ascending)
print(X)              # Output: [2, 3, 6, 7, 9]
```

> ⚠️ **Important:** `X.sort()` returns `None` and modifies `X` permanently.

### In-Place Descending Sort:
```python
X = np.array([6, 3, 9, 2, 7])
X.sort()              # Ascending first
X = X[::-1]           # Then reverse
print(X)              # [9, 7, 6, 3, 2]
```

Or in one line:
```python
X = np.sort(X)[::-1]  # But this creates a new array
```

---

## 📊 Comparison Table

| Feature | `np.sort(X)` | `np.argsort(X)` | `X.sort()` |
|---------|--------------|-----------------|------------|
| Returns | New sorted array | Indices array | `None` |
| Modifies X? | ❌ No | ❌ No | ✅ Yes |
| Memory usage | Extra (copy) | Extra (indices) | None (in-place) |
| Use case | Need to keep original | Need original positions | Don't need original |
| Default order | Ascending | Ascending (indices) | Ascending |

---

## ✅ Important Points for Exams/Interviews

1. **`np.sort()`** returns a **new array** – original unchanged.
2. **`array.sort()`** modifies the **original array** in-place.
3. **`np.argsort()`** returns **indices**, not values.
4. **Default sorting** is always **ascending**.
5. **Descending order** can be achieved by reversing the sorted array: `np.sort(X)[::-1]`.
6. `argsort` is commonly used when you need to know the **original positions** after sorting.

---

## 🧪 Practice Examples (Try Yourself)

```python
import numpy as np

arr = np.array([8, 2, 5, 1, 9, 3])

# 1. Sorted copy
print(np.sort(arr))        # ?

# 2. Original after np.sort()
print(arr)                 # ?

# 3. Argsort (indices)
print(np.argsort(arr))     # ?

# 4. Descending order using np.sort()
print(np.sort(arr)[::-1])  # ?

# 5. In-place sort
arr.sort()
print(arr)                 # ?

# 6. Original after in-place sort
print(arr)                 # ?
```

**Answers:**
- `[1, 2, 3, 5, 8, 9]`
- `[8, 2, 5, 1, 9, 3]` (unchanged)
- `[3, 1, 5, 2, 0, 4]` (positions of sorted values)
- `[9, 8, 5, 3, 2, 1]`
- `[1, 2, 3, 5, 8, 9]`
- Same as above (original is now modified)

---

## 🎯 Final Pro Tips

| You want to... | Use this |
|----------------|----------|
| Sort and keep original | `np.sort(arr)` |
| Sort and overwrite original | `arr.sort()` |
| Get sorted values from original | `np.sort(arr)` |
| Get positions that would sort the array | `np.argsort(arr)` |
| Sort in descending order | `np.sort(arr)[::-1]` |
| Save memory (no copy) | `arr.sort()` |

---

## 🚀 Summary

> **Sorting in NumPy (1D):**
> - `np.sort(X)` → returns **new sorted array** (original safe)
> - `X.sort()` → **in-place sort** (original modified)
> - `np.argsort(X)` → returns **indices** of sorted order
> - Default = **ascending**
> - Descending = `np.sort(X)[::-1]`

```python
# Quick visual
import numpy as np

arr = np.array([5, 2, 8, 1, 9])

print(np.sort(arr))      # [1, 2, 5, 8, 9] (copy)
print(arr)               # [5, 2, 8, 1, 9] (unchanged)

print(np.argsort(arr))   # [3, 1, 0, 2, 4] (indices)

arr.sort()               # in-place
print(arr)               # [1, 2, 5, 8, 9] (modified)
```

---

Happy Coding! 🐍📊  
You are now ready to answer any question on NumPy 1D sorting in exams and interviews. 💪
