### **Basic Level Questions**

1. **What is Python, and what are its key features?**
    - Python is a high-level, interpreted language known for its simplicity and readability. Key features include dynamic typing, memory management, and extensive standard libraries.
    

2. **What is a Python list, and how is it different from a tuple?**
    
    - Lists are mutable, meaning they can be modified, while tuples are immutable. Both can store collections of heterogeneous data.
```
	    # List Example 
	    
	    list_example = [1, 2, 3]
	    list_example[1] = 20 # Works because lists are mutable 
	    print("Modified list:", list_example)
	    
	    # Tuple Example 
	    
	    tuple_example = (1, 2, 3) 
	    try: 
		    tuple_example[1] = 20 # Raises an error because tuples are immutable 
	    except TypeError: 
		    print("Tuples are immutable, cannot modify.")
```
    

3. **How does Python handle memory management?**
    
    - Python uses automatic memory management, including a private heap and a built-in garbage collector to recycle unused memory.
    

4. **What are Python modules and packages?**
    
    - A module is a single file of Python code, and a package is a collection of modules organised into directories with `__init__.py` files.
    

5. **Explain the difference between `is` and `==` operators.**
    
    - `is` checks for object identity, i.e., whether two references point to the same object. `==` checks if two values are equivalent.
    

6. **What are `*args` and `**kwargs` in Python?**
    
    - `*args` passes a variable number of non-keyword arguments to a function, while `**kwargs` passes a variable number of keyword arguments.
    

7. **Explain list comprehensions with an example.**
    
    `squares = [x**2 for x in range(5)]`
    `# Output: [0, 1, 4, 9, 16]`
    

8. **What is the purpose of `__init__` in Python classes?**
    
    - `__init__` is the constructor method in Python used for initialising objects of a class.


### **Medium Level Questions**

1. **What are Python decorators, and how do you use them?**
    
    - Decorators modify the behaviour of a function or method. They wrap another function in a higher-order function.
    

2. **What are Python generators, and why are they used?**
    
    - Generators are iterators that yield values lazily, saving memory when dealing with large datasets.
    

4. **Explain the concept of closures in Python.**
    
    - A closure occurs when a nested function captures variables from its enclosing scope.

5. **What is a lambda function?**
    
    - A lambda function is an anonymous, inline function defined with the `lambda` keyword, often used for short functions.
    
    `add = lambda x, y: x + y`
    

6. **What is the difference between shallow and deep copy in Python?**
    
    - Shallow copy creates a new object but references nested objects, while deep copy creates a new object and recursively copies all objects it references.

7. **What is the Global Interpreter Lock (GIL), and how does it affect multi-threading in Python?**
    
    - The GIL prevents multiple native threads from executing Python byte-code simultaneously, affecting multi-threaded performance for CPU-bound tasks.

8. **What are magic methods in Python?**
    
    - Magic methods (like `__str__`, `__len__`, `__eq__`) are special methods used to define behaviour for built-in operations in Python classes.

9. **Explain the difference between `__str__` and `__repr__` in Python.**
    
    - `__str__` provides a readable string representation for end-users, while `__repr__` is meant to be unambiguous and for developers.

10. **How does exception handling work in Python?**
    
    - Python uses `try`, `except`, `else`, and `finally` blocks to catch and handle exceptions.

11. **What is the difference between `staticmethod` and `classmethod` in Python?**
    
    - `@staticmethod` doesn’t access class or instance data, while `@classmethod` can access the class (cls) but not instance data.

12. **How can you reverse a string in Python?**
    
    `reversed_str = "hello"[::-1] # Output: 'olleh'`
    

13. **What are the most common Python string methods, and how are they used?**
    
    - Methods like `join()`, `split()`, `replace()`, `strip()`, `find()`, `upper()`, `lower()`, etc., are commonly used to manipulate strings.

14. **Explain Python’s `with` statement.**
    
    - The `with` statement simplifies exception handling by encapsulating common resource management tasks, like file handling.
    
    `with open('file.txt', 'r') as file:     data = file.read()`
    

15. **What is a Python set, and how does it differ from a list?**
    
    - Sets are unordered collections of unique items, while lists are ordered collections that can contain duplicates.

16. **What is monkey patching in Python?**
    
    - Monkey patching refers to modifying or extending a class or module at runtime.

17. **Explain how Python handles inheritance and method resolution order (MRO).**
    
    - Python supports single and multiple inheritance. The MRO is the order in which base classes are searched for a method or attribute.

18. **What are Python iterators and iterables?**
    
    - An iterable is any object capable of returning its members one by one (e.g., lists, strings). An iterator is an object with a `__next__()` method that returns items from an iterable.

19. **Explain how `filter()`, `map()`, and `reduce()` work in Python.**

    
    `# Example usage: nums = [1, 2, 3, 4] squared = list(map(lambda x: x**2, nums)) # Output: [1, 4, 9, 16]`
    

20. **What is a metaclass in Python?**
    
    - Metaclasses define the behavior of a class, like a class factory. By default, Python classes are instances of the `type` metaclass.

21. **How does Python implement data hiding?**
    
    - Python uses a convention of prefixing variables or methods with `_` or `__` to indicate they are private, but it's not enforced.


### **Hard Level Questions**

31. **What is the difference between a thread and a process in Python?**
    
    - A thread runs in the same memory space, while a process runs in separate memory space. Use threads for I/O-bound tasks and processes for CPU-bound tasks.

32. **How does Python’s garbage collector work?**
    
    - Python uses reference counting and a cyclic garbage collector to manage memory and clean up objects with circular references.

33. **What are Python’s descriptors, and how are they used?**
    
    - Descriptors are objects that manage the attributes of other objects. A descriptor class must implement at least one method from `__get__`, `__set__`, or `__delete__`.

34. **What is memoization, and how would you implement it in Python?**
    
    - Memoization is an optimization technique to cache the results of expensive function calls. In Python, it can be implemented with `functools.lru_cache`.

35. **Explain the concept of coroutines and `asyncio` in Python.**
    
    - Coroutines allow non-blocking concurrency in Python using `async` and `await`. The `asyncio` module helps to run asynchronous tasks.

36. **What are Python’s `__slots__`, and why would you use them?**
    
    - `__slots__` limit the attributes an instance can have, which can reduce memory usage when creating many instances of a class.

37. **How would you implement a singleton design pattern in Python?**
    
```
    class Singleton:
	    _instance = None
	    def __new__(cls):
		    if cls._instance is None:
		        cls._instance = super(Singleton, cls).__new__(cls)
	        return cls._instance
```

38. **What is duck typing in Python?**
    
    - Duck typing is a concept where the type of an object is determined by its behavior (methods/properties) rather than its explicit type.

39. **What is the purpose of the `yield` keyword in Python?**
    
    - `yield` allows a function to return a value and later resume execution from where it left off, turning it into a generator.

40. **Explain the use of `super()` in Python.**
    
    - `super()` allows you to call methods from the parent class in a child class. It helps in multiple inheritance scenarios and ensures the MRO is followed.