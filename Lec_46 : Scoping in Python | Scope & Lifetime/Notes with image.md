# 🐍 Scoping and Lifetime of Variables in Python (With Visual Images & Diagrams)

---

# 🎯 1. What is Scope?

## 📖 Definition

**Scope** is the area of a program where a variable can be accessed or recognized.

### Simple Meaning

👉 Scope tells us:

> **"Where can I use this variable?"**

---

## 🖼️ Visual Image: Scope

```text
                PROGRAM

     ┌───────────────────────────┐
     │      Global Scope         │
     │                           │
     │   global_var = 100        │
     │                           │
     │ ┌───────────────────────┐ │
     │ │ Function Scope (F1)   │ │
     │ │ local_var = 50        │ │
     │ └───────────────────────┘ │
     │                           │
     └───────────────────────────┘
```

### Explanation

* `global_var` is visible everywhere.
* `local_var` is visible only inside Function F1.

---

# 🎯 2. Local Scope

## 📖 Definition

Variables declared inside a function are called **Local Variables**.

They can only be accessed inside that function.

---

## Example

```python
def show():
    message = "Hello Python"

    print(message)

show()
```

Output

```python
Hello Python
```

---

## 🖼️ Visual Image: Local Scope

```text
Function show()

┌─────────────────────┐
│ message = "Hello"   │
│                     │
│ print(message)      │
└─────────────────────┘

Accessible Only Here
```

---

## Real-Life Example

Imagine your classroom.

```text
School
│
├── Class 10A
│     └── Student Rahul
│
├── Class 10B
│
└── Class 10C
```

Rahul is known only in Class 10A.

Similarly,

`message` is known only inside `show()`.

---

# 🎯 3. Global Scope

## 📖 Definition

Variables declared outside all functions are called **Global Variables**.

They can be accessed throughout the program.

---

## Example

```python
name = "Python"

def show():
    print(name)

show()

print(name)
```

Output

```python
Python
Python
```

---

## 🖼️ Visual Image: Global Scope

```text
           Global Variable

           name="Python"

                  │
      ┌───────────┴───────────┐
      │                       │
      ▼                       ▼

 Function F1()         Main Program

 print(name)           print(name)
```

---

## Explanation

Global variables are available:

✅ Inside Functions

✅ Outside Functions

✅ Entire Program

---

# 🎯 4. Local and Global Variables Together

## Example

```python
glob = "I am Global"

def F1():

    local = "I am Local"

    print(local)

    print(glob)

F1()
```

---

## 🖼️ Memory Representation

```text
Main Memory

┌────────────────────┐
│ glob               │
│ I am Global        │
└────────────────────┘


Function F1()

┌────────────────────┐
│ local              │
│ I am Local         │
└────────────────────┘
```

---

## Output

```python
I am Local
I am Global
```

---

# 🎯 5. Why Global Variables Work Inside Functions?

## 🖼️ Scope Flow Diagram

```text
Global Scope
     │
     │
     ▼
Function F1()
     │
     ├── local
     │
     └── glob
```

Python first searches:

1. Local Scope
2. Global Scope

Therefore it finds `glob`.

---

# 🎯 6. Why Local Variables Fail Outside Function?

## Example

```python
glob = "I am Global"

def F1():

    local = "I am Local"

    print(local)

F1()

print(local)
```

---

## Error

```python
NameError
```

---

## 🖼️ Visual Image

```text
Inside Function

┌─────────────┐
│ local       │
└─────────────┘


Outside Function

Looking for local...

❌ Not Found

Result:

NameError
```

---

## Explanation

After function execution ends,

Python cannot find `local`.

Therefore:

```python
NameError: name 'local' is not defined
```

---

# 🎯 7. What is Lifetime?

## 📖 Definition

Lifetime is the duration for which a variable exists in memory.

### Simple Meaning

👉 Lifetime tells us:

> **"How long does the variable stay alive in memory?"**

---

# 🖼️ Scope vs Lifetime

```text
SCOPE
│
├─ Where variable is accessible
│
└─ Area / Region


LIFETIME
│
├─ How long variable exists
│
└─ Time Duration
```

---

# 🎯 8. Lifetime of Local Variables

## Example

```python
def F1():

    local = "Python"

    print(local)

F1()
```

---

## 🖼️ Execution Flow

```text
Function Called
      │
      ▼

local Created
      │
      ▼

local Used
      │
      ▼

Function Ends
      │
      ▼

local Destroyed
```

---

## Memory View

### Before Function Call

```text
Memory

(No local variable)
```

---

### During Function Execution

```text
Memory

┌─────────────┐
│ local       │
│ Python      │
└─────────────┘
```

---

### After Function Ends

```text
Memory

(local removed)
```

---

# 🎯 9. Lifetime of Global Variables

## Example

```python
glob = "Python"

def F1():
    print(glob)

F1()
```

---

## 🖼️ Global Lifetime Diagram

```text
Program Starts
      │
      ▼

glob Created
      │
      ▼

Function Executes
      │
      ▼

Still Exists
      │
      ▼

Program Ends
      │
      ▼

glob Destroyed
```

---

## Memory Representation

```text
Entire Program Execution

┌───────────────────┐
│ glob = "Python"   │
└───────────────────┘

      Exists

Program Start
      ↓
Program End
```

---

# 🎯 10. Scope vs Lifetime Comparison

## 🖼️ Visual Table

| Scope                      | Lifetime                 |
| -------------------------- | ------------------------ |
| Where variable can be used | How long variable exists |
| Area/Region                | Time Duration            |
| Accessibility              | Memory Existence         |
| Function/Program           | Seconds/Execution Time   |

---

# 🎯 11. Interview Trick Question

## Question

Which variable has longer lifetime?

### Local Variable

```python
def F1():
    x = 10
```

### Global Variable

```python
x = 10
```

---

## 🖼️ Comparison Diagram

```text
LOCAL VARIABLE

Function Start
     │
     ▼
Created
     │
     ▼
Destroyed
(Function End)



GLOBAL VARIABLE

Program Start
     │
     ▼
Created
     │
     ▼
Exists Entire Program
     │
     ▼
Destroyed
(Program End)
```

### Answer

✅ Global Variable

Because it survives throughout the program execution.

---

# 🎯 Complete Mind Map

```text
VARIABLES
│
├── Scope
│   │
│   ├── Local Scope
│   │     └── Function Only
│   │
│   └── Global Scope
│         └── Entire Program
│
│
└── Lifetime
    │
    ├── Local Variable
    │     └── Till Function Ends
    │
    └── Global Variable
          └── Till Program Ends
```

---

# 📝 Quick Revision

✅ **Scope** → Where variable can be used.

✅ **Lifetime** → How long variable remains in memory.

✅ **Local Variable**

* Created inside function
* Accessible only inside function
* Destroyed when function ends

✅ **Global Variable**

* Created outside function
* Accessible everywhere
* Destroyed when program ends

🎯 **Golden Rule for Interviews:**

> **Scope = Accessibility**
>
> **Lifetime = Memory Duration**
