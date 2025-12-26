# Table of Contents

## 1. Slicing

* [The Simple Slice `[start:end]`](#the-simple-slice-startend)
* [The Full Slice `[start:end:step]`](#the-full-slice-startendstep)
* [Slicing Syntax Comparison](#slicing-syntax-comparison)
* [The Role of `[:]`](#the-role-of)

## 2. `[:]`

* [Assignment vs. Slicing/Shallow Copy](#assignment-vs-slicingshallow-copy)
* [Slicing/Shallow Copy](#slicingshallow-copy)
* [Assignment](#assignment)
* [The REAL difference](#the-real-difference)

## 3. When to Create a Shallow Copy

* [The Core Rule (Memorize This)](#the-core-rule-memorize-this)
* [Why This Rule Exists](#why-this-rule-exists)
* [Comparison: Original List vs Shallow Copy](#comparison-original-list-vs-shallow-copy)
    * [Case 1: Iterating Without Modifying (Safe)](#case-1-iterating-without-modifying-safe)
    * [Case 2: Modifying While Iterating (Danger)](#case-2-modifying-while-iterating-danger)
    * [Case 3: Modifying While Iterating (Correct Way)](#case-3-modifying-while-iterating-correct-way)
* [When You NEED a Shallow Copy](#when-you-need-a-shallow-copy)
* [When You Do NOT Need a Copy](#when-you-do-not-need-a-copy)
* [`os.walk()` Is a Special Case](#oswalk-is-a-special-case)
* [Mental Checklist (Use This)](#mental-checklist-use-this)
* [Summary Table](#summary-table)

## 4. Memory Location Control

* [1. Simple Assignment vs. Slicing Assignment (`[:]` on the Left)](#1-simple-assignment-vs-slicing-assignment--on-the-left)
    * [Simple Assignment: Used for Reassignment](#simple-assignment-used-for-reassignment)
    * [Slicing Assignment](#slicing-assignment)
* [2. Simple Assignment vs. Shallow Copy (`[:]` on the Right)](#2-simple-assignment-vs-shallow-copy--on-the-right)
    * [Simple Assignment: Used for Aliasing](#simple-assignment-used-for-aliasing)
    * [Shallow Copy](#shallow-copy)
* [Simplified Memory Action Table](#simplified-memory-action-table)

## 5. Memory Operations Comparison Table

* [Feature Comparison Table](#feature-comparison-table)
* [1. Simple Assignment vs. Shallow Copy (`[:]` on the Right)](#1-simple-assignment-vs-shallow-copy--on-the-right)
* [2. Simple Assignment vs. Slicing Assignment (`[:]` on the Left)](#2-simple-assignment-vs-slicing-assignment--on-the-left)


--------


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


--------------------

# Memory Location Control

## 1. Simple Assignment vs. Slicing Assignment (`[:]` on the Left)
`[:]` on the left is about Slicing Assignment and modifying an existing object in place.<br>
Simple Assignment vs Slicing Assignment location: Simple Assignment creates a new location but Slicing Assignment uses the same location

### Simple Assignment: Used for Reassignment
```python
list_Y = [40, 50, 60] 
print(f"ID START: {id(list_Y)}")

list_Y = [10, 20, 30]
print(f"ID END: {id(list_Y)}")
```

Output:
```
ID START: 2480118056512
ID END: 2480118070528
```

### Slicing Assignment
```python
list_x = [40, 50, 60] 
print(f"ID START: {id(list_x)}")

list_x[:] = [10, 20, 30]
print(f"ID END: {id(list_x)}")
```
Output:
```
ID START: 2480121598272
ID END: 2480121598272
```


## 2. Simple Assignment vs. Shallow Copy (`[:]` on the Right)
`[:]` on the right is about shallow copy and creating a safe copy.<br>
Simple Assignment creates a new location but shallow copy creates a new location. (Simple Assignment creates a new location because it performs reassignment on the variable, meaning the variable drops its pointer to the old object and points to a new object.)

### Simple Assignment: Used for Aliasing
```python
list_A = [1,2,3]
print(f"List A, ID START: {id(list_A)}")

list_B = list_A
print(f"List A, ID END: {id(list_A)}")
print(f"List B, ID END: {id(list_B)}")
```

Output:
```
List A, ID START: 2480130787392
List A, ID END: 2480130787392
List B, ID END: 2480130787392
```

### Shallow Copy
```python
list_C = [1,2,3]
print(f"List C, ID START: {id(list_C)}")

list_D = list_C[:]
print(f"List C, ID END: {id(list_C)}")
print(f"List D, ID END: {id(list_D)}")
```

Output:
```python
List C, ID START: 2480113799808
List C, ID END: 2480113799808
List D, ID END: 2480130017280
```


In a very sinmple term:

* Reassignment creates new location
* Slicing Assignment uses the same location

--

* Aliasing uses the same location
* Shallow copy creates new location

<br>

| Operation Type | Syntax | Action on Memory Location (ID) | Aliasing |
| :--- | :--- | :--- | :--- |
| Aliasing | `new_list = old_list` | SAME | YES |
| Shallow Copy | `new_list = old_list[:]` | NEW | NO |
| Reassignment | `old_list = [new_data]` | NEW | NO |
| Slicing Assignment | `old_list[:] = new_data` | SAME | YES |

<br>

| *Here is my [notebook](https://static.marimo.app/static/slicing-notation-q4rw) for the code snippets.*

---------

# Memory Operations Comparison Table


| Feature | 1. Simple Assignment (`list_B = list_A`) | 2. Shallow Copy (`list_B = list_A[:]`) | 3. Slicing Assignment (`list_B[:] = list_A`) |
| :--- | :--- | :--- | :--- |
| **Technical Term** | Aliasing / Reassignment | Shallow Copy | In-Place Content Replacement |
| **Location/Usage of `[:]`** | Not used (uses only `=`) | Right Side (used to create a value) | Left Side (used as a target) |
| **Action on the Container (The List Itself)** | Variable `list_B` now points to the **SAME** object as `list_A`. | A **NEW** list object (container) is created for `list_B`. | The **SAME** list object (`list_B`) is kept, but its contents are overwritten. |
| **Memory ID of Target List** | **SAME ID** as `list_A` (They are aliases). | **NEW ID** (It's a separate object). | **SAME ID** as it had before the operation. |
| **Action on Simple Contents (e.g., numbers)** | Shared, but changing one creates a **NEW** number object (safe). | Copied into the new container (independent). | Replaced with new values (independent). |
| **Action on Mutable Contents (e.g., nested lists)** | Shared (They are all aliases, so they see the change). | **SHARED REFERENCE.** Both lists point to the **SAME** inner object. (**UNSAFE** for mutable data) | The contents of the inner list in `list_A` are copied into `list_B`. (If `list_A` contained mutable objects, those inner references are still copied, similar to shallow copy.) |
| **Summary of Dependence** | **FULLY DEPENDENT** (Everything is linked). | **PARTIALLY DEPENDENT** (Outer list is safe, inner mutable objects are linked). | **INDEPENDENT** (The resulting `list_B` is independent of the source `list_A`). |





# 1. Simple Assignment vs. Shallow Copy (`[:]` on the Right)
This comparison shows how to create an alias (link) versus an independent copy.

| Feature | Simple Assignment (`=`) | Shallow Copy (`old[:]` on the Right) |
| :--- | :--- | :--- |
| **Example Code** | `new_list = old_list` | `new_list = old_list[:]` |
| **Object Creation** | **NO**—The operation only copies the memory reference. | **YES**—A new list container is created in memory. |
| **Memory ID (Container)** | **STAYS THE SAME** (`id(new_list) == id(old_list)`). | **CHANGES** (`id(new_list) != id(old_list)`). |
| **Relationship** | **Aliased (Linked):** They are two names for one object. | **Independent** (at the top level). |
| **Impact of Modification** | Modifying `new_list` always changes `old_list` (and vice versa). | Modifying `new_list` never changes `old_list` (unless nested mutable objects are involved). |
| **Purpose** | To give an existing object an alternative name (alias). | To create a separate, independent version of the list. |


# 2. Simple Assignment vs. Slicing Assignment (`[:]` on the Left)
This comparison shows the difference between creating a new object versus modifying an existing object in place.

| Feature | Simple Assignment (`=`) | Slicing Assignment (`[:]` on the Left) |
| :--- | :--- | :--- |
| **Example Code** | `old_list = new_content` | `old_list[:] = new_content` |
| **Object Creation** | **YES**—A new list object is created for `new_content`. | **NO**—The existing list object is modified directly. |
| **Memory ID of `old_list`** | **CHANGES** (`id(old_list)` is now a new address). | **STAYS THE SAME** (`id(old_list)` is preserved). |
| **Effect on Aliases** | **Breaks Aliases:** If `list_Z` was an alias of `old_list`, `list_Z` is now pointing to the old content. | **Preserves Aliases:** All aliases (like `list_Z`) are instantly updated because the single object they all point to has been modified. |
| **Technical Term** | Reassignment (New reference, new object). | In-Place Content Replacement (Same reference, modified object). |
