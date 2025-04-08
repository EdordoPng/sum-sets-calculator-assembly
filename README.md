# sum-sets-calculator-assembly
This MIPS assembly program calculates the minimum and maximum sums from sets of numbers.

# MIPS Assembly - Sum Sets Calculator

## Description
This MIPS assembly program calculates the minimum and maximum sums from sets of numbers. The program asks the user to input a series of numbers (terminated by entering 0). It then calculates:

1. The maximum sum - formed by adding all numbers except the smallest one
2. The minimum sum - formed by adding all numbers except the largest one

Each sum set differs from the others as it excludes one number from the total sum, with the excluded number varying between sets.

## How It Works
1. The user enters numbers one by one, inputting 0 to end the input phase
2. The program tracks the minimum and maximum numbers entered
3. It calculates the total sum of all numbers
4. The minimum sum = (total sum - maximum number)
5. The maximum sum = (total sum - minimum number)
6. The program displays both results along with the respective discarded numbers

## Overflow Handling
The program includes logic to detect arithmetic overflow during the summation process and will terminate with an error message if overflow occurs.

## Technical Details
- Target Architecture: MIPS
- Memory Layout:
  - ROM data at 0x10000100
  - RAM data at 0x10011000
  - Text segment at 0x400100

## Usage
Load this program in a MIPS simulator (like MARS, SPIM, or QtSPIM) and run it. Follow the prompts to enter your numbers.

```
Enter a number, 0 to start computation:
[Enter your numbers, one at a time, finishing with 0]
```

## Example Output
```
Enter a number, 0 to start computation:
5
Enter a number, 0 to start computation:
10
Enter a number, 0 to start computation:
15
Enter a number, 0 to start computation:
0
The minimum sum is = 20
The discarded number is: 15
The maximum sum is = 25
The discarded number is: 5
Program terminating.
```
