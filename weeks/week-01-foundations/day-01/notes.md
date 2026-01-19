# Day one metadata

Week: 01 - foundation 
Day: 01
Focus: Shell fundamentals, execution model
Time Budget: 45mins
Shell: Bash
Env: Local shell


## Concept
Bash is a shell that can be scripted.

## Why Bash exists
Historically and architecturally, Bash exists to solve one problem:
> Provide a user-level interface to start, connect, and control programs

Bash did not originate to:
- Build applications
- Perform heavy computation
- Replace C or Python
It exists to **ochestrate**

## Shell Vs Program Vs Language

Shell
- A command interpreter
- Reads test
- Expands it
- Starts programs
- Connect input/output
- Returns exit status

Program
- A compiled or interpreted executable
- Lives on disk
- Runs in a process
- Has no idea bash exits

Language
- Has data structures
- Has predictable evaluation rules
- Owns execution

> Bash sits between the user and the kernel, not between logic and memory.

## What Bash actually does when you type a command
When you type:
```bash
ls
```

Bash does not:
- "Run `ls` magically"
- "Understand directories"

Bash does this instead, in order:
1. Reads the line as text
2. Parses it into tokens
3. Expands variables, globs, subtitutions
4. Searches for executable name `ls`
5. Calls the kernel to execute it
6. Waits for it to finish
7. Captures the exit code

Thats it. <br>
Everything else is illusion

## What Bash does not do
Bash does not:
- Know the filesystems are
- Know what a process actually does
- Know what memory is
- Validate command correctness
If a command fails, Bash usually just reports the exit code

This is why defensive scripting exists.
