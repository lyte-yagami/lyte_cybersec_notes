# Missing Semester – Introduction to the Shell

> [!info] Lecture
> **Course:** The Missing Semester of Your CS Education  
> **Lecture:** Course Overview + Introduction to the Shell  
> **Main goal:** Learn how to properly use the tools already available on your computer and combine them to work faster.

---

# 1. Why this course?

In computer science, we learn things like:

- Operating Systems
- Networking
- Algorithms
- Databases
- Programming

But we often don't learn **how to properly use our computer and development tools**.

For example, many people:

- know some commands but don't know what they actually do
- copy commands from the internet without understanding them
- repeat boring tasks manually
- don't know that tools already exist to automate those tasks

## Main idea

Computers are good at doing repetitive tasks.

But sometimes we forget that **we can also use the computer to automate the way we use the computer itself**.

> **explanation:**  Instead of repeatedly clicking 10 buttons every day, we can sometimes write one command that does all 10 things.

This course teaches tools that help us:

- work faster
- automate repetitive tasks
- understand our system better
- combine small tools to solve bigger problems
- become less dependent on GUIs

---

# 2. What is a Shell?

A **shell** is a program that lets us interact with the computer using commands.

Example:

```bash
date
```

You type a command → the shell understands it → the shell runs the program → you get the output.

```text
You
 ↓
Type command
 ↓
Shell
 ↓
Runs program
 ↓
Program output
```
![[Pasted image 20260915200843.png]]


## Simple definition

> **Shell = a command interpreter that lets you run programs using text commands.**

---

# 3. Terminal vs Shell

These are **not the same thing**.

### Terminal

The **terminal** is the application/window where you type commands.

### Shell

The **shell** is the program inside the terminal that reads and interprets your commands.

Think of it like:

```text
Terminal = The room
Shell    = The person inside the room listening to your commands
```

Or:

```text
Terminal → provides the interface
Shell    → processes the commands
```

For example, a setup can be:

```text
Terminal emulator: Kitty
Shell: Zsh
```


---

# 4. Different types of shells

Some common shells are:

- `bash`
- `zsh`
- `fish`
- `sh`
- PowerShell

The lecture mainly uses **Bash** because it is very common.

But many concepts also work in Zsh.

For example:

```bash
cd ~
ls
echo hello
```

will work similarly in both Bash and Zsh.

> **Important:** The exact syntax of every feature may not be identical between shells.

---

# 5. Opening a shell

On Linux, you usually open a terminal emulator.

Examples:

```text
Kitty
Alacritty
GNOME Terminal
Konsole
Foot
```

Inside it, you get a prompt.

Example:

```text
missing:~$
```

A prompt might look like:

```text
lyte@kali ~
%
```
![[Pasted image 20260915201013.png]]



---

# 6. Understanding the prompt

A prompt gives information about where and who you are.

Example:

```text
lyte@kali ~/Documents
```

Breakdown:

```text
lyte       → username
@          → separator
kali       → computer/hostname
~/Documents → current location
```

The prompt basically tells you:

> "You are Lyte, on the computer called kali, currently inside this directory."

---

# 7. Current Working Directory

Every shell has a **current working directory**.

This is basically:

> **The folder where you are currently standing.**

For example:

```text
~/Documents/obsidian
```

If you run:

```bash
ls
```

the shell lists files inside your **current working directory**.

---

# 8. `pwd`

```bash
pwd
```

**Meaning:** Print Working Directory.

It shows exactly where you currently are.

Example:

```bash
lyte@kali ~
% pwd
/home/lyte
```

So:

> `pwd` = **"Where am I?"**

---

# 9. `cd`

```bash
cd
```

**Meaning:** Change Directory.

It lets you move between folders.

Example:

```bash
cd Documents
```

Now you move into:

```text
~/Documents
```

---

## `cd ..`

```bash
cd ..
```

`..` means:

> **Parent directory / one folder above.**

Example:

```text
/home/lyte/Documents
```

Running:

```bash
cd ..
```

takes you to:

```text
/home/lyte
```

> `..` = **"Go one directory up."**

---

## `cd .`

```bash
cd .
```

`.` means:

> **The current directory.**

So:

```bash
cd .
```

basically means:

> "Go to the folder I'm already in."

Usually not useful by itself, but `.` becomes useful in paths and scripts.

---

# 10. `~`

```bash
~
```

The tilde represents your **home directory**.

For example:

```text
~
```

could mean:

```text
/home/lyte
```

So:

```bash
cd ~
```

means:

> **Go to my home directory.**

Example:

```bash
cd ~/Documents
```

means:

```text
/home/lyte/Documents
```

> **Baby explanation:** `~` is a shortcut for your home folder.

---

# 11. Absolute vs Relative Paths

There are two common ways to describe a location.

## Absolute path

An absolute path gives the **complete location**.

Example:

```text
/home/lyte/Documents/obsidian
```

It starts from the root directory:

```text
/
```

Example:

```bash
cd /home/lyte/Documents
```

No matter where you currently are, this points to the same location.

> **Absolute path = full address of a location.**

---

## Relative path

A relative path depends on where you currently are.

Suppose:

```text
Current location:
/home/lyte
```

Then:

```bash
cd Documents
```

works.

But if you are somewhere else:

```text
/home/lyte/Downloads
```

then:

```bash
cd Documents
```

may not work because the path is being interpreted relative to your current directory.

> **Relative path = directions based on where you currently are.**

---

# 12. The Linux Filesystem

Linux starts from one main directory:

```text
/
```

This is called the **root directory**.

Example structure:

```text
/
├── home
│   └── lyte
├── etc
├── usr
├── bin
├── tmp
└── var
```

Your home directory is usually:

```text
/home/username
```

For example:

```text
/home/lyte
```

---

# 13. `ls`

```bash
ls
```

**Meaning:** List files.

It shows the contents of the current directory.

Example:

```bash
ls
```

Output:

```text
Documents
Downloads
Pictures
```

You can also specify a directory:

```bash
ls /home/lyte/Documents
```

> `ls` = **"Show me what's inside this folder."**

---

# 14. Commands and Arguments

Commands can receive **arguments**.

Example:

```bash
echo hello
```

Here:

```text
echo  → command
hello → argument
```

Another example:

```bash
cd Documents
```

```text
cd        → command
Documents → argument
```

> **Baby explanation:** The command tells the computer what to do; the argument gives the command extra information about what to do it to.

---

# 15. `echo`

```bash
echo hello
```

Output:

```text
hello
```

`echo` prints something.

Example:

```bash
echo "Hello Lyte"
```

Output:

```text
Hello Lyte
```

> **Baby explanation:** `echo` basically repeats whatever you give it.

---

# 16. `date`

```bash
date
```

Shows the current system date and time.

> `date` = **"Tell me the current date and time."**

---

# 17. How does the shell find commands?

When you type:

```bash
echo hello
```

how does the shell know where `echo` is?

The answer is:

```bash
$PATH
```

---

# 18. `$PATH`

`$PATH` is an **environment variable**.

It contains a list of directories where the shell looks for executable programs.

Check it:

```bash
echo $PATH
```

You might see:

```text
/usr/local/bin:/usr/bin:/bin
```

The `:` separates the directories.

When you type:

```bash
echo
```

the shell searches the directories in `$PATH` until it finds an executable with that name.

Conceptually:

```text
/usr/local/bin/echo
/usr/bin/echo
/bin/echo
```

> **Baby explanation:** `$PATH` is basically the shell's list of places to search when you type a command.

---

# 19. `which`

```bash
which echo
```

Possible output:

```text
/bin/echo
```

This tells you which executable is found for that command.

Example:

```bash
which python
```

> `which` = **"Which executable will run when I type this command?"**

---

# 20. Running a program using its full path

Instead of:

```bash
echo hello
```

you can directly run:

```bash
/bin/echo hello
```

Both can produce:

```text
hello
```

The difference is:

```bash
echo
```

→ shell searches `$PATH`

while:

```bash
/bin/echo
```

→ you directly specify the program.

---

# 21. The Power of the Shell

The shell is not just about running commands one by one.

Its real power comes from:

> **Taking small programs and connecting them together.**

Conceptually:

```text
Program A
   ↓
Program B
   ↓
Program C
   ↓
Final result
```

This is done using:

```text
|
```

called a **pipe**.

---

# 22. Pipes `|`

Example:

```bash
ls | sort
```

The `|` symbol sends the output of one command into another command.

Conceptually:

```text
ls
 ↓
output
 ↓
sort
 ↓
sorted output
```

So:

```bash
ls | sort
```

means:

> **List the files, then send that list to `sort`.**

> **Baby explanation:** A pipe connects the output of one program to the input of another program.

---

# 23. Standard Input, Output and Error

Programs usually have three important streams:

```text
stdin
stdout
stderr
```

## stdin

**Standard Input**

Where a program receives input.

Normally this can be your keyboard.

> `stdin` = **"Where the program gets input from."**

---

## stdout

**Standard Output**

The normal output produced by a program.

Usually this is displayed in your terminal.

> `stdout` = **"Normal output from the program."**

---

## stderr

**Standard Error**

Where error messages are sent.

```text
stdout → normal result
stderr → error messages
```

> **Baby explanation:** Normal results and error messages are separate streams.

---

# 24. Redirection

Normally:

```bash
echo hello
```

prints to the terminal.

But we can redirect that output somewhere else.

---

## `>`

Example:

```bash
echo hello > hello.txt
```

This writes:

```text
hello
```

into:

```text
hello.txt
```

instead of displaying it in the terminal.

> `>` = **"Send the output into this file."**

### Important

If the file already exists, `>` **overwrites** its contents.

Example:

```bash
echo first > file.txt
echo second > file.txt
```

The file will contain:

```text
second
```

---

## `>>`

```bash
echo hello >> file.txt
```

This **appends** the output instead of overwriting the existing contents.

Example:

```bash
echo first > file.txt
echo second >> file.txt
```

Result:

```text
first
second
```

> `>>` = **"Add this output to the end of the file."**

---

# 25. `cat`

```bash
cat file.txt
```

Displays the contents of a file.

Example:

```bash
cat hello.txt
```

Output:

```text
hello
```

> `cat` = **"Show me what's inside this file."**

---

# 26. Combining Commands

The interesting part is combining commands.

Example:

```bash
cat file.txt | sort
```

Conceptually:

```text
file.txt
   ↓
cat reads it
   ↓
sort receives it
   ↓
sorted output
```

This represents an important Unix philosophy:

> **Small tools that do one thing well can be combined to do bigger things.**

---

# 27. Shell as a Programming Language

A shell is not just a command launcher.

Shells such as Bash and Zsh are also programming languages.

They support:

- variables
- conditions
- loops
- functions
- scripts

So you can move from simple commands:

```bash
ls
```

to complete shell programs.

---

# 28. Why the Shell Matters

Knowing the shell helps with:

- Linux administration
- Cybersecurity
- Open-source software
- Installing software
- Automation
- Debugging
- Servers
- SSH
- CTFs
- DevOps
- Scripting

For cybersecurity, the shell is especially useful because you often need to:

```text
search files
filter logs
connect through SSH
automate reconnaissance
process data
run tools
chain tools together
```

---

# 29. Example Mindset

Suppose you have a huge log file.

Instead of manually:

```text
Open file
↓
Search
↓
Copy results
↓
Sort manually
↓
Remove duplicates
```

you can combine tools:

```bash
grep something logfile | sort | uniq
```

Here:

```text
grep  → finds what you want
sort  → organizes the results
uniq  → removes adjacent duplicate lines
```

Each command does a small job.

Together they solve a bigger problem.

---

# 30. Important Takeaways

## Shell

> A shell is a program that interprets commands and lets you interact with the computer using text.

## Terminal

> A terminal is the application/interface used to access a shell.

## Current Working Directory

> The folder where you are currently operating.

## `pwd`

```bash
pwd
```

> **"Where am I?"**

## `ls`

```bash
ls
```

> **"What's inside this folder?"**

## `cd`

```bash
cd folder
```

> **"Move me into this folder."**

## `~`

```bash
~
```

> **Your home directory.**

## `..`

```bash
..
```

> **One directory above the current directory.**

## `.`

```bash
.
```

> **The current directory.**

## `$PATH`

> **The list of directories where the shell searches for executable commands.**

## `which`

```bash
which command
```

> **"Where is the executable that will run for this command?"**

## Pipe

```text
|
```

> **Take the output of one program and give it as input to another.**

## `>`

```bash
command > file
```

> **Write output to a file and overwrite existing contents.**

## `>>`

```bash
command >> file
```

> **Append output to the end of a file.**

## `stdin`

> **Input going into a program.**

## `stdout`

> **Normal output coming from a program.**

## `stderr`

> **Error output coming from a program.**

---

# 31. Mental Model

```text
I type a command
        ↓
The Shell reads it
        ↓
The Shell finds the program using $PATH
        ↓
The program runs
        ↓
stdout → normal output
stderr → errors
        ↓
I can:
├── see the output
├── save it using >
├── append it using >>
└── send it to another program using |
```

---

# 32. Practice Commands

Try these yourself instead of only reading them:

```bash
pwd
```

```bash
ls
```

```bash
cd ~
```

```bash
echo hello
```

```bash
date
```

```bash
echo $PATH
```

```bash
which echo
```

```bash
echo hello > test.txt
```

```bash
cat test.txt
```

```bash
ls | sort
```

---

# 33. What I Actually Need to Remember

I don't need to memorize hundreds of commands.

I need to understand:

1. **Where I am** → `pwd`
2. **What's here** → `ls`
3. **How to move** → `cd`
4. **How paths work** → `/`, `.`, `..`, `~`
5. **How commands are found** → `$PATH`
6. **How to find an executable** → `which`
7. **How programs communicate** → `|`
8. **How to save output** → `>`
9. **How to append output** → `>>`
10. **The difference between input, output and errors** → `stdin`, `stdout`, `stderr`
11. **How small commands can be combined to solve bigger problems**

---

# Key Unix Philosophy

> **Build small tools that do one thing well, then combine them together.**

This is one of the most important ideas behind working effectively in the shell.
