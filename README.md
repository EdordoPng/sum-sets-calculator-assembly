# MIPS Assembly - Sum Sets Calculator

![MIPS Logo](https://img.shields.io/badge/MIPS-Assembly-blue)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

A MIPS assembly program that calculates the minimum and maximum possible sums from a set of user-provided numbers by selectively excluding one number at a time.

## 📋 Table of Contents
- [Description](#description)
- [Algorithm Explanation](#algorithm-explanation)
- [Overflow Handling](#overflow-handling)
- [Technical Details](#technical-details)
- [Usage Instructions](#usage-instructions)
- [Example Output](#example-output)
- [Register Usage](#register-usage)

## 📝 Description

This MIPS assembly program determines the minimum and maximum possible sums from sets of numbers. The user inputs a series of numbers (entering 0 to terminate input), and the program calculates:

- **Maximum Sum**: The sum of all entered numbers **except** the smallest one
- **Minimum Sum**: The sum of all entered numbers **except** the largest one

In mathematical terms, if you have entered _n_ numbers, the program calculates _n_ different possible sums, each excluding one number, and finds the minimum and maximum among these sums.

## 🧮 Algorithm Explanation

The algorithm works through these steps:

1. **Input Phase**: 
   - User enters numbers one by one
   - Input terminates when the user enters 0
   - During input, the program keeps track of:
     - The smallest number entered
     - The largest number entered
     - The running sum of all numbers

2. **Calculation Phase**:
   - **Minimum Sum** = (Total Sum) - (Maximum Number)
   - **Maximum Sum** = (Total Sum) - (Minimum Number)

3. **Output Phase**:
   - The program displays:
     - The minimum sum and the number excluded to obtain it
     - The maximum sum and the number excluded to obtain it

## ⚠️ Overflow Handling

The program implements logic to detect arithmetic overflow during the summation process. If an overflow occurs:

- The program will immediately terminate
- An error message will be displayed: "The program has encountered overflow. END"
- This prevents incorrect results due to binary addition limitations

## 🔧 Technical Details

- **Target Architecture**: MIPS
- **Memory Layout**:
  - ROM data segment: `0x10000100`
  - RAM data segment: `0x10011000`
  - Text segment: `0x400100`
- **Compatible Simulators**:
  - MARS (MIPS Assembler and Runtime Simulator)
  - SPIM
  - QtSPIM

## 🚀 Usage Instructions

1. Load the program into a MIPS simulator (MARS, SPIM, or QtSPIM)
2. Run the program
3. Follow the prompts to enter your numbers:
   ```
   Enter a number, 0 to start computation:
   ```
4. Enter each number followed by Enter
5. Enter 0 when you're done inputting numbers
6. The program will display the results

## 📊 Example Output

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

## 📋 Register Usage

| Register | Purpose |
|----------|---------|
| `$s0` | Starting address of max/min constants in ROM |
| `$s1` | Temporary storage for currently read data |
| `$s2` | Minimum value entered (initialized to max representable) |
| `$s3` | Maximum value entered (initialized to min representable) |
| `$s4` | Running total sum of all entered numbers |
| `$t0` | Used for overflow detection comparisons |
| `$t1` | Used for storing sign in overflow checks |
| `$t2` | Storage for the maximum sum result |
| `$t3` | Storage for the minimum sum result |
