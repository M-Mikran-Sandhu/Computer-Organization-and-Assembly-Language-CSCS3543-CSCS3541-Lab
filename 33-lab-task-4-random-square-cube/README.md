# Task 4: Random Number, Square and Cube

Name: Mikran Sandhu
Roll Number: 260

## What it does
An x86 assembly program (MASM with the Irvine32 library) that reads a number from the user, generates a random number from 0 up to that number (both included), then prints the random number, its square and its cube.

## Concepts used
- Data section with strings (`DB`) and variables (`DD`)
- `writestring`, `readint`, `writeint` and `crlf` from the Irvine32 library
- `inc` to add 1 to a variable
- `Randomize` and `RandomRange` for random numbers
- `mul` for multiplication (the result is placed in `eax`)
- Storing a value from `eax` into a variable with `mov`

## Requirements
- MASM with the Irvine32 library
- 32-bit x86 (`.386`)

## Sample run
The random number changes on every run.

```text
Enter a Random Number: 10
Random Number is: +4
Square of a Number is :+16
Cube of a Number is +64
```

```text
Enter a Random Number: 5
Random Number is: +3
Square of a Number is :+9
Cube of a Number is +27
```

## Notes
- The number you enter is the highest value the random number can be. `inc` adds 1 first because `RandomRange` never returns the limit itself.
- `mul var1` multiplies `eax` by `var1` and keeps the answer in `eax`.
- The square is `number x number`. The cube multiplies that square by the number again.
- `writeint` prints the sign, so results show as `+16`.
- The cube is shown correctly only up to about 1290, because larger results do not fit in a signed 32-bit register.
- The program is meant for numbers that are 0 or more.

## What I learned
I learned how to use mul. The number in eax is multiplied by the variable and the answer stays in eax.
For the square I multiply the number by itself.
For the cube I multiply the square by the number once more.
I also learned that I must multiply by the original number, not by the square, or I get the fourth power.
crlf works like endl in C++ and moves the output to a new line.