### Coding and Style Guide for Open Source Plugins
The purpose of this document is to lay out coding and style guidance for contributors to use when developing and revising Indigo's codebase. Adhering to these styles 
helps to keep Indigo's codebae uniform across the framework and help other contributors and reviewers to more easily understand your code. There are a few fundamental 
points that submissions should include:

1. Keep code to manageable chunks -- collapsing too much code and logic into a single file makes it much harder to manage going forward.
2. Explicit is better than implicit -- where possible, make it obvious what your code does.
3. Document your code -- including comments that explain the purpose of your code if the intent is not obvious to a cold reader.
4. Be Pythonic -- adherence to Python's Core Principals helps everyone. Load up a Python interpreter and run `import this`.

Thank you for contributing to Indigo's codebase!

#### Method Returns
Instead of this:
```
return A, B, C  # implicit tuple
```
do this:
```
return (A, B, C)  # explicit tuple
```

#### String Construction
New string construction should use f-strings whenever possible (feel free to update existing ones also if you want, but new ones should definitely be f-strings).

#### Use Type Hints
Add python type hints, especially to the method/function definition (skip self):
```
def selectObject(self, valuesDict: indigo.Dict, typeId: str = "", devId: int = None) -> indigo.Dict:
```

#### Use Full Sphinx-style Docstrings
Add method descriptions, for instance:
```
def addProperty(self, valuesDict, typeId="", devId=None): # noqa
        """ Add a property to the selected object
        
        :param valuesDict: this is the Indigo dictionary containing the configured values
        :param typeId: unused
        :param devId: unused
        :return: an updated valuesDict and potentially an errorsDict with any errors
        """
```
Note that type hints are left out of this example for clarity.
