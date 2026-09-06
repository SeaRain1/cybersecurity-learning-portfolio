# Pasting into the Desktop

## Concepts Learned

While completing this challenge, I strengthened my understanding of how Bash interprets input and how Linux programs exchange data through standard input and standard output. 

## Text Entered at the Bash Prompt

Bash normally interprets text entered at its prompt as a command. For example:

hello

Bash attempts to locate and execute a program named `hello`. If that program does not exist, Bash returns a `command not found` error.

To display text, it can instead be provided to a command such as `echo`:

echo "Hello, Linux"

## Standard Input and Standard Output

Linux programs commonly work with two data streams:

- Standard input (`stdin`) supplies data to a program.

- Standard output (`stdout`) contains the data produced by a program.

By default, standard input usually comes from the keyboard, while standard output appears in the terminal. Pipes and redirection allow these defaults to be changed.

## Pipes

The pipe operator (`|`) sends the standard output of one command to the standard input of another command.

printf "apple\nbanana\norange\n" | grep "banana"

Here, `printf` produces three lines of output. The pipe sends those lines to `grep`, which displays the matching line:

banana

A pipe transfers data directly between commands without requiring an intermediate file.

## Output Redirection

The `>` operator sends standard output into a file instead of displaying it in the terminal.

```bash

echo "Linux practice notes" > notes.txt

```

This creates `notes.txt`, or overwrites it if it already exists.

The `>>` operator appends output without replacing the existing contents:

```bash

echo "Practiced input and output redirection" >> notes.txt

```

## Input Redirection

The `<` operator makes a program receive standard input from a file instead of the keyboard.

```bash

wc -w < notes.txt

```

In this example, `wc` reads the contents of `notes.txt` and reports the number of words.

## Key Takeaway

Pipes transfer data directly between programs, while redirection changes whether a program reads from or writes to a file:

- `command1 | command2` transfers output between commands.

- `command > file` writes output to a file.

- `command >> file` appends output to a file.

- `command < file` supplies file contents as input.
