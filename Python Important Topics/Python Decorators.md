Python **decorators** are a powerful and expressive way to modify or extend the behaviour of functions or methods without permanently modifying it. Decorators are essentially functions that take another function as an argument, extend its behaviour, and return a new function. They are often used for logging, enforcing access control, instrumentation, and caching, among other tasks.

```
def log_decorator(func):
    def wrapper(*args, **kwargs):
        print(f"Calling function '{func.__name__}' with arguments {args} and {kwargs}")
        result = func(*args, **kwargs)  # Call the original function
        print(f"Function '{func.__name__}' executed successfully.")
        return result
    return wrapper

@log_decorator
def add(a, b):
    return a + b

@log_decorator
def greet(name):
    print(f"Hello, {name}!")

# Using the decorated functions
result = add(3, 5)
print(f"Result: {result}")

greet("Alice")

```

### Explanation:

- **`*args, **kwargs`**: These allow the decorator to handle functions with any number of positional and keyword arguments.
- The decorator logs the function name and arguments before and after calling the function.
### Output:

```
Calling function 'add' with arguments (3, 5) and {}
Function 'add' executed successfully.
Result: 8
Calling function 'greet' with arguments ('Alice',) and {}
Hello, Alice!
Function 'greet' executed successfully.

```