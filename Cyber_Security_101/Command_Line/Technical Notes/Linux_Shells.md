# Linux Shells - TryHackMe

## 1. Types of Linux Shells

Like the Command Prompt and PowerShell in Windows OS, Linux has different types of shells available, each with its own features and characteristics.

Multiple shells are installed in different Linux distributions. To see which shell you are using, type the following command: `echo $SHELL`.

#### `cat /etc/shells`: to list down the available shells in your Linux OS.

#### `zsh`: To switch between these shells.

#### `chsh -s /usr/bin/zsh`:  to permanently change your default shell.

### Shells:

**Bourne Again Shell (Bash)** is the default shell for most Linux distributions. When you open the terminal, bash is present for you to enter commands. Before bash, some shells like sh, ksh, and csh had different capabilities. Bash came as an enhanced replacement for these shells, borrowing capabilities from all of them. This means that it has many of the features of these old shells and some of its unique abilities. Some of the key features provided by bash are listed below:

- Bash is a widely used shell with scripting capabilities.
- It offers a tab completion feature, which means if you are in the middle of completing a command, you can press the tab key on your keyboard. It will automatically complete the command based on a possible match or give you multiple suggestions for completing it.
- Bash keeps a history file and logs all of your commands. You can use the up and down arrow keys to use the previous commands without typing them again. You can also type history to display all your previous commands.
- Friendly Interactive Shell

**Friendly Interactive Shell (Fish)** is also not default in most Linux distributions. As its name suggests, it focuses more on user-friendliness than other shells. Some of the key features provided by fish are listed below:

- It offers a very simple syntax, which is feasible for beginner users.
- Unlike bash, it has auto spell correction for the commands you write.
- You can customize the command prompt with some cool themes using fish.
- The syntax highlighting feature of fish colors different parts of a command based on their roles, which can improve the readability of commands. It also helps us to spot errors with their unique colors.
- Fish also provides scripting, tab completion, and command history functionality like the shells mentioned in this task.

**Z Shell (Zsh)** is not installed by default in most Linux distributions. It is considered a modern shell that combines the functionalities of some previous shells. Some of the key features provided by zsh are listed below:

Zsh provides advanced tab completion and is also capable of writing scripts.
Just like fish, it also provides auto spell correction for the commands.
It offers extensive customization that may make it slower than other shells.
It also provides tab completion, command history functionality, and several other features.

## 2. Shell Scripting and Components

A shell script is nothing but a set of commands.

Unlike the other commands we type in the shell, we first need to create a file using any text editor for the script.

Every script should start from shebang. Shebang is a combination of some characters that are added at the beginning of a script, starting with #! followed by the name of the interpreter to use while executing the script. Example: `#!/bin/bash`

To execute the script, we first need to make sure that the script has execution permissions. To give these permissions to the script, we can type the following command in our terminal: `chmod +x scriptName.sh`

To run script use `./scriptName.sh`

### Variables

`read` is used to take input from the user. Example: `read name` (`name` name of variable)

### Loops

Loop, as the name suggests, is something that is repeating.

```Bash
for i in {1..10};
do
echo $i
done
```

### Conditional Statements

```Bash

#!/bin/bash
echo "Please enter your name first:"
read name
if [ "$name" = "Stewart" ]; then
        echo "Welcome Stewart! Here is the secret: THM_Script"
else
        echo "Sorry! You are not authorized to access the secret."
fi
```

### Comments

```Bash
# TEXT
```

