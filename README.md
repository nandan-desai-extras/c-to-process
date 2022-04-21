# C to Process

In this study module, you'll be learning some very fundamental concepts related to how a simple C program becomes a Process in the Operating System.

The primary focus of this study module will be on the Windows operating system but there will be some comparisons with Linux to understand certain concepts.

## Author

All the notes written and diagrams in this study module are created by [Nandan Desai](https://github.com/NandanDesai)

## Prerequisites

- Knowledge of Physical and Virtual Memory: https://nkdesai409.blogspot.com/2022/02/understanding-computer-memory.html (my blogpost)
- If you've written any simple C program before, you're good to go! You'll learn the internals of it here.

## Learning outcomes

- You'll learn all the stages of compilation and linking in detail.
- You'll learn about what an object file is, and what's inside it (like Sections, Symbol Table and Relocation Table).
- You'll learn about Static and Dynamic Libraries.
- You'll be able to understand the internals of the PE (Portable Executable) file format.
- You'll understand various data structures (or rather, "data directories") in a PE file like Import Table, Export Table, Base Relocation Table etc.
- You'll learn how a Loader works and how DLLs are loaded.
- You'll understand the memory structure of a process's virtual address space.
- Overall, you'll have a pretty clear understanding of how a C program that you write in a text file turns into a process in the operating system!


## Index

 - 1. Introduction
	- 1.1. C Standard Library
	- 1.2. Setting up the C development environment
		- 1.1.1. C development environment setup for Windows
	- 1.3. Eagle's Eye view of the compilation process
- 2. Compilation Stages
	- 2.1. Stage 1: Preprocessing
	- 2.2. Stage 2: Compilation
	- 2.3. Stage 3: Assembly
		- 2.3.1. Anatomy of an object file
			- 2.3.1.1 Sections
			- 2.3.1.2 Symbol Table
	- 2.4. Stage 4: Linking - Part 1
		- 2.4.1. Static Libraries
			- 2.4.1.1. Picking a suitable library for Linking
	- 2.5. Stage 4: Linking - Part 2
		- 2.5.1. The Linker's Flow
			- 2.5.1.1. Part 1 - Searching the Libraries
			- 2.5.1.2. Part 2 - Linker visits the DLL file
				-  2.5.1.2.1. The Export Tables of DLL
			- 2.5.1.3. Part 3 - Linker starts creating the EXE file
				- 2.5.1.3.1. The Import Tables of EXE
				- 2.5.1.3.2. Linker starts copying object file Sections into exe
					- COFF Relocation Table
					- Base Relocation Table
- 3. Process Creation
	- 3.1. The Loader Flow
		- 3.1.1. Loading the DLLs
			- 3.1.1.1. Step 1: Reading the Import Table of the exe
			- 3.1.1.2. Step 2: Reading the Export Table of the DLL
			- 3.1.1.3. Step 3: Adding entries into the Import Address Table (IAT)
		- 3.1.2. Loading the Sections of exe into memory

## License

![CC BY-NC-SA license](https://mirrors.creativecommons.org/presskit/buttons/88x31/png/by-nc-sa.png)

This entire GitHub repository is published under [Creative Commons BY-NC-SA 4.0 license](https://creativecommons.org/licenses/by-nc-sa/4.0/). "This license lets others remix, tweak, and build upon your work non-commercially, as long as they credit you and license their new creations under the identical terms."


