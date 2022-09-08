# Monty
`monty` is an interpreter of Monty ByteCodes files, which is a scripting language just like Python.
## About the Monty languageThis is a language that contains specific instructions to manipulate data information (stacks or queues), where each instruction (*called opcode*) is sended per line. Files which contains Monty byte codes usually have the `.m` extension.
Example (`file.m`):```bash$ cat file.m# Pushing element to the stackpush 0push 1push 2# Printing all elementspallpush 3push 4pop# Rotating the stack to the bottomrotrpallrotl# Setting FIFOqueuepush 5# Setting LIFOstackpush 5$```
## Technologies* Interpreter was written with C language* C files are compiled using `gcc`* C files are written according to the betty coding standard* Tested on Ubuntu 20.04 LTS
## UsageTo compile all files:
```bash$ gcc -Wall -Werror -Wextra -pedantic *.c -o monty$```
The **synopsis** of the interpreter is the following:
```bash$ ./monty [filename]$```
To run the interpreter:
```bash$ ./monty file.m2100321$```
## Features### Opcodes`monty` executes the following opcodes:
| Opcode | Description || -------- | ----------- || `push` | Pushes an element to the stack || `pall` | Prints all the values on the stack || `pint` | Prints the value at the top of the stack || `pop` | Removes the top element of the stack || `swap` | Swaps the top two elements of the stack || `queue` | Sets the format of the data to a queue (FIFO) || `stack` | Sets the format of the data to a stack (LIFO) || `nop` | Doesn't do anything || `add` | Adds the top two elements of the stack || `sub` | Subtracts the top element of the stack from the second top element of the stack || `mul` | Multiplies the second top element of the stack with the top element of the stack || `div` | Divides the second top element of the stack by the top element of the stack || `mod` | Computes the rest of the division of the second top element of the stack by the top element of the stack || `pchar` | Prints the char at the top of the stack || `pstr` | Prints the string starting at the top of the stack || `rotl` | Rotates the stack to the top || `rotr` | Rotates the stack to the bottom |
Comments, indicated with `#`, are not executed by the interpreter.
When a **nonextistent opcode** is passed, the interpreter prints an error message and stops:
```bash$ cat errorfile.mpush 1pintpcx$ ./monty errorfile.m1L3: unknown instruction pcx```
### Return valueWhen there is no errors, `monty` returns `0`. Otherwise, returns `1`
## Authors* Goodness Nwaneri: [Twitter](https://twitter.com/goodnessnwa) - [GitHub](https://github.com/goodnessnwa)*
 Oliver Samuel: [Twitter](https://twitter.com/tecnophille) - [GitHub](https://github.com/tecnophille)
