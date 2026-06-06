# 📦 Variables in Python
<sub>📺 <a href="https://youtu.be/ahEzdQe45Bk?si=doca8FWrFI1vBqj9">Video Link</a></sub>

### Why Do We Need Variables?

Let's understand with a simple school-level math problem:

> **Question:** If the Cost Price is 25% of the Selling Price, find the Profit Percentage.

**Solution using a variable:**

| Step | Description |
| :--- | :--- |
| Let SP = 100 | Assume Selling Price as 100 (using a variable `SP`) |
| CP = 25% of SP = 25 | Cost Price becomes 25 |
| Profit = SP - CP = 75 | Profit calculated |
| Profit % = (75 / 25) × 100 = **300%** | Final answer |

> **A variable is like a container.** It stores data so we can easily manage, manipulate, and change it later.

---

## 1. 🎯 What is a Variable?

A variable is a named container used to store data values. The programmer gives it a name and can later access, modify, or manipulate that data.

---

## 2. 🐍 How Python Variables are Different (Key Advantage)

| Feature | C / C++ / Java | Python |
| :--- | :--- | :--- |
| **Declaration** | Must declare type explicitly: `int a = 10;` | Simply write: `a = 10` |
| **Type Determination** | At compile time (static) | At runtime (dynamic) — Python figures it out automatically |
| **Type Changing** | Cannot change type: `a = 10` stays integer | Can change anytime: `a = 10` then `a = "Hello"` is perfectly valid |

### Examples:

```python
a = 10          # Python auto-detects this as integer
a = "Hello"     # Now a becomes a string — completely allowed!
```

> Python is **dynamically typed** — the type is determined at runtime based on the value you assign.

---

## 3. 📝 Syntax & Rules for Naming Variables

### Basic Syntax:
```python
variable_name = value
```

### Examples:
```python
x = 10                  # Integer
name = "Varun"          # String (single or double quotes both work)
price = 99.99           # Float
is_valid = True         # Boolean
```

---

## 4. 📏 Rules for Variable Names

### Rule 1: Must Start with a Letter or Underscore

| ✅ Valid | ❌ Invalid | Reason |
| :--- | :--- | :--- |
| `var1` | | Starts with letter `v` |
| `_var` | | Starts with underscore `_` |
| `a123` | | Starts with letter `a` |
| | `1var` | Starts with number — NOT allowed |
| | `@name` | Starts with special character — NOT allowed |

```python
_var = 5        # ✅ Valid
var1 = 10       # ✅ Valid
1var = 10       # ❌ Invalid — SyntaxError
```

---

### Rule 2: No Spaces Allowed

| ✅ Valid | ❌ Invalid |
| :--- | :--- |
| `var_one` | |
| `varOne` | |
| `my_variable` | |
| | `var one` (space not allowed) |

> Use **underscore `_`** or **camelCase** to combine multiple words.

```python
my name = "Varun"     # ❌ Invalid
my_name = "Varun"     # ✅ Valid
myName = "Varun"      # ✅ Valid
```

---

### Rule 3: Cannot Use Python Keywords

Python has around **35 reserved keywords**. You cannot use them as variable names.

| ❌ Invalid (Keywords) | Examples of Keywords |
| :--- | :--- |
| `def = 10` | `def` is used to define functions |
| `if = 5` | `if` is used for conditions |
| `True = 1` | `True` is a boolean keyword |
| `None = 0` | `None` is a special keyword |

```python
def = 10    # ❌ Invalid — SyntaxError (def is a keyword)
deff = 10   # ✅ Valid — small spelling change makes it okay
```

> **Tip:** In Python editors, keywords appear in a different color (like green). If your variable name changes color, it's likely a keyword — avoid it!

---

### Rule 4: Variable Names are Case-Sensitive

| Variable | Value |
| :--- | :--- |
| `a = 10` | Small `a` stores 10 |
| `A = 20` | Capital `A` stores 20 |

```python
a = 10
A = 20

print(a)    # Output: 10
print(A)    # Output: 20
```

> `a` and `A` are **completely different variables** in Python.

---

## 5. 📊 Summary Table of Rules

| Rule | Description | ✅ Valid Example | ❌ Invalid Example |
| :--- | :--- | :--- | :--- |
| **Start** | Must begin with letter or `_` | `name`, `_var` | `1name`, `@var` |
| **Spaces** | No spaces allowed | `my_name`, `myName` | `my name` |
| **Keywords** | Cannot use Python keywords | `student`, `value` | `def`, `if`, `True` |
| **Case Sensitivity** | `age` and `Age` are different | `age = 10`, `Age = 20` | Treating them as same |

---

## 7. 📝 Key Takeaways

| Point | Details |
| :--- | :--- |
| **Definition** | A variable is a container to store data |
| **Dynamic Typing** | Python auto-detects type at runtime — no need to declare |
| **Flexibility** | A variable can change type during execution |
| **Naming Rules** | Start with letter/underscore, no spaces, no keywords, case-sensitive |
| **Exam Tip** | Rules for naming variables and Python's dynamic typing are favourite interview questions |

---

**Now you know everything about Variables in Python!** 📦
