# Lab Task 6

Name: Muhammad Mikran Sandhu
Roll Number: 260

## What it does
Two programs written in x86 assembly (MASM with the Irvine32 library).

1. **question-1-weekday.asm**: reads a number from 1 to 7 and prints the day of the week (1 = Monday, 7 = Sunday). Any other number prints `Invalid Number.` and the program ends.
2. **question-2-grade.asm**: reads marks from 1 to 100 and prints the grade. Marks outside this range print `Your input number is not correct` and the program asks again.

Grade table used in Question 2:

| Marks | Grade |
|-------|-------|
| 90 to 100 | A |
| 80 to 89 | B |
| 70 to 79 | C |
| 60 to 69 | D |
| 1 to 59 | F |

## Concepts used
- Data section with strings (`DB`)
- `writestring`, `readint` and `crlf` from the Irvine32 library
- `cmp` with conditional jumps (`je`, `jg`, `jge`, `jl`, `jle`)
- Labels used like switch cases and if/else
- `jmp` to go back and ask again (Question 2)
- Input validation

## Requirements
- MASM with the Irvine32 library
- 32-bit x86 (`.386`)

## Sample run

Question 1:
```text
Enter a number=1
Today is Monday
```

```text
Enter a number=7
Today is Sunday
```

```text
Enter a number=9
Invalid Number.
```

Question 2:
```text
Enter a number=95
GRADE IS A
```

```text
Enter a number=40
GRADE IS F
```

```text
Enter a number=150
Your input number is not correct
Enter a number=85
GRADE IS B
```

## Notes
- Question 1 compares the number with 1 to 7 one by one, like a switch statement in C++. The checks for 8 and above and for 0 and below catch the invalid numbers.
- Question 1 does not ask again after an invalid number. The program ends.
- In Question 2 the checks go from the highest grade to the lowest, so the first matching `cmp` decides the grade. That is why 90 gives A and not B.
- Marks of exactly 100 are accepted, and 0 is invalid.
- Neither program prints a new line after the result message.

## What I learned
A series of cmp and jump lines works like an if-else ladder or a switch in C++.
In the grade program the order of the checks matters, because the first one that matches wins.
I check the highest grade first and go down to the lowest.
Labels mark where the code jumps to, and jmp can send the program back to ask for the input again.
I also learned to reject numbers outside the valid range before using them.
