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
So, the double colon `::` is just a concise way to signal that you want to use the default start and end, but still specify a **step**.


---------------------------------


