# Task 3: Random Number

## What it does
An x86 assembly program (MASM with the Irvine32 library) that reads a number from the user and prints a random number between 0 and that number (both included).

## Concepts used
- Data section with a string (`DB`) and a variable (`DD`)
- `writestring`, `readint` and `writeint` from the Irvine32 library
- `inc` to add 1 to a variable
- `Randomize` to seed the random number generator
- `RandomRange`, which gives a number from 0 up to one less than the value in `eax`

## Requirements
- MASM with the Irvine32 library
- 32-bit x86 (`.386`)

## Sample run
The output changes every time because the number is random.

```text
Enter a Random Number: 10
+7
```

```text
Enter a Random Number: 5
+2
```

```text
Enter a Random Number: 0
+0
```

## Notes
- The number you enter is the highest value that can come out.
- `RandomRange` never returns the value in `eax` itself, so the program adds 1 first. This way the entered number can also be the result.
- `Randomize` is called once so the numbers are different on every run.
- `writeint` prints the sign, so the result shows as `+7`.
- The program is meant for numbers that are 0 or more. A negative input gives an unexpected result.

## What I learned
I learned how to get a random number in assembly using Randomize and RandomRange.
RandomRange takes its limit from eax and gives the answer back in eax.
The answer is from 0 to one less than the limit, so I add 1 with inc to include the number I entered.
Randomize is needed so the program does not give the same number every time.