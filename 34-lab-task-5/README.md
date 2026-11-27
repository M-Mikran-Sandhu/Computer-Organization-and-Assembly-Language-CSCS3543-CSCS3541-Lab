# Lab Task 5

Name: Muhammad Mikran Sandhu
Roll Number: 260

## What it does
Two programs written in x86 assembly (MASM with the Irvine32 library).

1. **question-1-average-marks.asm**: reads the marks of three subjects and finds the average. If the average is above 80 it prints `Admission Granted`, otherwise `Sorry,Fail!`. If the average is above 100, it prints `Invalid Input! Try Again` and asks for the marks again.
2. **question-2-even-odd.asm**: reads one number and prints `Even` or `Odd`.

## Concepts used
- Data section with strings (`DB`) and variables (`DD`)
- `writestring` and `readint` from the Irvine32 library
- `mov`, `add` and `cmp`
- `div` and the remainder stored in `edx`
- Clearing `edx` with `mov edx,0` before `div`
- Conditional jumps (`je`, `jg`, `jl`, `jle`) and `jmp`
- Labels used like if/else and a retry loop

## Requirements
- MASM with the Irvine32 library
- 32-bit x86 (`.386`)

## Sample run

Question 1:
```text
Enter Marks of Subject 1=90
Enter Marks of Subject 2=85
Enter Marks of Subject 3=80
Admission Granted
```

```text
Enter Marks of Subject 1=60
Enter Marks of Subject 2=70
Enter Marks of Subject 3=50
Sorry,Fail!
```

Question 2:
```text
Enter a Number: 14
Even
```

```text
Enter a Number: 7
Odd
```

## Notes
- The average uses integer division, so the decimal part is dropped. For example, marks 80, 81 and 81 give an average of 80.
- An average of exactly 80 counts as Fail, because the check is "greater than 80".
- Each mark is not checked on its own. Only the average is checked, so marks like 150, 50 and 50 (average 83) are accepted.
- In Question 2 the number is divided by 2 and the remainder is checked: 0 means Even and 1 means Odd.
- Both programs print no new line after the result message.

## What I learned
Numbers are read with readint and the value comes back in eax.
Division puts the answer in eax and the remainder in edx.
I set edx to 0 before div, because div uses edx and eax together.
For even or odd I divide by 2 and check the remainder.
cmp followed by a jump works like an if statement in C++.
A label and jmp can send the program back to the start to ask again.