## Coding and Style Guide for Open Source Plugins
The purpose of this document is to lay out coding and style guidance for contributors to use when developing and revising Indigo's codebase. Adhering to these styles 
helps to keep Indigo's codebae uniform across the framework and help other contributors and reviewers to more easily understand your code. Be sure to also take a look at the [contributor's guidance](./README.md). 

There are a few fundamental points that your submission should include:
1. Keep code to manageable chunks -- collapsing too much code and logic into a single file makes it much harder to manage going forward.
2. Explicit is better than implicit -- where possible, make it obvious what your code does.
3. Document your code -- including comments that explain the purpose of your code if the intent is not obvious to a cold reader.
4. Be Pythonic -- adherence to Python's Core Principals helps everyone. Load up a Python interpreter and run `import this`.

Thank you for contributing to Indigo's codebase!

### Method Returns
```
# Do this:
return (A, B, C)  # explicit tuple

# Instead of this:
return A, B, C  # implicit tuple
```

### String Construction
Use f-strings whenever possible (feel free to update existing ones also if you want, but new ones should definitely be f-strings).

### Use Type Hints
Add python type hints, especially to the method/function definition (skip self). You should even consider type-hinting things that appear obvious, because it can help to type check the entire project if your IDE supports it:
```
def selectObject(self, valuesDict: indigo.Dict, typeId: str = "", devId: int = None) -> indigo.Dict:
    my_var: str = ""
    my_val: float = 123.4
```

### Add Method Descriptions
Use full Google-style docstrings, for instance:
```
def calculate_average(numbers: list) -> float:
    """Calculates the arithmetic mean of a list of numbers.

    Args:
        numbers (list[float]): A list of numeric values. The list must not be empty.

    Returns:
        float: The arithmetic mean of the provided numbers.

    Raises:
        ValueError: If `numbers` is empty.

    Example:
        >>> calculate_average([1.0, 2.0, 3.0])
        2.0
    """
```
You may find Sphinx-style docstrings in our codebase. We are switching those to Google-style over time.

### Use Descriptive Variable Names
It's best to use names that clearly show their purpose where possible.

```
# Do this:
num_devices = 1

# Instead of this:
d = 1
```
