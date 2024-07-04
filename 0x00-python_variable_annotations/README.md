
# 0x00. Python - Variable Annotations

## Overview
This project focuses on understanding and using type annotations in Python 3. By the end of the project, you should be able to explain type annotations, specify function signatures and variable types, understand duck typing, and validate your code using mypy.

## Concepts
- Advanced Python

## Resources
- [Python 3 typing documentation](https://docs.python.org/3/library/typing.html)
- [MyPy cheat sheet](https://mypy.readthedocs.io/en/stable/cheat_sheet_py3.html)

## Learning Objectives
By the end of this project, you should be able to:
- Understand type annotations in Python 3.
- Use type annotations to specify function signatures and variable types.
- Understand and apply duck typing.
- Validate your code with mypy.

## Requirements
- **Editors:** `vi`, `vim`, `emacs`
- **Interpreted/compiled:** Ubuntu 18.04 LTS using python3 (version 3.7)
- **File format:** All files should end with a new line.
- **Shebang:** The first line of all files should be exactly `#!/usr/bin/env python3`
- **Documentation:** 
  - All modules, classes, and functions must have a proper docstring.
- **Code style:** Follow `pycodestyle` (version 2.5.0)
- **File executability:** All files must be executable.
- **File length:** The length of your files will be tested using `wc`.

## Tasks

### 0. Basic annotations - add
Write a type-annotated function `add` that takes two floats `a` and `b` as arguments and returns their sum as a float.

**File:** `0-add.py`
```python
def add(a: float, b: float) -> float:
    return a + b
```

### 1. Basic annotations - concat
Write a type-annotated function `concat` that takes two strings `str1` and `str2` as arguments and returns a concatenated string.

**File:** `1-concat.py`
```python
def concat(str1: str, str2: str) -> str:
    return str1 + str2
```

### 2. Basic annotations - floor
Write a type-annotated function `floor` which takes a float `n` as an argument and returns the floor of the float.

**File:** `2-floor.py`
```python
import math

def floor(n: float) -> int:
    return math.floor(n)
```

### 3. Basic annotations - to string
Write a type-annotated function `to_str` that takes a float `n` as an argument and returns the string representation of the float.

**File:** `3-to_str.py`
```python
def to_str(n: float) -> str:
    return str(n)
```

### 4. Define variables
Define and annotate the following variables with the specified values:
- `a`: an integer with a value of 1
- `pi`: a float with a value of 3.14
- `i_understand_annotations`: a boolean with a value of True
- `school`: a string with a value of “Holberton”

**File:** `4-define_variables.py`
```python
a: int = 1
pi: float = 3.14
i_understand_annotations: bool = True
school: str = "Holberton"
```

### 5. Complex types - list of floats
Write a type-annotated function `sum_list` which takes a list `input_list` of floats as an argument and returns their sum as a float.

**File:** `5-sum_list.py`
```python
from typing import List

def sum_list(input_list: List[float]) -> float:
    return sum(input_list)
```

### 6. Complex types - mixed list
Write a type-annotated function `sum_mixed_list` which takes a list `mxd_lst` of integers and floats and returns their sum as a float.

**File:** `6-sum_mixed_list.py`
```python
from typing import List, Union

def sum_mixed_list(mxd_lst: List[Union[int, float]]) -> float:
    return sum(mxd_lst)
```

### 7. Complex types - string and int/float to tuple
Write a type-annotated function `to_kv` that takes a string `k` and an int or float `v` as arguments and returns a tuple. The first element of the tuple is the string `k`. The second element is the square of the int/float `v` and should be annotated as a float.

**File:** `7-to_kv.py`
```python
from typing import Union, Tuple

def to_kv(k: str, v: Union[int, float]) -> Tuple[str, float]:
    return (k, float(v**2))
```

### 8. Complex types - functions
Write a type-annotated function `make_multiplier` that takes a float `multiplier` as an argument and returns a function that multiplies a float by `multiplier`.

**File:** `8-make_multiplier.py`
```python
from typing import Callable

def make_multiplier(multiplier: float) -> Callable[[float], float]:
    def multiply(n: float) -> float:
        return n * multiplier
    return multiply
```

### 9. Let's duck type an iterable object
Annotate the function `element_length`'s parameters and return values with the appropriate types.

**File:** `9-element_length.py`
```python
from typing import Iterable, Sequence, List, Tuple

def element_length(lst: Iterable[Sequence]) -> List[Tuple[Sequence, int]]:
    return [(i, len(i)) for i in lst]
```