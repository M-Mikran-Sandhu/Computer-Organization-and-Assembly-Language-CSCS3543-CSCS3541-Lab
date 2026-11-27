# Lab Task 9: Even and Odd Numbers in a Range

Name: Muhammad Mikran Sandhu
Roll Number: 260

## What it does

Four programs written in x86 assembly (MASM with the Irvine32 library). Each one reads a starting number and an ending number, then prints the even or odd numbers in that range, one per line.

| File                        | Prints       | Start and end numbers |
| --------------------------- | ------------ | --------------------- |
| question-1-even-numbers.asm | even numbers | included              |
| question-2-even-numbers.asm | even numbers | not included          |
| question-3-odd-numbers.asm  | odd numbers  | included              |
| question-4-odd-numbers.asm  | odd numbers  | not included          |

## Concepts used

- Data section with strings (`db`) and variables (`dd`)
- `writestring`, `readint`, `writeint` and `crlf` from the Irvine32 library
- `loop` with the counter in `ecx`
- `div` and the remainder in `edx`, used to test even or odd
- `cmp` with `je` and `jne`
- `inc` and `dec`

## Requirements

- MASM with the Irvine32 library
- 32-bit x86 (`.386`)

## How the loop is set up

- The range is `end - start`, stored in `rangee`.
- Questions 1 and 3 set `ecx = range + 1`, so the loop runs once for every number from start to end.
- Questions 2 and 4 set `ecx = range - 1` and add 1 to `startt` first, so the loop checks only the numbers between start and end.
- Each round divides `startt` by 2. If the remainder is 0 the number is even, otherwise it is odd. Then `startt` goes up by 1.

## Sample run

Question 1 (even, both ends included):

```text
Enter A starting number:1
Enter A ending number:10
+2
+4
+6
+8
+10
```

Question 2 (even, both ends not included):

```text
Enter A starting number:1
Enter A ending number:10
+2
+4
+6
+8
```

Question 3 (odd, both ends included):

```text
Enter A starting number:1
Enter A ending number:10
+1
+3
+5
+7
+9
```

Question 4 (odd, both ends not included):

```text
Enter A starting number:1
Enter A ending number:10
+3
+5
+7
+9
```

## Notes

- The programs are the same except for the loop start, the loop count and which remainder prints the number.
- In Questions 3 and 4 the jumps are swapped: a remainder of 0 skips the print, so only odd numbers are printed.
- `writeint` prints the sign, so numbers show as `+2`.
- The ending number must be bigger than the starting number. In Questions 2 and 4 it must be at least 2 bigger, otherwise `ecx` becomes 0 or negative and the loop runs a very large number of times.
- `div` is unsigned, so the programs are meant for numbers that are 0 or more.

## What I learned

I learned how to use a loop with ecx as the counter in assembly.
The loop instruction subtracts 1 from ecx and jumps back until ecx becomes 0.
To count the numbers in a range I subtract the start from the end and add 1 to include both ends.
I check even or odd by dividing by 2 and looking at the remainder in edx.
Changing the starting value and the count of the loop changes whether the end numbers are included.
