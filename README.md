# SKILL1_MPMC_BHARATH

## AIM

Write an assembly language program in 8051 to calculate the sum of 5 numbers stored sequentially in memory and store the result in a another memory location.

## APPARATUS REQUIRED

Personal computer with Keil software

## ALGORITHM

1. Initialize pointer register (R0) to the starting address of the 5 numbers (e.g., 30H).
2. Clear accumulator A to 00H (will hold running sum).
3. Load counter (R1) with 05 (number of data elements).
4. Loop:
5. Save the current sum into B (MOV B,A).
6. Load the current data byte from memory pointed by R0 into A (MOV A,@R0).
7. Add previous sum (in B) to current number (ADD A,B) → new running sum in A.
8. Increment pointer R0 to next data byte.
9. Decrement counter R1 and repeat loop until zero.
10. Store final sum from A into a chosen internal RAM location (e.g., 35H).
11. End / infinite loop or RET.

## PROGRAME
```
ORG 0000H
MOV RO, #30H
MOV R1, #5
CLR A
SUM LOOP:
MOV B, A
MOV A, @RO
ADD A, B
INC RO
DJNZ R1, SUM_LOOP
MOV 35H, A
END
```
## OUTPUT

<img width="819" height="516" alt="Screenshot 2025-10-13 195850" src="https://github.com/user-attachments/assets/a0123b4f-6b95-4b96-966b-0768aff6ef26" />

<img width="819" height="540" alt="Screenshot 2025-10-13 091810" src="https://github.com/user-attachments/assets/c17f1a9d-ca65-49c0-93ab-fad174e12312" />


## RESULT

Thus, the sum of five numbers stored sequentially in memory was calculated and executed successfully using 8051 microcontroller.
