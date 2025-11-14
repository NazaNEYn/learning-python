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



