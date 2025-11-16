# Tk Entry Widget Documentation (Python: `tkinter.Entry`)

The `entry` widget is used to display and edit a single line of text. Entries may contain only text, and all characters in an entry must belong to the same font.

---

## Basic Syntax & Creation

In Python's `tkinter`, the `entry` widget is created using the `tkinter.Entry` class.

### Creation

```python
import tkinter as tk

# Syntax: tk.Entry(master, options)
entry_widget = tk.Entry(parent_widget, width=30, textvariable=input_var)
```

--------


## Options

The following options control the appearance and behavior of the entry widget:

| Option | Description | Default |
| :--- | :--- | :--- |
| **background** / **bg** | Background color of the entry area. | System dependent |
| **borderwidth** / **bd** | Width of the border around the entry. | 1-2 pixels |
| **cursor** | Mouse cursor to use when over the entry. | `xterm` |
| **exportselection** | Boolean. If true, selected text is exported to the selection buffer. | `True` |
| **font** | Font for the text displayed in the entry. | System dependent |
| **foreground** / **fg** | Color of the text. | System dependent |
| **insertbackground** | Background color of the insertion cursor. | `Black` |
| **insertborderwidth** | Border width of the insertion cursor. | 0 |
| **insertofftime** | The number of milliseconds the insertion cursor is "off" when blinking. | 300 |
| **insertontime** | The number of milliseconds the insertion cursor is "on" when blinking. | 600 |
| **insertwidth** | Width of the insertion cursor. | 2 |
| **justify** | How the text is justified: `left`, `center`, or `right`. | `left` |
| **readonlybackground** | Background color when the `state` is set to `readonly`. | System dependent |
| **relief** | 3D effect: `raised`, `sunken`, `flat`, `ridge`, `groove`. | `sunken` |
| **selectbackground** | Background color of selected text. | System dependent |
| **selectborderwidth** | Border width of the selection highlight. | 0 |
| **selectforeground** | Text color of selected text. | System dependent |
| **show** | Character to display instead of the actual text (e.g., `'*'` for passwords). | Empty string (shows text) |
| **state** | The widget state: `normal`, `disabled`, or `readonly`. | `normal` |
| **textvariable** | A `tkinter.StringVar` object linked to the entry's content. Recommended for getting/setting content. | `None` |
| **takefocus** | Determines whether the widget accepts keyboard focus. | System dependent |
| **width** | Width of the entry in characters (not pixels). | System dependent |
| **xscrollcommand** | Associates a scrollbar with the entry for horizontal scrolling. | `None` |


------

##  Widget Commands (Methods)

The entry widget supports several **methods (commands)** for manipulating its text and cursor position.

| Method | Description | Example |
| :--- | :--- | :--- |
| **delete**(*first*, *last*=None) | Deletes one or more characters. *first* and *last* are index positions. If *last* is omitted, only the character at *first* is deleted. | `entry.delete(0, tk.END)` (Clear all) |
| **get**() | Returns the entry's current text as a string. (Often preferred to use `textvariable.get()`) | `content = entry.get()` |
| **icursor**(*index*) | Sets the position of the insertion cursor (the blinking bar) to the specified index. | `entry.icursor(tk.END)` (Move to end) |
| **index**(*indexName*) | Returns the numerical index corresponding to a named index (e.g., `tk.INSERT`, `tk.END`). | `pos = entry.index(tk.INSERT)` |
| **insert**(*index*, *text*) | Inserts the given text before the character at the specified index. | `entry.insert(0, "Prefix: ")` |
| **scan_mark**(*x*) | Used for implementing fast scrolling. Records the current view position corresponding to screen coordinate *x*. | (Used internally for mouse scrolling) |
| **scan_dragto**(*x*) | Used for fast scrolling. Adjusts the view relative to the position marked by `scan_mark`. | (Used internally for mouse scrolling) |
| **selection_adjust**(*index*) | Adjusts the selection so the character at *index* is included and is the anchor. | `entry.selection_adjust(10)` |
| **selection_clear**() | Removes the selection from the entry. | `entry.selection_clear()` |
| **selection_from**(*index*) | Sets the selection anchor to the character at *index*. | `entry.selection_from(0)` |
| **selection_present**() | Returns `True` if there is a selection, `False` otherwise. | `if entry.selection_present(): ...` |
| **selection_range**(*start*, *end*) | Sets the selection to span from the character at *start* up to (but not including) the character at *end*. | `entry.selection_range(0, 5)` |
| **selection_to**(*index*) | Extends the selection from the anchor to the character at *index*. | `entry.selection_to(tk.END)` |
| **xview**(*moveto/scroll*, *args) | Used to change the set of characters visible in the entry window (horizontal scrolling). | `entry.xview('scroll', 1, 'units')` |


------


## Important Indices

Entry indices refer to positions *between* characters.

| Index | Description | Example Position |
| :--- | :--- | :--- |
| **number** | A numerical character position (e.g., **0** is before the first character). | `entry.insert(1, "A")` |
| **tk.INSERT** | The position of the insertion cursor. | |
| **tk.ANCHOR** | The end of the selection that is not the cursor (the fixed point). | |
| **tk.END** | The position just after the last character in the entry. | `entry.delete(0, tk.END)` |

-----


## State Management (`show`)

---

### Password Fields (`show` Option)

To create a password field where typed characters are masked, use the `show` option:

```python
password_entry = tk.Entry(root, show='*')
```

------


## 🔒 Disabling Input (`state` Option)

To prevent the user from editing the text, you can configure the entry's `state` option:

```python
# Prevent user modification, selection, and scrolling
entry.config(state=tk.DISABLED) 

# Prevent user modification, but still allow selection and scrolling
entry.config(state=tk.READONLY)
```

To re-enable editing, set the state back to `tk.NORMAL`.
