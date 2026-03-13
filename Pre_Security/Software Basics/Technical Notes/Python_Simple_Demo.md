# Python: Simple Demo - TryHackMe

## 1. Variables

In programming, **variables** are used to store data that a program can read and modify during execution. They allow programs to keep track of information such as numbers, user input, and program state.

Example Python:

`<variable name> = <something>`

## 2. Conditional Statements

Conditional statements allow a program to **make decisions based on conditions**. In Python, the `if`, `elif`, and `else` statements are used to check different situations and execute specific code depending on the result.

Example Python:

```python
a = 1
b = 2

if a < b:
    print("a < b")
elif a > b:
    print("a > b")
else:
    print("a = b")

```
## 3. Iterations

Iterations, also known as **loops**, allow a program to repeat a set of instructions multiple times. They are used when a task needs to be performed repeatedly until a specific condition is met.
In programming, loops help automate repetitive actions, such as processing data, checking user input, or repeating a task until the correct result is achieved.

Example Python:

### while loop
A **while loop** repeats a block of code **as long as a condition remains true**. It is useful when the number of repetitions is not known beforehand.

Example:

```python
tries = 0

while tries < 3:
    print("Trying again...")
    tries = tries + 1
```

### for loop
A **for loop** is used when we want to iterate over a sequence such as a list, string, or range of numbers.

Example:

```python
for i in range(5):
    print("Iteration number:")
```