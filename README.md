# C to Process

In this study module, you'll be learning some very fundamental concepts related to how a simple C program becomes a Process in the Operating System.

The primary focus of this study module will be on the Windows operating system but there will be some comparisons with Linux to understand certain concepts.

## Author

All the notes are written and all the diagrams are created by [Nandan Desai](https://github.com/NandanDesai)

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

 - [1. Introduction](/1.md#1-introduction)
	- [1.1. C Standard Library](/1.md#11-c-standard-library)
	- [1.2. Setting up the C development environment](/1.md#12-setting-up-the-c-development-environment)
		- [1.1.1. C development environment setup for Windows](/1.md#111-c-development-environment-setup-for-windows)
	- [1.3. Eagle's Eye view of the compilation process](/1.md#13-eagles-eye-view-of-the-compilation-process)
- [2. Compilation Stages](/2.md#2-compilation-stages)
	- [2.1. Stage 1: Preprocessing](/2.md#21-stage-1-preprocessing)
	- [2.2. Stage 2: Compilation](/2.md#22-stage-2-compilation)
	- [2.3. Stage 3: Assembly](/2.md#23-stage-3-assembly)
		- [2.3.1. Anatomy of an object file](/3.md#231-anatomy-of-an-object-file)
			- [2.3.1.1 Sections](/3.md#2311-sections)
			- [2.3.1.2 Symbol Table](/3.md#2312-symbol-table)
	- [2.4. Stage 4: Linking - Part 1](/4.md#24-stage-4-linking---part-1)
		- [2.4.1. Static Libraries](/4.md#241-static-libraries)
			- [2.4.1.1. Picking a suitable library for Linking](/4.md#2411-picking-a-suitable-library-for-linking)
	- [2.5. Stage 4: Linking - Part 2](/5.md#25-stage-4-linking---part-2)
		- [2.5.1. The Linker's Flow](/5.md#251-the-linkers-flow)
			- [2.5.1.1. Part 1 - Searching the Libraries](/5.md#2511-part-1---searching-the-libraries)
			- [2.5.1.2. Part 2 - Linker visits the DLL file](/5.md#2512-part-2---linker-visits-the-dll-file)
				-  [2.5.1.2.1. The Export Tables of DLL](/5.md#25121-the-export-tables-of-dll)
			- [2.5.1.3. Part 3 - Linker starts creating the EXE file](/5.md#2513-part-3---linker-starts-creating-the-exe-file)
				- [2.5.1.3.1. The Import Tables of EXE](/5.md#25131-the-import-tables-of-exe)
				- [2.5.1.3.2. Linker starts copying object file Sections into exe](/5.md#25132-linker-starts-copying-object-file-sections-into-exe)
					- [COFF Relocation Table](/5.md#coff-relocation-table)
					- [Base Relocation Table](/5.md#base-relocation-table)
- [3. Process Creation](/6.md#3-process-creation)
	- [3.1. The Loader Flow](/6.md#31-the-loader-flow)
		- [3.1.1. Loading the DLLs](/6.md#311-loading-the-dlls)
			- [3.1.1.1. Step 1: Reading the Import Table of the exe](/6.md#3111-step-1-reading-the-import-table-of-the-exe)
			- [3.1.1.2. Step 2: Reading the Export Table of the DLL](/6.md#3112-step-2-reading-the-export-table-of-the-dll)
			- [3.1.1.3. Step 3: Adding entries into the Import Address Table (IAT)](/6.md#3113-step-3-adding-entries-into-the-import-address-table-iat)
		- [3.1.2. Loading the Sections of exe into memory](/6.md#312-loading-the-sections-of-exe-into-memory)


## License

![CC BY-NC-SA license](https://mirrors.creativecommons.org/presskit/buttons/88x31/png/by-nc-sa.png)

This entire GitHub repository is published under [Creative Commons BY-NC-SA 4.0 license](https://creativecommons.org/licenses/by-nc-sa/4.0/). "This license lets others remix, tweak, and build upon your work non-commercially, as long as they credit you and license their new creations under the identical terms."


