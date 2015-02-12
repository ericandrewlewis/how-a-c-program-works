# how-a-c-program-works

`program.c` is a Hello World program in C.

To compile a c program, you would use the GNU C Compiler to produce an executable
by running `gcc program.c -o program`. Then, you can run the program from the command
line via `./program`.

Let's take the scenic route.

Run `gcc -E program.c > program.i`. This will run C preprocessor against the source.
The preprocessor injects the source of `stdio.h` into the file. Since we're using `printf()` inside `main()` function, `printf()` is included in `stdio.h`.

Run `gcc -S program.i`. This is translates preprocessed C source code into
assembly code in `program.s`.

### Open questions

What does executable code look like? How does writing echo "hello"; on the command
line invoke an executable and return the response?