# `tkinter` Module

(Official Doc)[https://www.tcl-lang.org/man/tcl8.4/TkCmd/contents.htm}

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


# How to update the lable:

[Setting Options](https://docs.python.org/3/library/tkinter.html#handy-reference)

```python
my_label = tkinter.Label(text="I am a label", font=("Arial", 24, "bold"))

my_label.pack()

my_label["text"] = "New text"
# OR
my_label.config(text="New Text")
```


# How to create a button:

```python
button = tk.Button(text="Click Me")
button.pack()
```
