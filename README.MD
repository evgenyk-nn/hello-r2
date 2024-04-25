# Compiling C Programs Manually Using Different Compilation Stages

This README.MD file provides instructions on manually compiling a C program using different compilation stages.

## Preprocessing

1. **`cpp hello.c > hello.i`**: Perform preprocessing of the source file **`hello.c`** using the C preprocessor, and save the result in an intermediate file **`hello.i`**.

## Compilation

2. **`gcc -S hello.i`**: Compile the intermediate file **`hello.i`** using the GCC compiler with the **`-S`** option, which generates an assembly file **`hello.s`**.

## Assembling

3. **`as -o hello.o hello.s`**: Assemble the assembly file **`hello.s`** using the assembler, creating an object file **`hello.o`**.

## Linking

4. **`ld -e hello -o hello hello.o -lc -I /lib64/ld-linux-x86-64.so.2`**: Link the object file **`hello.o`** using the linker. In this case, the **`-e`** flag is used to specify the entry point of the program as the **`hello`** function, and the standard input-output library **`-lc`** is added. The resulting executable file is named **`hello`**.

## Redefining Entry Point

In this example, the entry point of the program is redefined from the `main` function to the `hello` function. This was done using the linker, which used the `-e hello` flag to specify the new entry point.

## Running the Program

5. **`./hello`**: Run the executable file **`hello`**, which outputs "Hello".
