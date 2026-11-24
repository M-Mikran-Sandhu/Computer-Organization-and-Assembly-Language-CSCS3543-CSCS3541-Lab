# Task 2: Average of Five Numbers

## What it does
An x86 assembly program (MASM with the Irvine32 library) that reads five numbers, adds them, divides the sum by 5 and prints the average. The code is in `Average-of-5.asm`.

## Concepts used
- Data section with strings (`DB`) and variables (`DD`)
- `writestring`, `readint` and `writeint` from the Irvine32 library
- Storing each input in a variable with `mov`
- Adding values with `add`
- `div` with the divisor stored in a variable (`var6 = 5`)
- Clearing `edx` before division

## Requirements
- MASM with the Irvine32 library
- 32-bit x86 (`.386`)

## Sample run
```text
Enter 1st Number: 10
Enter 2nd Number: 20
Enter 3rd Number: 30
Enter 4th Number: 40
Enter 5th Number: 50
+30
```

```text
Enter 1st Number: 1
Enter 2nd Number: 2
Enter 3rd Number: 3
Enter 4th Number: 4
Enter 5th Number: 6
+3
```

## Notes
- `writeint` prints the sign, so a positive answer shows as `+30`.
- The division is integer division, so the decimal part is dropped. In the second run the sum is 16, and 16 / 5 gives 3.
- `div` is unsigned, so the program is meant for numbers that are 0 or more.

## What I learned
I learned how to read many numbers and store each one in its own variable.
I add the numbers in eax, then divide by 5 using div.
Before div I set edx to 0, because div uses edx and eax together.
The answer of div comes back in eax and the remainder in edx.
writeint prints the number with its sign.