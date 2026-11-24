# Task 1: Assembly Basics

## What it does
Two small programs written in x86 assembly (MASM with the Irvine32 library).

1. **30.1-average-admission.asm**: reads the marks of three subjects, finds the average, and prints `ADMISSION GRANTED!` if the average is above 80, otherwise `FAIL!`. If the average is below 0 or above 100, it prints an invalid input message and asks for the marks again.
2. **30.2-even-odd.asm**: reads one number and prints `EVEN` or `ODD`.

## Concepts used
- Data section with strings (`db`) and variables (`dd`)
- `writestring` and `readint` from the Irvine32 library
- `mov`, `add` and `cmp`
- `div` and the remainder stored in `edx`
- Conditional jumps (`je`, `jg`, `jl`, `jle`) and `jmp`
- Labels used like if/else and a retry loop

## Requirements
- MASM with the Irvine32 library
- 32-bit x86 (`.386`)

## Sample run

Average admission:
```text
Enter 1st subject marks:90
Enter 2nd subject marks:85
Enter 3rd subject marks:80
ADMISSION GRANTED!
```

```text
Enter 1st subject marks:60
Enter 2nd subject marks:70
Enter 3rd subject marks:50
FAIL!
```

Even or odd:
```text
Enter a number:14
EVEN
```

```text
Enter a number:7
ODD
```

## Notes
- The average uses integer division, so the decimal part is dropped. For example, marks 80, 81 and 81 give an average of 80.
- An average of exactly 80 counts as FAIL, because the check is "greater than 80".
- In even/odd, the number is divided by 2 and the remainder is checked: 0 means EVEN and 1 means ODD.

## What I learned
Numbers are read with readint and the value comes back in eax.
Division puts the answer in eax and the remainder in edx.
For even or odd I divide by 2 and check the remainder.
cmp followed by a jump works like an if statement in C++.
A label and jmp can send the program back to the start to ask again.