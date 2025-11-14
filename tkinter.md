# `tkinter` Module

```python
import tkinter


window = tkinter.Tk()
window.title("GUI Program")
window.minsize(500, 300)

# Label
# 1. first create a label/component
my_label = tkinter.Label(text="I am a label", font=("Arial", 24, "bold"))

# 2. choosing how to call the label/component
# `pack` is a method to center the text
my_label.pack()


# ##############################
# To keep the window pop up
window.mainloop()
```

-----

# Tkinter `pack()` Geometry Manager Documentation

The **`pack()`** geometry manager is one of the simplest methods in Tkinter for organizing and positioning widgets in a container (like a `Frame` or the root window). It uses a simpler, more abstract approach than `grid()` or `place()`, arranging widgets in blocks **before** them.

---

## How `pack()` Works

`pack()` treats its container as a series of blocks. When you pack a widget, you tell Tkinter which side of the container (or the side of the last packed widget) to place the new widget on. Tkinter then determines the minimum size needed for the widget and allocates the necessary space.

* Widgets are typically placed in the order they are packed.
* Once a side is used, the remaining space in the container is reduced, and subsequent widgets are packed into that smaller remaining area.

---

## Key Options (Arguments)

The `pack()` method accepts several keyword arguments to control a widget's placement and behavior.

### 1. `side`

Specifies which side of the container (or the remaining area) the widget should be placed against.

| Value | Description |
| :---: | :--- |
| **`'top'`** (Default) | Packs the widget against the top edge. |
| **`'bottom'`** | Packs the widget against the bottom edge. |
| **`'left'`** | Packs the widget against the left edge. |
| **`'right'`** | Packs the widget against the right edge. |

### 2. `fill`

Determines if and how the widget should **expand** to fill any extra space in the container allocated to it *along a single axis*.

| Value | Description |
| :---: | :--- |
| **`'none'`** (Default) | Widget retains its preferred size. |
| **`'x'`** | Fills the space horizontally. |
| **`'y'`** | Fills the space vertically. |
| **`'both'`** | Fills the space both horizontally and vertically. |

### 3. `expand`

A boolean (`True` or `False`) that controls whether the widget should take up **extra space** in the parent window.

* If `**expand=True**`, the widget will be centered in the extra space allocated by the packer. This space is what remains *after* all widgets have been given their preferred sizes.
* It's often used with `fill` to make widgets grow when the window is resized.

### 4. Padding Options

These options add empty space around the widget.

* **`padx`** (External Padding X): Adds horizontal space **outside** the widget's border.
* **`pady`** (External Padding Y): Adds vertical space **outside** the widget's border.
* **`ipadx`** (Internal Padding X): Adds horizontal space **inside** the widget's border (padding *within* the widget itself).
* **`ipady`** (Internal Padding Y): Adds vertical space **inside** the widget's border.

---

## Example Usage

Here is a simple example demonstrating some of the common arguments:

```python
import tkinter as tk

root = tk.Tk()
root.title("Pack Example")

# 1. Widget packed with default settings (side='top', fill='none', expand=False)
label1 = tk.Label(root, text="Top Default", bg="lightblue")
label1.pack() 

# 2. Widget packed against the left, filling available vertical space
label2 = tk.Label(root, text="Left and Fill Y", bg="lightgreen")
label2.pack(side='left', fill='y') 

# 3. Widget packed against the bottom, with external padding
label3 = tk.Label(root, text="Bottom with Padding", bg="yellow")
label3.pack(side='bottom', pady=10) 

# 4. Widget that expands to fill any extra available space in the main container
label4 = tk.Label(root, text="Expands & Fills Both", bg="orange")
label4.pack(expand=True, fill='both', padx=5, pady=5)

root.mainloop()
```


## Advanced Options

### 5. Stacking Order (`before` and `after`) 

These options allow you to explicitly control the packing order relative to another widget object, overriding the default order of creation.

* **`after=other_widget`**: Places the current widget immediately **after** the specified widget in the packing order.
* **`before=other_widget`**: Places the current widget immediately **before** the specified widget in the packing order.

### 6. Anchor (`anchor`)

Specifies where the widget should be placed within its allocated space when the widget's requested size is **smaller** than the available space (e.g., when padding or `expand` is used without `fill`).

| Value | Location | Value | Location |
| :---: | :---: | :---: | :---: |
| **`'n'`** | North (Top) | **`'s'`** | South (Bottom) |
| **`'e'`** | East (Right) | **`'w'`** | West (Left) |
| **`'ne'`** | Northeast | **`'nw'`** | Northwest |
| **`'se'`** | Southeast | **`'sw'`** | Southwest |
| **`'center'`** (Default) | Center | | |

---

## Example Code Snippet

```python
import tkinter as tk

root = tk.Tk()

# 1. Simple 'top' placement with internal padding
label1 = tk.Label(root, text="Basic", bg="lightblue")
label1.pack(ipady=5)

# 2. Packed left, filling vertical space, expanding horizontally
label2 = tk.Label(root, text="Fill Y, Expand", bg="lightgreen")
label2.pack(side='left', fill='y', expand=True)

# 3. Packed right, anchored to the bottom-right corner of its space
label3 = tk.Label(root, text="Anchor SE", bg="yellow")
label3.pack(side='right', anchor='se', padx=10, pady=10) 

root.mainloop()
```

-----


