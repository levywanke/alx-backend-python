# 0x02. Python - Async Comprehension

## Overview
This project focuses on understanding and implementing asynchronous comprehensions and generators in Python. You will learn how to write asynchronous generators, use async comprehensions, and type-annotate generators.

## Resources
- [PEP 530 – Asynchronous Comprehensions](https://www.python.org/dev/peps/pep-0530/)
- [What’s New in Python: Asynchronous Comprehensions / Generators](https://docs.python.org/3/whatsnew/3.6.html#whatsnew36-pep530)
- [Type-hints for generators](https://docs.python.org/3/library/typing.html#typing.Generator)

## Learning Objectives
By the end of this project, you should be able to:
- Write an asynchronous generator.
- Use async comprehensions.
- Type-annotate generators.

## Requirements
- Allowed editors: `vi`, `vim`, `emacs`
- All files will be interpreted/compiled on Ubuntu 18.04 LTS using Python 3.7
- All files should end with a new line
- The first line of all your files should be exactly `#!/usr/bin/env python3`
- A `README.md` file at the root of the project folder is mandatory
- Your code should use the `pycodestyle` style (version 2.5.x)
- All modules should have documentation
- All functions and coroutines must be type-annotated

## Tasks

### 0. Async Generator
Write a coroutine called `async_generator` that takes no arguments. The coroutine will loop 10 times, each time asynchronously wait 1 second, then yield a random number between 0 and 10.

```python
# File: 0-async_generator.py

import asyncio
import random

async def async_generator():
    for _ in range(10):
        await asyncio.sleep(1)
        yield random.uniform(0, 10)
```

**Example:**
```python
# File: 0-main.py

import asyncio
async_generator = __import__('0-async_generator').async_generator

async def print_yielded_values():
    result = []
    async for i in async_generator():
        result.append(i)
    print(result)

asyncio.run(print_yielded_values())
```

### 1. Async Comprehensions
Import `async_generator` from the previous task and write a coroutine called `async_comprehension` that takes no arguments. The coroutine will collect 10 random numbers using an async comprehending over `async_generator`, then return the 10 random numbers.

```python
# File: 1-async_comprehension.py

import asyncio
async_generator = __import__('0-async_generator').async_generator

async def async_comprehension():
    return [i async for i in async_generator()]
```

**Example:**
```python
# File: 1-main.py

import asyncio
async_comprehension = __import__('1-async_comprehension').async_comprehension

async def main():
    print(await async_comprehension())

asyncio.run(main())
```

### 2. Run time for four parallel comprehensions
Import `async_comprehension` from the previous task and write a `measure_runtime` coroutine that will execute `async_comprehension` four times in parallel using `asyncio.gather`. `measure_runtime` should measure the total runtime and return it.

```python
# File: 2-measure_runtime.py

import asyncio
import time
async_comprehension = __import__('1-async_comprehension').async_comprehension

async def measure_runtime():
    start_time = time.time()
    await asyncio.gather(*(async_comprehension() for _ in range(4)))
    return time.time() - start_time
```

**Example:**
```python
# File: 2-main.py

import asyncio
measure_runtime = __import__('2-measure_runtime').measure_runtime

async def main():
    return await measure_runtime()

print(asyncio.run(main()))
```