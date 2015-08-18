# How a C program works

`program.c` is a Hello World program in C.

## Compiling source

The source code of a C program cannot be run by itself. It must be compiled to machine code to be run by the computer's processor.

The compilation process looks like this:

source > preprocessed source > assembly code > executable binary file

### Compile source to a binary executable (i.e. machine code)

A C program can be compiled from source to executable binary file in one command.

```bash
gcc program.c -o program
```

Then run the program from the command line via `./program`.

### Compile source to preprocessed source

The preprocessor injects all included files into one file. We're using `printf()` in the program, and `printf()` is included in `stdio.h` (the standard input/output library). So the preprocessor will inject the source of `stdio.h`.

Run C preprocessor against the source.

```bash
gcc -E program.c > program.i
```

### Compile source to assembly code

This is translates preprocessed C source code into assembly code in `program.s`.

```bash
gcc -E program.c > program.i && gcc -S program.i
```

Since we're using `gcc`, this will output x86 assembly in GAS syntax.

### Open questions

What does executable code look like? How does writing echo "hello"; on the command
line invoke an executable and return the response?