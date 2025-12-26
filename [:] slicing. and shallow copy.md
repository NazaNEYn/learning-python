# Slicing:

**The Simple Slice** `[start:end]` <br>
The most basic slice uses two numbers: a **start** and an **end**.

* **start:** This is the index where your slice begins. The item at this index is **included**.
* **end:** This is the index where your slice stops. The item at this index is **not included**.

For example, let's say we have a list of fruits: `fruits = ["apple", "banana", "cherry", "date", "elderberry"]`

`fruits[1:4]` would give you `["banana", "cherry", "date"]`. It starts at index 1 ("banana") and goes up to, but not including, index 4 ("elderberry").


**The Full Slice** `[start:end:step]` <br>

You can add a third number, the **step**, to control how you "walk" through the sequence.

* **step:** This tells Python how many items to skip after each one it grabs. The default is 1. If you set the step to 2, you'll get every second item.

`numbers = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]`
`numbers[1:8:2]` would give you `[1, 3, 5, 7]`. It starts at index 1, goes up to but not including index 8, and grabs every second number.


| Syntax | Colons Used | What It Does |
| :--- | :--- | :--- |
| `my_list[1:8]` | Single colon `:` | Slices from index 1 to 8 (not including 8) with the default step of 1. |
| `my_list[1:8:2]` | Two colons `::` (a "double colon" operation) | Slices from index 1 to 8, taking every second item. |
| `my_list[::2]` | Two colons `::` | Shortcut for `my_list[0:len(my_list):2]`. Takes every second item from the beginning to the end. |


*Note:* <br>
The double colon `::` is not a different part of the syntax; it's just Python's way of saying **"leave the start and end values empty"** so you can jump right to the step.

| Form Field | Your Request (`my_list[1:8:2]`) | Shortcut (`my_list[::2]`) |
| :--- | :--- | :--- |
| **Start Index** | 1 | (leave blank) |
| **End Index** | 8 | (leave blank) |
| **Step** | 2 | 2 |

When you leave those fields blank, Python uses its default values: **start** becomes 0 and **end** becomes the end of the sequence. <br>
So, the double colon `::` is just a concise way to signal that you want to use the default start and end, but still specify a **step**. <br><br>


*Note:* `[:]` can act differently, based on the context.<br>
It depends on how it’s used.<br>
It is one syntax, but its behavior and purpose change depending on context and data structure.

---------------------------------

# `[:]`

The usage of `[:]` is fundamentally about controlling how Python interacts with memory references and object boundaries.


---------------------


# Assignment vs. Slicing/Shallow Copy

**Slicing/Shallow Copy**

```python
test = [1, 2, 3, 4, 5, 6, 7, 8, 9]

copy_num = test[:]
print(copy_num)

# [1, 2, 3, 4, 5, 6, 7, 8, 9]
```

VS

**Assignment**

```python
test = [1, 2, 3, 4, 5, 6, 7, 8, 9]

copy_num = test
print(copy_num)

# [1, 2, 3, 4, 5, 6, 7, 8, 9]
```

If you print the result, the result is the same because you’re printing the **contents**, not the memory

## Slicing/Shallow Copy

```python
test = [1, 2, 3, 4, 5, 6, 7, 8, 9]

copy_num = test[:]
print(copy_num)
```

### What this means:

When you execute an operation like `test[:]` to create a new list:

* `test[:]` creates a **new list** in memory.
* The **values** from the original list are copied into that new list.
* `test` and the new list (e.g., `copy_num`) are two **different lists in memory**.

Think of it like:

> Writing the same numbers on two separate pieces of paper.



## Assignment

```python
test = [1, 2, 3, 4, 5, 6, 7, 8, 9]

copy_num = test
print(copy_num)
```

### What this means:

When you assign a list using simple assignment (e.g., `copy_num = test`):

* **No new list is created.**
* `copy_num` just becomes another **name** for the original list (`test`).
* `test` and `copy_num` both **point to the same list in memory.**

Think of it like:

> Two labels stuck on the same piece of paper.


## The REAL difference
Let's try to modify them and see what happens

**Slicing/Shallow Copy**

```python
test = [1, 2, 3, 4, 5, 6, 7, 8, 9]

copy_num = test[:]

copy_num.append(10)
print(f"Slicing: {copy_num}")
print(f"Slicing: {test}")
```

Output:

```
Slicing: [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
Slicing: [1, 2, 3, 4, 5, 6, 7, 8, 9]
```

**Assignment**

```python
test1 = [1, 2, 3, 4, 5, 6, 7, 8, 9]

copy_num1 = test1
copy_num1.append(10)
print(f"Assignment: {copy_num1}")
print(f"Assignment: {test1}")
```

Output:

```
Assignment: [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
Assignment: [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
```

-------------------

# when to create a shallow copy


## The Core Rule (Memorize This)

> **If you change a list while looping over it → do NOT loop over the original list.**

That’s it. Everything else is details.


## Why This Rule Exists
When Python loops over a list, it uses indexes internally.
If you:

* remove items
* insert items
* reorder items

the indexes shift, and Python gets confused about “what comes next”.
This causes:

* skipped items
* unexpected behavior
* bugs that don’t crash but give wrong results (worst kind)


# Comparison: Original List vs Shallow Copy

## Case 1: Iterating Without Modifying (Safe)
**Scenario**
You only read items.
```python
for x in my_list:
    print(x)
```
*  Safe
*  No copy needed
*  Most common case
Use this by default.


## Case 2: Modifying While Iterating (Danger)
**Scenario**
You remove items:
```python
for x in my_list:
    if x == "bad":
        my_list.remove(x)
```
*  Dangerous
*  Skips elements
*  Unpredictable behavior
You should never do this.


## Case 3: Modifying While Iterating (Correct Way)
**Scenario**
You remove items, but safely:
```python
for x in my_list[:]:
    if x == "bad":
        my_list.remove(x)
```
*  Safe
*  Loop is stable
*  Original list changes
This is where shallow copies are needed.

## When You NEED a Shallow Copy
You need `list[:]` when **ALL** of these are true:

| Condition | Yes / No |
| :--- | :--- |
| Looping over a list | ✅ |
| Modifying the same list | ✅ |
| Order/index matters | ✅ |

If all three are **YES** → make a copy


## When You Do NOT Need a Copy

| Situation | Copy Needed? |
| :--- | :--- |
| Only reading values | ❌ |
| Building a new list | ❌ |
| Appending to a different list | ❌ |
| Using `append()` on another list | ❌ |
| Looping over dict keys | ❌ |

**Example (no copy needed):**
```python
result = []
for x in my_list:
    if x > 0:
        result.append(x)
```


## `os.walk()` Is a Special Case
You **MUST**:

* modify subfolders
* while looping
* without breaking traversal

## Mental Checklist (Use This)
Before modifying a list in a loop, ask:

* **Am I changing this list?**
* **Am I looping over it?**
  * **Do I care about correctness?**

If yes to all → copy first


## Summary Table 

| Situation | Iterate Over |
| :--- | :--- |
| Read-only loop | `my_list` |
| Modify list items | `my_list[:]` |
| Build new list | `my_list` |
| `os.walk` subfolders | `subfolders[:]` |
