# 🃏 Insertion Sort in Python
<sub>📺 <a href="https://youtu.be/9j7llneJ77o?si=7KW1jmRcdIFWmrIC">Video Link</a></sub>
## 🔹 What is Insertion Sort?

> **Insertion Sort** is a simple sorting algorithm that builds the final sorted array **one element at a time** by inserting each element into its correct position among the already sorted elements.

✅ Think of it like **sorting playing cards** in your hand – you pick one card at a time and insert it into the correct position among the cards you're already holding.

---

## 🔹 The Card Sorting Analogy 🃏

Imagine you have a hand of cards and you want to sort them:

| Step | Action |
|------|--------|
| 1 | Start with the **first card** (it's already "sorted" alone) |
| 2 | Pick the **next card** |
| 3 | Compare it with cards to its left |
| 4 | **Shift larger cards to the right** |
| 5 | **Insert** the new card in the correct position |
| 6 | Repeat until all cards are sorted |

---

## 🔹 Step-by-Step Example

**Initial Array:** `[40, 30, 20, 10]`

### Pass 1 – Insert 30:

```
Start: [40, 30, 20, 10]
Pick 30, compare with 40 → 40 > 30 → Shift 40 right
Result: [30, 40, 20, 10]  (30 inserted at correct position)
```

### Pass 2 – Insert 20:

```
Current: [30, 40, 20, 10]
Pick 20, compare with 40 → 40 > 20 → Shift 40 right
Compare with 30 → 30 > 20 → Shift 30 right
Insert 20 at position 0
Result: [20, 30, 40, 10]
```

### Pass 3 – Insert 10:

```
Current: [20, 30, 40, 10]
Pick 10, compare with 40 → 40 > 10 → Shift 40 right
Compare with 30 → 30 > 10 → Shift 30 right
Compare with 20 → 20 > 10 → Shift 20 right
Insert 10 at position 0
Result: [10, 20, 30, 40]  ✅ Sorted!
```

---

## 🔹 Visual Representation

```
Original:  [40, 30, 20, 10]
           ↑
           First element (already sorted)

Pass 1:    [40, 30, 20, 10] → Insert 30 → [30, 40, 20, 10]
                ↑
                Pick 30

Pass 2:    [30, 40, 20, 10] → Insert 20 → [20, 30, 40, 10]
                    ↑
                    Pick 20

Pass 3:    [20, 30, 40, 10] → Insert 10 → [10, 20, 30, 40]
                        ↑
                        Pick 10

Final:     [10, 20, 30, 40]  ✅ Sorted
```

---

## 🔹 Key Insight – Sorted Prefix Property

> **Important:** After each pass, all elements to the **left of the current element** are already **sorted**.

This is why we only need to compare with elements to the left – we don't need to check the right side.

---

## 🔹 Python Code for Insertion Sort

```python
def insertion_sort(arr):
    """
    Sorts an array using Insertion Sort algorithm
    """
    n = len(arr)
    
    # Start from index 1 (second element) because first element is already "sorted"
    for i in range(1, n):
        key = arr[i]        # Element to be inserted
        j = i - 1           # Start comparing with element to the left
        
        # Shift elements that are greater than key to the right
        while j >= 0 and arr[j] > key:
            arr[j + 1] = arr[j]   # Shift right
            j = j - 1              # Move left
        
        # Insert key at its correct position
        arr[j + 1] = key
    
    return arr

# Example usage
my_list = [40, 30, 20, 10]
sorted_list = insertion_sort(my_list)
print(sorted_list)  # Output: [10, 20, 30, 40]
```

---

## 🔹 Code Explanation – Step by Step

### Variables:
| Variable | Meaning |
|----------|---------|
| `n` | Length of the array |
| `i` | Current index (element being inserted) |
| `key` | Value of current element (the "card in hand") |
| `j` | Index of element to the left (starts at i-1, moves left) |

### The `for` loop:
```python
for i in range(1, n):
```
- Starts from index `1` (second element)
- First element (index 0) is considered already sorted

### The `while` loop:
```python
while j >= 0 and arr[j] > key:
    arr[j + 1] = arr[j]
    j = j - 1
```
- Runs while we haven't reached the beginning (`j >= 0`)
- AND the left element is greater than `key`
- **Shift** the larger element one position to the right
- Move `j` one step left to check next element

### The Insertion:
```python
arr[j + 1] = key
```
- After shifting all larger elements, insert `key` at its correct position
- `j + 1` is the correct position (because `j` is now at the element smaller than key)

---

## 🔹 Step-by-Step Code Execution for `[40, 30, 20, 10]`

### Initial: `arr = [40, 30, 20, 10]`, `n = 4`

### i = 1 (key = 30):
| Step | j | arr[j] | Condition (j>=0 and arr[j] > key) | Action |
|------|---|--------|-----------------------------------|--------|
| 1 | 0 | 40 | 0>=0 ✅ and 40 > 30 ✅ | Shift 40 to index 1 → `[40, 40, 20, 10]` |
| 2 | -1 | – | -1 >=0 ❌ | Exit while |
| Insert key=30 at j+1=0 → `[30, 40, 20, 10]` |

### i = 2 (key = 20):
| Step | j | arr[j] | Condition | Action |
|------|---|--------|-----------|--------|
| 1 | 1 | 40 | 1>=0 ✅ and 40 > 20 ✅ | Shift 40 to index 2 → `[30, 40, 40, 10]` |
| 2 | 0 | 30 | 0>=0 ✅ and 30 > 20 ✅ | Shift 30 to index 1 → `[30, 30, 40, 10]` |
| 3 | -1 | – | -1 >=0 ❌ | Exit while |
| Insert key=20 at j+1=0 → `[20, 30, 40, 10]` |

### i = 3 (key = 10):
| Step | j | arr[j] | Condition | Action |
|------|---|--------|-----------|--------|
| 1 | 2 | 40 | 2>=0 ✅ and 40 > 10 ✅ | Shift 40 to index 3 → `[20, 30, 40, 40]` |
| 2 | 1 | 30 | 1>=0 ✅ and 30 > 10 ✅ | Shift 30 to index 2 → `[20, 30, 30, 40]` |
| 3 | 0 | 20 | 0>=0 ✅ and 20 > 10 ✅ | Shift 20 to index 1 → `[20, 20, 30, 40]` |
| 4 | -1 | – | -1 >=0 ❌ | Exit while |
| Insert key=10 at j+1=0 → `[10, 20, 30, 40]` |

**Final Sorted Array:** `[10, 20, 30, 40]` ✅

---

## 📊 Complexity Analysis

| Complexity | Value |
|------------|-------|
| **Best Case** | O(n) – Already sorted (only comparisons, no shifts) |
| **Worst Case** | O(n²) – Reverse sorted (maximum shifts) |
| **Average Case** | O(n²) |
| **Space Complexity** | O(1) – In-place sorting |

---

## ✅ Important Points for Exams/Interviews

1. **In-place algorithm** – sorts without using extra space (O(1) space).
2. **Stable sort** – maintains relative order of equal elements.
3. **Adaptive** – efficient for partially sorted or small datasets.
4. **Best case** (already sorted): only O(n) comparisons, no shifts.
5. **Worst case** (reverse sorted): maximum number of shifts.
6. Works well for **small datasets** or **nearly sorted data**.
7. Used as part of more advanced algorithms (like Timsort).
8. **Key insight:** Left portion of array is always sorted.

---

## 🧪 Practice Examples (Try Yourself)

```python
# Example 1
arr1 = [5, 2, 4, 6, 1, 3]
insertion_sort(arr1)  # [1, 2, 3, 4, 5, 6]

# Example 2
arr2 = [1, 2, 3, 4, 5]  # Already sorted
insertion_sort(arr2)  # [1, 2, 3, 4, 5] (best case)

# Example 3
arr3 = [9, 8, 7, 6, 5]  # Reverse sorted
insertion_sort(arr3)  # [5, 6, 7, 8, 9] (worst case)

# Example 4
arr4 = [3]  # Single element
insertion_sort(arr4)  # [3]

# Example 5
arr5 = []  # Empty array
insertion_sort(arr5)  # []
```

---

## 🎯 Final Pro Tips

| Feature | Insertion Sort |
|---------|----------------|
| Type | Comparison-based, in-place, stable |
| Best for | Small arrays or nearly sorted data |
| When to use | When data is streaming (online algorithm) |
| When NOT to use | Large datasets (use merge sort or quicksort) |

---

## 🚀 Summary

> **Insertion Sort = Building sorted array by inserting one element at a time**

```python
# Algorithm template
for i in range(1, len(arr)):
    key = arr[i]
    j = i - 1
    while j >= 0 and arr[j] > key:
        arr[j + 1] = arr[j]   # Shift right
        j -= 1                # Move left
    arr[j + 1] = key          # Insert key
```

### Quick Visual:

```
Start:  [40, 30, 20, 10]
        ↑
Pass 1: [30, 40, 20, 10]
            ↑
Pass 2: [20, 30, 40, 10]
                ↑
Pass 3: [10, 20, 30, 40]
                    ↑
Final:  [10, 20, 30, 40]  ✅
```

---

Happy Coding! 🐍🃏  
You are now ready to answer any question on Insertion Sort in Python for exams and interviews. 💪
