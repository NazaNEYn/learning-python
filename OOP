## OOP  (Object-Oriented Programming) : 
In OOP we are trying to model  real life objects. <br>

Objects :
* Have things (Arttributes/Variables) : <br>
  is_holding_plate = True <br>
  tables = [4, 3 , 2]
* Do things. Like some kinda of functionality. (Methods) <br>
  def take_order(table, order) <br>

**An object** is basically combining a peice of data (attributes) and some kinda of functionality (methods). <br>
We can have multiple objects, generated from the same type. <br>

**Class , Object :** <br>
car = CarBlueprint() <br>
`car` is an object that is generetad from the `CarBlueprint()` class.


-------------------------------------------------
## Creating `classes`:

```python
class User:
    def __init__(self):
        pass
```

Example:

```python
class User:
    def __init__(self):
        print("New user has been created")
```

*Note:* 
<br>
The `__init__` method in a Python class is a special method that gets called automatically every single time you create a new object (or "instance") from that class.

```python
class User:
    def __init__(self):
        print("New user has been created")

user_1 = User() # __init__ called (1st time)
user_2 = User() # __init__ called (2nd time)
user_3 = User() # __init__ called (3rd time)
user_4 = User() # __init__ called (4th time)

# New user has been created
# New user has been created
# New user has been created
# New user has been created
```


This is why `__init__` is often called the constructor in other programming languages. Its main job is to initialize the attributes (the starting data) of the brand new object that's being created.
<br>

-------------------------------------------------

## `self.`:

**You need `self.` for an attribute when you want to access or change a value that is a permanent part of the object.**

You **don't** need `self.` when you are talking about a temporary value, like a parameter that was just passed into the method.<br>

We need to use `self` for an attribute when we want to make that attribute a part of the object itself. We don't need to use `self` when the attribute is a simple variable that only exists inside a function and disappears when the function is finished.


### What is `self.`?

Imagine you're building a robot. Each robot needs to have its own color, right? When you create a robot, you want to say, "This robot's color is red." The word `self` is like pointing to that specific robot and saying, "Hey, you (the robot), your color is red."

When you define an attribute like `self.color = "red"`, you are attaching the `color` attribute directly to the specific object you've created. This means every time you talk about that robot, you can ask it, "What's your color?" and it will remember.


### When to Use `self.`?
You should use `self` for an attribute when you want that attribute to be saved and remembered by the object. This is usually done inside the `__init__` function (the special function that runs when you create a new object).

For example, let's say you're building a Car class. Each `car` has a `brand` and a `color`. You want each car object to remember its own brand and color.

```python
class Car:
    def __init__(self, brand, color):
        # We use self here so that the object remembers its brand and color.
        self.brand = brand
        self.color = color

# Now we can create a car object.
my_car = Car("Honda", "blue")

# We can access the attributes we saved.
print(my_car.brand)  # Output: Honda
print(my_car.color)  # Output: blue
```

In this example, `my_car` is an object, and its `brand` is "Honda". If you create another car, `your_car`, its brand can be something different, like "Toyota". The `self` makes sure each car has its own brand and color.

### When to NOT Use `self.`:

You don't need to use `self` for an attribute if the attribute is just a temporary variable that's only needed for a little while, inside a specific function. Once the function is done, the variable is forgotten.<br>

Let's say you have a function inside your Car class that calculates a special code for the car, but you don't need the `car` to remember this code forever.

```python
class Car:
    def __init__(self, brand, color):
        self.brand = brand
        self.color = color

    def calculate_code(self):
        # 'temporary_code' is a simple variable, not an attribute of the object.
        # It's only needed inside this function and is forgotten afterwards.
        temporary_code = "XYZ-" + self.brand
        return temporary_code

my_car = Car("Honda", "blue")
car_code = my_car.calculate_code()

print(car_code)  # Output: XYZ-Honda
```

Here, `temporary_code` is not part of `self`. It's just a variable that's used to hold a value for a moment while the function is running. Once `calculate_code` is finished, `temporary_code` is gone. You can't say `my_car.temporary_code` because it doesn't belong to the car object.

-------------------------------------


## Class inheritance

it's a way for a new class to inherit or "borrow" properties (attributes) and behaviors (methods) from an existing class. <br>

Think of it like a family tree. A **parent class** (or **base class** or **superclass**) is like a parent. It has certain traits, like a last name or eye color. A **child class** (or **derived class** or **subclass**) is like a child. It can inherit those traits from the parent. <br>


Syntax :
```python
class Fish(Animal):
    def __init__(self):
        super().__init__()
```

This is our `Fish` class
```python
class Fish:
    def __init__(self):
```

For a class to inherit from another class, all we have to do is:
```python
class Fish(Animal):
    def __init__(self):
        super().__init__()
```

**What `super()` does**

The `super()` function is a special tool in Python that allows a child class to call a method from its parent class.<br>

*Note:* If you don't call `super().__init__()`, the child class's `__init__` method will completely override the parent's `__init__` method.



### Modifying a Method:

```python
class Animal:
    def __init__(self, name, animal_type):
        self.name = name
        self.animal_type = animal_type
        print(f"Say hello to {self.name}!")
        print(f"{self.name} is a {self.animal_type}")

    def sleep(self):
        print(f"{self.name} is currently sleeping")


dog = Animal("Rex", "dog")

print("---------------------------------------")

class Cat(Animal):
    def __init__(self, name, animal_type):
        super().__init__(name, animal_type)

    # Modifying the method
    def sleep(self):
        super().sleep()
        print(f"Wake {self.name} up!")


cat = Cat("Alex", "cat")
cat.sleep()
```

### Overriding a Method:

```python
class Animal:
    def __init__(self, name, animal_type):
        self.name = name
        self.animal_type = animal_type
        print(f"Say hello to {self.name}!")
        print(f"{self.name} is a {self.animal_type}")

    def sleep(self):
        print(f"{self.name} is currently sleeping")


dog = Animal("Rex", "dog")

print("---------------------------------------")

class Cat(Animal):
    def __init__(self, name, animal_type):
        super().__init__(name, animal_type)

    # Overriding a Method
    def sleep(self):
        print(f"Wake {self.name} up!")


cat = Cat("Alex", "cat")
cat.sleep()
```

-------------------------------------
## What Goes in the Main File?

**Import Statements:** All import statements, like from character import Character, belong here.

**Object Creation:** This is where you create all the objects from your classes, like player = Character(...) and enemy = Character(...).

**Game Logic:** This includes everything that controls the game's flow, like the while True game loop, the input() commands, and the if/else statements that decide what happens next.

**Calling Methods:** The main file's job is to call the methods of your objects, like player.attack(enemy).

Think of it like a movie: The classes are the actors—they know how to perform specific actions. The main file is the script and director—it tells the actors when to perform their actions and in what order.
