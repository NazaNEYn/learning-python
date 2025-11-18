# Tkinter Canvas Widget Documentation

The `Canvas` widget is a versatile, rectangular drawing surface used to display and manipulate custom graphics, images, text, and even other Tkinter widgets using absolute coordinates. It is the primary tool for creating simple games, custom visualizers, and complex layouts where precise positioning is required.

---

## Basic Syntax and Creation

The Canvas widget is created with specified dimensions and a background color.

### Creation

```python
import tkinter as tk

# Syntax: tk.Canvas(master, options)
canvas = tk.Canvas(
    root, 
    width=600, 
    height=400, 
    bg="white"
)
canvas.pack()
```


------


## Key Configuration Options

| Option | Description | Default |
| :--- | :--- | :--- |
| **width** | Width of the canvas area in pixels. | System dependent |
| **height** | Height of the canvas area in pixels. | System dependent |
| **background / bg** | Background color of the canvas. | System dependent |
| **borderwidth / bd** | Width of the border around the canvas. | 0 |
| **relief** | 3D effect of the border (flat, raised, sunken, ridge, groove). | flat |
| **scrollregion** | Defines the bounding box of all items, enabling scrolling. | Auto-calculated |
| **xscrollcommand / yscrollcommand** | Links the canvas to a horizontal/vertical scrollbar. | None |


----- 


## Coordinate System

The Canvas uses a standard **2D Cartesian coordinate system**:

* The **origin (0, 0)** is located at the **upper-left corner** of the canvas.
* The **X-coordinate** increases as you move **right**.
* The **Y-coordinate** increases as you move **down**.


------


## Core Item Creation Methods

Items drawn on a Canvas are called "**Canvas Items**." All creation methods return a **unique Item ID** (an integer) used for later manipulation.

| Method | Arguments (Coordinates) | Description |
| :--- | :--- | :--- |
| `create_rectangle()` | `(x1, y1, x2, y2)` | Draws a rectangle defined by the **top-left** and **bottom-right** corners. |
| `create_oval()` | `(x1, y1, x2, y2)` | Draws an oval (ellipse or circle) **inscribed within the bounding box**. |
| `create_line()` | `(x1, y1, x2, y2, ...)` | Draws a **straight line** or series of connected lines. |
| `create_polygon()` | `(x1, y1, x2, y2, ...)` | Draws a **closed shape** with specified vertices. |
| `create_text()` | `(x, y)` | Draws text **centered** at the given coordinate. |
| `create_image()` | `(x, y)` | Displays a Tkinter `PhotoImage` or PIL `ImageTk` object. |
| `create_window()` | `(x, y)` | Places another **standard Tkinter widget** (like a Button or Entry) on the canvas. |

```python
# Draws a red line from (0, 0) to (500, 400)
line_id = canvas.create_line(0, 0, 500, 400, fill="red", width=2)

# Places a text label
text_id = canvas.create_text(
    300, 200, 
    text="Hello Canvas", 
    font=("Arial", 16)
)
```

### How to create an image:
```python
canvas = Canvas(width=200, height=224)
img = PhotoImage(file="img.png")
canvas.create_image(100, 112, image=img)
canvas.pack()
```

-----

## Item Manipulation and Configuration

You can change the properties, position, and visibility of any canvas item using its **Item ID** or a **Tag** (a named group of items).

### Key Manipulation Methods

| Method | Arguments | Description |
| :--- | :--- | :--- |
| `coords()` | `(item_id or tag), (new_x1, new_y1, ...)` | Sets new **coordinates** for the specified item(s). |
| `move()` | `(item_id or tag, dx, dy)` | Moves the item(s) by a **relative amount** (`delta_x`, `delta_y`). |
| `itemconfig()` | `(item_id or tag, **options)` | **Modifies the configuration options** (e.g., color, outline) of the item(s). Example: `(item_id, fill="green")` |
| `delete()` | `(item_id or tag)` | **Deletes** the specified item(s). `canvas.delete("all")` clears the entire canvas. |
| `tag_bind()` | `(tag, sequence, func)` | **Binds a Tkinter event sequence** (like a mouse click) to an item or group of items. Example: `("square", "<Button-1>", on_click)` |




------


## Tagging

You can assign **tags** when creating an item or later using `itemconfig()`:

```python
# Creates a blue square with the tag "square"
rect_id = canvas.create_rectangle(10, 10, 100, 100, fill="blue", tags=("shape", "square"))

# Move all items with the tag "shape"
canvas.move("shape", 10, 0)
```


----



##  Finding Items

These methods are essential for interactive graphics, allowing you to identify what the user is clicking or what is in a specific area.

| Method | Arguments | Description |
| :--- | :--- | :--- |
| `find_closest()` | `(x, y)` | Returns the **ID of the item closest** to the given coordinates. Example: `(mouse_x, mouse_y)` |
| `find_withtag()` | `(tag)` | Returns a **tuple of all Item IDs** that have the given tag. Example: `("square")` |
| `find_overlapping()` | `(x1, y1, x2, y2)` | Returns the **IDs of all items that overlap** with the defined bounding box. Example: `(box_x1, box_y1, ...)` |

------
