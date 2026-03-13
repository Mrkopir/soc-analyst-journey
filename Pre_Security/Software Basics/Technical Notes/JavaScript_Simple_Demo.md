# JavaScript: Simple Demo - TryHackMe


## 1. Variables

In programming, **variables** are used to store data that a program can read and modify during execution. They allow the program to keep track of values such as numbers, user input, or application state.

In JavaScript, variables can be declared using **let**, **const**, or **var**.

Example:

```javascript
let secret = Math.floor(Math.random() * 20) + 1;
let tries = 0;
let guess = 0;
```

- `secret` stores the random number the user needs to guess.
- `tries` counts the number of attempts.
- `guess` stores the user's input.

## 2. Prompting the User for Input

Programs often need to interact with users. In JavaScript, user input can be requested using the **prompt()** function in browser environments.

Example:

```javascript
let text = prompt("Take a guess:");
let guess = Number(text);
```

- `prompt()` asks the user to enter a value.
- The result is returned as text, so it is converted to a number using `Number()`.

## 3. Conditional Statements

Conditional statements allow programs to **make decisions based on conditions**. JavaScript uses **if**, **else if**, and **else** statements to control program flow.

Example:

```javascript
if (guess < 1 || guess > 20) {
    console.log("That number is out of range. Try again.");
} else if (guess < secret) {
    console.log("Too low, try again.");
} else if (guess > secret) {
    console.log("Too high, try again.");
} else {
    console.log("You got it in " + tries + " tries!");
}
```

The program checks:

- if the guess is outside the allowed range
- if the guess is lower than the secret number
- if the guess is higher than the secret number
- if the guess is correct

## 4. Iterations

**Iterations (loops)** allow a program to repeat a block of code multiple times.

### while loop

A **while loop** repeats code while a condition is true.

```javascript
let tries = 0;

while (tries < 3) {
    console.log("Trying again...");
    tries = tries + 1;
}
```

### for loop

A **for loop** runs code a specific number of times.

```javascript
for (let i = 0; i < 5; i++) {
    console.log("Iteration number:", i);
}
```

Loops are useful for repeating actions such as validating input, processing data, or running a program until a condition is met.