Object-Oriented Programming (OOP) is a programming paradigm based on the concept of "objects", which can contain data and code: data in the form of fields (often known as attributes or properties), and code in the form of procedures (often known as methods).

Here are the key concepts of OOP:

1. **Classes and Objects**
2. **Encapsulation**
3. **Inheritance**
4. **Polymorphism**
5. **Abstraction**


### **Objects**:


**Objects** are a representation of real world objects like cars, dogs, or bikes. The objects share two main characteristics: **==data==** and **==behavior==**.

Cars have **data,** like number of wheels, number of doors, and seating capacity They also exhibit **behavior**: they can accelerate, stop, show how much fuel is left, and so many other things.

We identify **data** as **attributes** and **behavior** as **methods** in object-oriented programming. 

1. **Data → Attributes 
2. **Behavior → Methods

## Class:

A **class** is a blueprint for creating objects (a particular data structure), defining attributes and methods. An **object** is an instance of a class, and class is model for its objects.

**Class** it is just a model, or a way to define **attributes** and **behavior**.

Example :
```
# Defining a class named Car
class Car:
    # Constructor method to initialize the attributes of the class
    def __init__(self, brand, model, year):
        self.brand = brand
        self.model = model
        self.year = year
    
    # Method to display car information
    def display_info(self):
        print(f"{self.year} {self.brand} {self.model}")

# Creating objects of the Car class
car1 = Car("Toyota", "Camry", 2020)
car2 = Car("Honda", "Accord", 2021)

# Calling the display_info method for each object
car1.display_info()  # Output: 2020 Toyota Camry
car2.display_info()  # Output: 2021 Honda Accord
```

in this example, `Car` is a class, and `car1` and `car2` are objects (instances of the class).

## 3. Encapsulation:

**Encapsulation** is the bundling of data (attributes) and methods (functions) that operate on the data into a single unit or class, and restricting access to some of the object's components. It also restricts direct access to some of the object's components, which can prevent the accidental modification of data.

```
# Defining a class named BankAccount
class BankAccount:
    # Constructor method to initialize the attributes
    def __init__(self, account_number, balance):
        self.__account_number = account_number  # Private attribute
        self.__balance = balance  # Private attribute
    
    # Public method to deposit money
    def deposit(self, amount):
        if amount > 0:
            self.__balance += amount
    
    # Public method to withdraw money
    def withdraw(self, amount):
        if amount > 0 and amount <= self.__balance:
            self.__balance -= amount
    
    # Public method to get the balance
    def get_balance(self):
        return self.__balance

# Creating an object of BankAccount class
account = BankAccount("123456", 1000)

# Depositing and withdrawing money using public methods
account.deposit(500)
account.withdraw(200)

# Accessing the private attribute via a public method
print(account.get_balance())  # Output: 1300
```

Here, the attributes `__account_number` and `__balance` are private, meaning they cannot be accessed directly from outside the class. They can be accessed through the public methods `deposit`, `withdraw`, and `get_balance`.

## 3. Inheritance:

**Inheritance** is a way to form new classes using classes that have already been defined. It helps in code re-usability and establishing a relationship between different classes. Inheritance allows a class to inherit attributes and methods from another class, promoting code reuse.

```
# Defining a base class named Vehicle
class Vehicle:
    def __init__(self, brand, model):
        self.brand = brand
        self.model = model
    
    def display_info(self):
        print(f"Vehicle: {self.brand} {self.model}")

# Defining a derived class named Car that inherits from Vehicle
class Car(Vehicle):
    def __init__(self, brand, model, year):
        super().__init__(brand, model)  # Calling the constructor of the base class
        self.year = year
    
    def display_info(self):
        print(f"Car: {self.year} {self.brand} {self.model}")

# Creating objects of the derived class
car = Car("Toyota", "Camry", 2020)
car.display_info()  # Output: Car: 2020 Toyota Camry

```

Here, `Car` inherits from `Vehicle`. The `Car` class uses the `super()` function to call the constructor of the `Vehicle` class.


## 4. Polymorphism:

**Polymorphism** means the ability to take many forms. It allows methods to do different things based on the object it is acting upon.

```
# Defining a base class named Bird
class Bird:
    def make_sound(self):
        print("Bird sound")

# Defining derived classes that inherit from Bird
class Sparrow(Bird):
    def make_sound(self):
        print("Chirp chirp")

class Crow(Bird):
    def make_sound(self):
        print("Caw caw")

# Creating objects of derived classes
sparrow = Sparrow()
crow = Crow()

# Calling the make_sound method on different objects
sparrow.make_sound()  # Output: Chirp chirp
crow.make_sound()  # Output: Caw caw

```

Here, both `Sparrow` and `Crow` classes inherit from `Bird` and override the `make_sound` method. The method behaves differently based on the object.




## 5. Abstraction:

Abstraction is the concept of hiding the complex implementation details and showing only the essential features of the object.

```
from abc import ABC, abstractmethod

# Defining an abstract base class named Shape
class Shape(ABC):
    @abstractmethod
    def area(self):
        pass

# Defining a derived class named Rectangle that inherits from Shape
class Rectangle(Shape):
    def __init__(self, width, height):
        self.width = width
        self.height = height
    
    def area(self):
        return self.width * self.height

# Defining a derived class named Circle that inherits from Shape
class Circle(Shape):
    def __init__(self, radius):
        self.radius = radius
    
    def area(self):
        return 3.14 * self.radius * self.radius

# Creating objects of derived classes
rect = Rectangle(10, 20)
circ = Circle(5)

# Calling the area method on different objects
print(f"Rectangle area: {rect.area()}")  # Output: Rectangle area: 200
print(f"Circle area: {circ.area()}")  # Output: Circle area: 78.5

```

Here, `Shape` is an abstract class with an abstract method `area`. The `Rectangle` and `Circle` classes provide concrete implementations

