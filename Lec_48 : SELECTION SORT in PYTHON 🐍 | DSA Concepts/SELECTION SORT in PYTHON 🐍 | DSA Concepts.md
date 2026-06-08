# 🎯 Selection Sort in Python
<sub>📺 <a href="https://youtu.be/xWpqj3s6ebM?si=eR_HjK58Ep9tD0iR">Video Link</a></sub>
## 🔹 What is Selection Sort?

> **Selection Sort** is a simple sorting algorithm that repeatedly finds the **minimum element** from the unsorted portion of the array and places it at the **beginning** of the sorted portion.

✅ After each pass, one more element is placed in its correct position (at the beginning of the sorted part).

---

## 🔹 The Core Concept

| Pass | What happens |
|------|--------------|
| **Pass 1** | Find the **smallest** element in the entire array → swap with **first position** |
| **Pass 2** | Find the **second smallest** from remaining unsorted → swap with **second position** |
| **Pass 3** | Find the **third smallest** → swap with **third position** |
| ... | Continue until entire array is sorted |

> 🔥 **Key Insight:** After each pass, the **smallest remaining element** is placed in its correct final position.

---

## 🔹 Step-by-Step Example

**Initial Array:** `[41, 33, 17, 42, 24]`

### Pass 1 (i = 0) – Find smallest in entire array:

| Step | j | arr[j] | arr[min] | Comparison | min updated? |
|------|---|--------|----------|------------|---------------|
| Start | – | – | min = 0 (41) | – | – |
| 1 | 1 | 33 | 41 | 33 < 41? ✅ | min = 1 (33) |
| 2 | 2 | 17 | 33 | 17 < 33? ✅ | min = 2 (17) |
| 3 | 3 | 42 | 17 | 42 < 17? ❌ | No change |
| 4 | 4 | 24 | 17 | 24 < 17? ❌ | No change |

**Smallest element = 17 (at index 2)**  
**Swap arr[0] and arr[2]**

```
Before swap: [41, 33, 17, 42, 24]
After swap:  [17, 33, 41, 42, 24]
```
✅ After Pass 1: **17 is in its correct position (index 0)**

---

### Pass 2 (i = 1) – Find smallest from index 1 to end:

Array: `[17, 33, 41, 42, 24]`

| Step | j | arr[j] | arr[min] | Comparison | min updated? |
|------|---|--------|----------|------------|---------------|
| Start | – | – | min = 1 (33) | – | – |
| 2 | 2 | 41 | 33 | 41 < 33? ❌ | No change |
| 3 | 3 | 42 | 33 | 42 < 33? ❌ | No change |
| 4 | 4 | 24 | 33 | 24 < 33? ✅ | min = 4 (24) |

**Smallest in remaining = 24 (at index 4)**  
**Swap arr[1] and arr[4]**

```
Before swap: [17, 33, 41, 42, 24]
After swap:  [17, 24, 41, 42, 33]
```
✅ After Pass 2: **24 is in its correct position (index 1)**

---

### Pass 3 (i = 2) – Find smallest from index 2 to end:

Array: `[17, 24, 41, 42, 33]`

| Step | j | arr[j] | arr[min] | Comparison | min updated? |
|------|---|--------|----------|------------|---------------|
| Start | – | – | min = 2 (41) | – | – |
| 3 | 3 | 42 | 41 | 42 < 41? ❌ | No change |
| 4 | 4 | 33 | 41 | 33 < 41? ✅ | min = 4 (33) |

**Smallest in remaining = 33 (at index 4)**  
**Swap arr[2] and arr[4]**

```
Before swap: [17, 24, 41, 42, 33]
After swap:  [17, 24, 33, 42, 41]
```
✅ After Pass 3: **33 is in its correct position (index 2)**

---

### Pass 4 (i = 3) – Find smallest from index 3 to end:

Array: `[17, 24, 33, 42, 41]`

| Step | j | arr[j] | arr[min] | Comparison | min updated? |
|------|---|--------|----------|------------|---------------|
| Start | – | – | min = 3 (42) | – | – |
| 4 | 4 | 41 | 42 | 41 < 42? ✅ | min = 4 (41) |

**Swap arr[3] and arr[4]**

```
Before swap: [17, 24, 33, 42, 41]
After swap:  [17, 24, 33, 41, 42]
```

✅ **Final Sorted Array:** `[17, 24, 33, 41, 42]`

---

## 🔹 Python Code for Selection Sort

```python
def selection_sort(arr):
    """
    Sorts an array using Selection Sort algorithm
    """
    n = len(arr)
    
    # Outer loop: selects position to fill
    for i in range(n - 1):      # i = 0 to n-2
        min_index = i            # Assume current position has smallest
        
        # Inner loop: find actual smallest in remaining
        for j in range(i + 1, n):
            if arr[j] < arr[min_index]:
                min_index = j    # Update min_index if smaller found
        
        # Swap: place smallest at correct position
        arr[i], arr[min_index] = arr[min_index], arr[i]
    
    return arr

# Example usage
my_list = [41, 33, 17, 42, 24]
sorted_list = selection_sort(my_list)
print(sorted_list)  # Output: [17, 24, 33, 41, 42]
```

---

## 🔹 Code Explanation – Detailed Breakdown

### Variables:
| Variable | Meaning |
|----------|---------|
| `n` | Length of the array (number of elements) |
| `i` | Current position being filled (boundary between sorted and unsorted) |
| `min_index` | Index of the smallest element found so far in unsorted portion |
| `j` | Scans through the unsorted portion to find the minimum |

### Outer Loop: `for i in range(n - 1):`
- Runs from `i = 0` to `i = n-2`
- Total passes = `n-1` (last element automatically sorted)
- `i` marks the **boundary**: elements before `i` are sorted

### Inner Loop: `for j in range(i + 1, n):`
- Starts from `i+1` (one position after current)
- Goes to the end of array (`n-1`)
- Finds the smallest element in unsorted portion

### Swap: `arr[i], arr[min_index] = arr[min_index], arr[i]`
- Pythonic way to swap without temporary variable
- Places the smallest element at position `i`

---

## 🔹 Step-by-Step Code Execution Trace

**Initial:** `arr = [41, 33, 17, 42, 24]`, `n = 5`

### i = 0:
| Variable | Value |
|----------|-------|
| `min_index` | 0 |
| j loop | j=1→33<41? ✅ → min=1; j=2→17<33? ✅ → min=2; j=3→42<17? ❌; j=4→24<17? ❌ |
| `min_index` = 2 | (element 17) |
| Swap | arr[0]=41 ↔ arr[2]=17 → `[17, 33, 41, 42, 24]` |

### i = 1:
| Variable | Value |
|----------|-------|
| `min_index` | 1 |
| j loop | j=2→41<33? ❌; j=3→42<33? ❌; j=4→24<33? ✅ → min=4 |
| `min_index` = 4 | (element 24) |
| Swap | arr[1]=33 ↔ arr[4]=24 → `[17, 24, 41, 42, 33]` |

### i = 2:
| Variable | Value |
|----------|-------|
| `min_index` | 2 |
| j loop | j=3→42<41? ❌; j=4→33<41? ✅ → min=4 |
| `min_index` = 4 | (element 33) |
| Swap | arr[2]=41 ↔ arr[4]=33 → `[17, 24, 33, 42, 41]` |

### i = 3:
| Variable | Value |
|----------|-------|
| `min_index` | 3 |
| j loop | j=4→41<42? ✅ → min=4 |
| `min_index` = 4 | (element 41) |
| Swap | arr[3]=42 ↔ arr[4]=41 → `[17, 24, 33, 41, 42]` |

**Final:** `[17, 24, 33, 41, 42]` ✅

---

## 🔹 Visual Progress of Sorting

```
Start:     [41, 33, 17, 42, 24]
Pass 1:    [17, 33, 41, 42, 24]   ← 17 is correct
Pass 2:    [17, 24, 41, 42, 33]   ← 24 is correct
Pass 3:    [17, 24, 33, 42, 41]   ← 33 is correct
Pass 4:    [17, 24, 33, 41, 42]   ← 41 is correct
Final:     [17, 24, 33, 41, 42]   ← Fully sorted
```

---

## 📊 Complexity Analysis

| Complexity | Value | Explanation |
|------------|-------|-------------|
| **Best Case** | O(n²) | Always scans all unsorted elements |
| **Worst Case** | O(n²) | Always scans all unsorted elements |
| **Average Case** | O(n²) | Always scans all unsorted elements |
| **Space Complexity** | O(1) | In-place sorting |

> ⚠️ Unlike Insertion Sort, Selection Sort has **O(n²) in all cases** – it doesn't adapt to already sorted data.

---

## 🔹 Selection Sort vs Insertion Sort

| Feature | Selection Sort | Insertion Sort |
|---------|---------------|----------------|
| Best case time | O(n²) | O(n) |
| Number of swaps | O(n) (minimum) | O(n²) |
| Adaptive? | ❌ No | ✅ Yes |
| Stable? | ❌ No (can be implemented as stable) | ✅ Yes |

---

## ✅ Important Points for Exams/Interviews

1. **Selection Sort** repeatedly selects the **minimum** from unsorted portion.
2. **Outer loop** runs `n-1` times (last element automatically in place).
3. **Inner loop** scans the unsorted portion to find the minimum.
4. After each pass, **one element is permanently placed** in correct position.
5. **Time complexity** is O(n²) for all cases (best, average, worst).
6. **Space complexity** is O(1) – sorts in-place.
7. **Number of swaps** is at most n-1 (better than bubble sort).
8. **Not stable** by default (but can be modified to be stable).
9. **Not adaptive** – doesn't take advantage of already sorted data.
10. Good for **small datasets** or when **swap cost is high** (minimizes swaps).

---

## 🧪 Practice Examples (Try Yourself)

```python
# Example 1
arr1 = [64, 25, 12, 22, 11]
selection_sort(arr1)  # [11, 12, 22, 25, 64]

# Example 2
arr2 = [5, 4, 3, 2, 1]  # Reverse sorted
selection_sort(arr2)  # [1, 2, 3, 4, 5]

# Example 3
arr3 = [1, 2, 3, 4, 5]  # Already sorted
selection_sort(arr3)  # [1, 2, 3, 4, 5] (still O(n²))

# Example 4
arr4 = [3]  # Single element
selection_sort(arr4)  # [3]

# Example 5
arr5 = []  # Empty array
selection_sort(arr5)  # []
```

---

## 🎯 Final Pro Tips

| Feature | Selection Sort |
|---------|----------------|
| Type | Comparison-based, in-place, not stable |
| Best for | Small datasets, when memory write is expensive |
| Worst for | Large datasets (use merge sort or quicksort) |
| Key advantage | Minimizes number of swaps (O(n) swaps) |
| Key disadvantage | Always O(n²) comparisons |

---

## 🚀 Summary

> **Selection Sort = Find minimum and swap to front, repeat**

```python
# Algorithm template
def selection_sort(arr):
    n = len(arr)
    for i in range(n - 1):
        min_idx = i
        for j in range(i + 1, n):
            if arr[j] < arr[min_idx]:
                min_idx = j
        arr[i], arr[min_idx] = arr[min_idx], arr[i]
    return arr
```

### Quick Visual:

```
Start:  [41, 33, 17, 42, 24]
        ↑
Pass 1: [17, 33, 41, 42, 24]  ← 17 in place
            ↑
Pass 2: [17, 24, 41, 42, 33]  ← 24 in place
                ↑
Pass 3: [17, 24, 33, 42, 41]  ← 33 in place
                    ↑
Pass 4: [17, 24, 33, 41, 42]  ← 41 in place
Final:  [17, 24, 33, 41, 42]  ✅ Sorted
```

---

Happy Coding! 🐍🎯  
You are now ready to answer any question on Selection Sort in Python for exams and interviews. 💪
