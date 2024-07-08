# 0x01. Python - Async

## Overview
This project explores asynchronous programming in Python, focusing on the `async` and `await` syntax. By the end of this project, you should understand how to execute asynchronous programs using `asyncio`, run concurrent coroutines, create asyncio tasks, and utilize the random module for generating delays.

## Learning Objectives
By completing this project, you will be able to:
- Understand and use `async` and `await` syntax.
- Execute an async program with `asyncio`.
- Run concurrent coroutines.
- Create and manage asyncio tasks.
- Utilize the `random` module in asynchronous contexts.

## Resources
To help you understand these concepts, read or watch:
- [Async IO in Python: A Complete Walkthrough](https://realpython.com/async-io-python/)
- [asyncio - Asynchronous I/O](https://docs.python.org/3/library/asyncio.html)
- [random.uniform](https://docs.python.org/3/library/random.html#random.uniform)

## Requirements
- A `README.md` file at the root of the project folder is mandatory.
- Allowed editors: `vi`, `vim`, `emacs`.
- All files will be interpreted/compiled on Ubuntu 18.04 LTS using Python 3.7.
- All files should end with a new line.
- All files must be executable.
- The length of your files will be tested using `wc`.
- The first line of all your files should be exactly `#!/usr/bin/env python3`.
- Code should follow `pycodestyle` style (version 2.5.x).
- All functions and coroutines must be type-annotated.
- All modules should have documentation.
- All functions should have documentation explaining the purpose of the module, class, or method.

## Tasks

### 0. The Basics of Async
Write an asynchronous coroutine `wait_random` that takes an integer argument (`max_delay`, default value 10) and waits for a random delay between 0 and `max_delay` seconds before returning it.
```sh
# Example
$ ./0-main.py
9.034261504534394
1.6216525464615306
10.634589756751769
```
- **File:** `0-basic_async_syntax.py`

### 1. Execute Multiple Coroutines with Async
Write an async routine `wait_n` that takes in two integers: `n` and `max_delay`. Spawn `wait_random` n times with the specified `max_delay` and return the list of all delays in ascending order without using `sort()`.
```sh
# Example
$ ./1-main.py
[0.9693881173832269, 1.0264573845731002, 1.7992690129519855, 3.641373003434587, 4.500011569340617]
```
- **File:** `1-concurrent_coroutines.py`

### 2. Measure the Runtime
Create a `measure_time` function with integers `n` and `max_delay` as arguments that measures the total execution time for `wait_n(n, max_delay)` and returns `total_time / n`.
```sh
# Example
$ ./2-main.py
1.759705400466919
```
- **File:** `2-measure_runtime.py`

### 3. Tasks
Write a function `task_wait_random` that takes an integer `max_delay` and returns an `asyncio.Task`.
```sh
# Example
$ ./3-main.py
<class '_asyncio.Task'>
```
- **File:** `3-tasks.py`

### 4. Task-Waiting
Modify `wait_n` into a new function `task_wait_n` using `task_wait_random`.
```sh
# Example
$ ./4-main.py
[0.2261658205652346, 1.1942770588220557, 1.8410422186086628, 2.1457353803430523, 4.002505454641153]
```
- **File:** `4-tasks.py`
