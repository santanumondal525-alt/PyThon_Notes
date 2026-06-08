# 🫧 Bubble Sort (Optimized) in Python
<sub>📺 <a href="https://youtu.be/00mmzkOvLlM?si=EL7Ploleqg7TtZlJ">Video Link</a></sub>
## 🔹 What is Bubble Sort?

> **Bubble Sort** is a simple sorting algorithm that repeatedly steps through the array, **compares adjacent elements**, and **swaps them** if they are in the wrong order. Larger elements "bubble up" to their correct position at the end of the array.

✅ After each pass, the **largest unsorted element** moves to its correct position at the rightmost end.

---

## 🔹 The Core Concept

| Pass | What happens |
|------|--------------|
| **Pass 1** | Largest element "bubbles up" to the **last position** (index n-1) |
| **Pass 2** | Second largest element moves to the **second last position** (index n-2) |
| **Pass 3** | Third largest element moves to the **third last position** (index n-3) |
| ... | Continue until entire array is sorted |

> 🔥 **Key Insight:** After each complete pass, one more element is placed in its final correct position.

---

## 🔹 Why Optimized Bubble Sort?

**Problem with Standard Bubble Sort:** Even if the array becomes sorted in the middle of execution, it continues making unnecessary passes.

**Solution (Optimized):** Use a `swapped` flag to track if any swap happened in a pass. If **no swaps** occurred, the array is already sorted → **break early**.

✅ This optimization improves the **best-case time complexity** from O(n²) to **O(n)**.

---

## 🔹 Step-by-Step Example (Worst Case – Reverse Sorted)

**Initial Array:** `[40, 30, 20, 10]`

### Pass 1 (i = 0) – Find largest and bubble to end:

| Step | Compare | Swap? | Array after swap |
|------|---------|-------|------------------|
| 1 | 40 > 30? ✅ | Swap | `[30, 40, 20, 10]` |
| 2 | 40 > 20? ✅ | Swap | `[30, 20, 40, 10]` |
| 3 | 40 > 10? ✅ | Swap | `[30, 20, 10, 40]` |

✅ **After Pass 1:** Largest element `40` is at correct position (index 3)

---

### Pass 2 (i = 1) – Find second largest:

| Step | Compare | Swap? | Array after swap |
|------|---------|-------|------------------|
| 1 | 30 > 20? ✅ | Swap | `[20, 30, 10, 40]` |
| 2 | 30 > 10? ✅ | Swap | `[20, 10, 30, 40]` |

✅ **After Pass 2:** Second largest `30` is at correct position (index 2)

---

### Pass 3 (i = 2) – Find third largest:

| Step | Compare | Swap? | Array after swap |
|------|---------|-------|------------------|
| 1 | 20 > 10? ✅ | Swap | `[10, 20, 30, 40]` |

✅ **After Pass 3:** Third largest `20` is at correct position (index 1)

---

### Pass 4 (i = 3) – No comparisons needed (last element already in place)

**Final Sorted Array:** `[10, 20, 30, 40]` ✅

---

## 🔹 Step-by-Step Example (Best Case – Already Sorted)

**Initial Array:** `[10, 20, 30, 40]`

### Pass 1 (i = 0):

| Step | Compare | Swap? |
|------|---------|-------|
| 1 | 10 > 20? ❌ | No swap |
| 2 | 20 > 30? ❌ | No swap |
| 3 | 30 > 40? ❌ | No swap |

**No swaps occurred in the entire pass!**  
`swapped` flag remains `False` → **Break out of the loop**

✅ **Array is already sorted – algorithm stops after only 1 pass!**

---

## 🔹 Optimized Bubble Sort Code

```python
def bubble_sort(arr):
    """
    Sorts an array using Optimized Bubble Sort algorithm
    """
    n = len(arr)
    
    # Outer loop: number of passes
    for i in range(n):          # i = 0 to n-1
        swapped = False         # Track if any swap happened in this pass
        
        # Inner loop: compare adjacent elements
        # After i passes, last i elements are already sorted
        for j in range(0, n - i - 1):
            if arr[j] > arr[j + 1]:
                # Swap if elements are in wrong order
                arr[j], arr[j + 1] = arr[j + 1], arr[j]
                swapped = True  # Mark that a swap occurred
        
        # If no swaps happened, array is already sorted
        if not swapped:
            break               # Exit early (optimization)
    
    return arr

# Example usage
my_list = [40, 30, 20, 10]
sorted_list = bubble_sort(my_list)
print(sorted_list)  # Output: [10, 20, 30, 40]
```

---

## 🔹 Code Explanation – Detailed Breakdown

### Variables:
| Variable | Meaning |
|----------|---------|
| `n` | Length of the array (number of elements) |
| `i` | Current pass number (also number of elements already sorted at the end) |
| `j` | Index for comparing adjacent elements `arr[j]` and `arr[j+1]` |
| `swapped` | Flag indicating whether any swap occurred in the current pass |

### Outer Loop: `for i in range(n):`
- Runs passes from `i = 0` to `i = n-1`
- After `i` passes, the **last i elements** are in their correct positions

### Inner Loop: `for j in range(0, n - i - 1):`
- Compares adjacent elements from index `0` to `n - i - 2`
- `n - i - 1` ensures we don't compare already-sorted elements at the end
- Example: If `n=4`, `i=0` → `j` goes to `2` (compares indices 0-1, 1-2, 2-3)

### Swap: `arr[j], arr[j+1] = arr[j+1], arr[j]`
- Pythonic way to swap two elements without a temporary variable
- Executes when `arr[j] > arr[j+1]` (wrong order)

### Optimization: `if not swapped: break`
- If a pass completes with **no swaps**, array is already sorted
- Breaks out of the outer loop early, saving unnecessary passes

---

## 🔹 Complete Code Execution Trace (Worst Case)

**Initial:** `arr = [40, 30, 20, 10]`, `n = 4`

### Pass 1 (i = 0):
| j | Compare arr[j] vs arr[j+1] | Swap? | Array after |
|---|---------------------------|-------|-------------|
| 0 | 40 > 30? ✅ | Swap | `[30, 40, 20, 10]` |
| 1 | 40 > 20? ✅ | Swap | `[30, 20, 40, 10]` |
| 2 | 40 > 10? ✅ | Swap | `[30, 20, 10, 40]` |

`swapped = True` → Continue

### Pass 2 (i = 1):
| j | Compare arr[j] vs arr[j+1] | Swap? | Array after |
|---|---------------------------|-------|-------------|
| 0 | 30 > 20? ✅ | Swap | `[20, 30, 10, 40]` |
| 1 | 30 > 10? ✅ | Swap | `[20, 10, 30, 40]` |

`swapped = True` → Continue

### Pass 3 (i = 2):
| j | Compare arr[j] vs arr[j+1] | Swap? | Array after |
|---|---------------------------|-------|-------------|
| 0 | 20 > 10? ✅ | Swap | `[10, 20, 30, 40]` |

`swapped = True` → Continue

### Pass 4 (i = 3):
`n - i - 1 = 4 - 3 - 1 = 0` → Inner loop does not run  
`swapped = False` → `if not swapped: break`

**Final:** `[10, 20, 30, 40]` ✅

---

## 📊 Complexity Analysis

| Case | Comparisons | Swaps | Time Complexity |
|------|-------------|-------|-----------------|
| **Best Case** (Already sorted) | O(n) | 0 | **O(n)** |
| **Worst Case** (Reverse sorted) | O(n²) | O(n²) | **O(n²)** |
| **Average Case** | O(n²) | O(n²) | **O(n²)** |

### Derivation of Worst Case Complexity:

| Pass | Comparisons | Swaps |
|------|-------------|-------|
| 1 | n-1 | n-1 |
| 2 | n-2 | n-2 |
| 3 | n-3 | n-3 |
| ... | ... | ... |
| n-1 | 1 | 1 |

**Total comparisons/swaps** = (n-1) + (n-2) + ... + 1 = **n(n-1)/2** = **O(n²)**

---

## 🔹 Bubble Sort vs Other Sorting Algorithms

| Feature | Bubble Sort | Selection Sort | Insertion Sort |
|---------|-------------|----------------|----------------|
| Best case | O(n) ✅ | O(n²) ❌ | O(n) ✅ |
| Worst case | O(n²) | O(n²) | O(n²) |
| Adaptive? | ✅ Yes (optimized) | ❌ No | ✅ Yes |
| Stable? | ✅ Yes | ❌ No (standard) | ✅ Yes |
| In-place? | ✅ Yes | ✅ Yes | ✅ Yes |
| When to use | Small datasets, nearly sorted | Small datasets | Small/nearly sorted datasets |

---

## ✅ Important Points for Exams/Interviews

1. **Bubble Sort** repeatedly compares adjacent elements and swaps if they are in wrong order.
2. **Largest elements "bubble up"** to the end after each pass.
3. **Optimized version** uses a `swapped` flag to detect if array is already sorted.
4. **Best case** (already sorted): **O(n)** – only one pass with no swaps.
5. **Worst case** (reverse sorted): **O(n²)** – maximum swaps and comparisons.
6. **Average case**: **O(n²)**.
7. **Space complexity:** **O(1)** – sorts in-place.
8. **Stable sort** – maintains relative order of equal elements.
9. **Adaptive** – performs better on already/nearly sorted data.
10. Not recommended for large datasets due to O(n²) time complexity.

---

## 🧪 Practice Examples (Try Yourself)

```python
# Example 1: Already sorted (Best case)
arr1 = [10, 20, 30, 40, 50]
bubble_sort(arr1)  # [10, 20, 30, 40, 50] (O(n))

# Example 2: Reverse sorted (Worst case)
arr2 = [50, 40, 30, 20, 10]
bubble_sort(arr2)  # [10, 20, 30, 40, 50] (O(n²))

# Example 3: Partially sorted
arr3 = [10, 50, 20, 40, 30]
bubble_sort(arr3)  # [10, 20, 30, 40, 50]

# Example 4: With duplicates (stable)
arr4 = [5, 2, 5, 1, 2]
bubble_sort(arr4)  # [1, 2, 2, 5, 5] (stable)

# Example 5: Single element
arr5 = [10]
bubble_sort(arr5)  # [10]

# Example 6: Empty array
arr6 = []
bubble_sort(arr6)  # []
```

---

## 🎯 Final Pro Tips

| Feature | Optimized Bubble Sort |
|---------|----------------------|
| Type | Comparison-based, in-place, stable, adaptive |
| Best for | Small datasets, nearly sorted data |
| Worst for | Large datasets (use merge sort or quicksort) |
| Key advantage | Simple to understand and implement |
| Key disadvantage | Very slow for large datasets (O(n²)) |

---

## 🚀 Summary

> **Bubble Sort = Larger elements "bubble up" to the end**
> - Compare adjacent elements
> - Swap if in wrong order
> - After each pass, largest unsorted element is in place
> - Use `swapped` flag for optimization

```python
# Optimized Bubble Sort template
def bubble_sort(arr):
    n = len(arr)
    for i in range(n):
        swapped = False
        for j in range(n - i - 1):
            if arr[j] > arr[j + 1]:
                arr[j], arr[j + 1] = arr[j + 1], arr[j]
                swapped = True
        if not swapped:
            break
    return arr
```

### Quick Visual:

```
Start:  [40, 30, 20, 10]  (Worst case)
Pass 1: [30, 20, 10, 40]  ← 40 bubbles to end
Pass 2: [20, 10, 30, 40]  ← 30 bubbles to position
Pass 3: [10, 20, 30, 40]  ← 20 bubbles to position
Pass 4: Already sorted    ← Break
Final:  [10, 20, 30, 40]  ✅
```

---

Happy Coding! 🐍🫧  
You are now ready to answer any question on Bubble Sort (Optimized) in Python for exams and interviews. 💪
