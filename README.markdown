brainfuck
===========
Brainfuck interpreter written in C.

## Usage
    brainfuck [-ch] <filenames>
	-e  run code directly
	-h  show a help message.

The interactive console can be accessed by passing no arguments.    

We also provide a C api:

``` c
#include <stdio.h>
#include <brainfuck.h>
    
int main() {
	BrainfuckState *state = brainfuck_state();
	BrainfuckExecutionContext *context = brainfuck_context(BRAINFUCK_TAPE_SIZE);
	BrainfuckInstruction *instruction = brainfuck_parse_string("+++++.");
 	brainfuck_add(state, instruction);
 	brainfuck_execute(state->root, context);
	brainfuck_destroy_context(context);
 	brainfuck_destroy_state(state);
	return EXIT_SUCCESS;
}
```

## Getting the source
Download the source code by running the following code in your command prompt:
```sh
$ git clone https://github.com/FabianM/brainfuck.git
```
or simply [grab](https://github.com/FabianM/brainfuck/archive/master.zip) a copy of the source code as a Zip file.

## Building
Create the build directory.
```sh
$ mkdir build
$ cd build
```
Brainfuck requires CMake and a C compiler (e.g. Clang or GCC) in order to run.
Then, simply create the Makefiles:
```sh
$ cmake ..
```
and finally, build it using the building system you chose (e.g. Make):
```sh
$ make
```

## License
See LICENSE file.

## Contributors
    Fabian M. https://www.github.com/FabianM  mail.fabianm@gmail.com
    aliclubb https://www.github.com/aliclubb
	diekmann https://www.github.com/diekmann
