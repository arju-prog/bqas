

## Q1) Solve the following questions as per the given instructions:

### a) The representation of the value of a 16-bit unsigned integer X in a hexadecimal number system is BCA9. The representation of the value of X in the octal number system is:
**Solution:**

```
(BCA9)16

=(1011 1100 1010 1001)2

=(1 011 110 010 101 001)2

=(136251)8
```

### b) Convert (8.3637)10 to its exact equivalent base 8 number.
**Solution:**

To convert 8.363710 to base 8, we first separate it into the integer part (8) and the fractional part (0.3637). For the integer part, dividing 8 by 8 gives a quotient of 1 and a remainder of 0, so 810=108 . For the fractional part, we repeatedly multiply by 8, recording the integer parts:

```
0.3637×8=2.9096(2),

0.9096×8=7.2768(7),

0.2768×8=2.2144(2), and so on,
```
yielding 0.272158 (up to 5 places). Combining both parts, 8.363710 ≈10.272158.

---

## Q2) The output F of the Circuit Shown below is:
**Solution:**

For the first mux:
```
𝑌 = 𝐵'. 1 + 𝐵. 0

𝑌 = 𝐵'

𝐼1 = 𝑌
```

The Equation for the Second Mux is:
```
𝐹 = 𝐴'. 𝐼0 + 𝐴. 𝐼1

= 𝐴'. 1 + 𝐴. 𝐵'
= 𝐴'. (1 + 𝐵') + 𝐴. 𝐴𝐵'

= 𝐴' + 𝐴'. 𝐵' + 𝐴. 𝐵'
= 𝐴' + 𝐵'. (𝐴' + 𝐴)

= 𝐴' + 𝐵'. (1)
𝐹 = 𝐴' + 𝐵' = (𝐴𝐵)'
```

---

## Q3) A logic network has two data inputs, A and B, and two control inputs, C₀ and C₁. It implements the function F according to the following table:

| C₁ | C₀ | F              |
|----|----|----------------|
| 0  | 0  | F = ( A + B )’|
| 0  | 1  | F = A + B      |
| 1  | 0  | F = A⊕ B       |
| 1  | 1  | F = 0          |

### a) Create the expanded truth table for F based on all possible values of C₁, C₀, A, and B.

| C₁ | C₀ | A | B | Function F |
|----|----|---|---|------------|
| 0  | 0  | 0 | 0 | 1          |
| 0  | 0  | 0 | 1 | 0          |
| 0  | 0  | 1 | 0 | 0          |
| 0  | 0  | 1 | 1 | 0          |
| 0  | 1  | 0 | 0 | 0          |
| 0  | 1  | 0 | 1 | 1          |
| 0  | 1  | 1 | 0 | 1          |
| 0  | 1  | 1 | 1 | 1          |
| 1  | 0  | 0 | 0 | 0          |
| 1  | 0  | 0 | 1 | 1          |
| 1  | 0  | 1 | 0 | 1          |
| 1  | 0  | 1 | 1 | 0          |
| 1  | 1  | 0 | 0 | 0          |
| 1  | 1  | 0 | 1 | 0          |
| 1  | 1  | 1 | 0 | 0          |
| 1  | 1  | 1 | 1 | 0          |

### b) Circuit Implementation:

Design and implement the circuit using the following components:
- One 4-to-1 Multiplexer
- One 2-input Exclusive OR (XOR) Gate
- One 2-input AND Gate
- One 2-input OR Gate
- One Inverter

---

## Q4) Consider a hypothetical machine with the following specifications:

**a)** Draw the best hardware implementation for realizing the instruction OR R1, R1, #0xFF.

**Solution:**

To implement the instruction OR R1, R1, #0xFF, you need:

1. Inputs:
   - R1 (8-bit register).
   - Immediate value #0xFF (8 bits hardcoded as 11111111).
2. Logic:
   - Use 8 parallel 2-input OR gates (one for each bit of R1).
   - Each gate takes one bit from R1 and the corresponding bit from #0xFF.
   - The output of each gate is stored back into the respective bit of R1.
3. Output:
   - The output is written back to R1, setting all its bits to 1.

**b)** Consider the instruction MUL R1, R2, R3. What should be the maximum and minimum values of R2 and R3 to obtain the correct output in R1?

**Solution:**

Each register (R2 and R3) can store 8-bit values, meaning their range is from 0 to 255 (unsigned).

The multiplication of two 8-bit numbers can result in a 16-bit value. Since the result must fit into R1 (8 bits):
- The maximum value for R2 and R3 is 15 (so the result fits within 8 bits: 15×15=225).
- The minimum value is 0.

**c)** Draw the best hardware implementation for realizing the instruction MUL R1, R2, R3.

**Solution:**

1. Use a multiplier circuit capable of multiplying two 8-bit values (from R2 and R3).
2. Connect the outputs of R2 and R3 to the multiplier inputs.
3. The result is truncated to 8 bits (lower byte) since R1 can only store 8 bits.
4. Write the truncated result into R1.

Components:
- Two 8-bit buses for R2 and R3.
- An 8-bit multiplier circuit.
- A write-back control signal to store the result in R1.

**d)** What is the addressability and address space of the given memory?

**Solution:**

- Address Space: The memory has 256 locations, which can be accessed using an 8-bit address. Therefore, the address space is 28 = 256.
- Addressability: Each memory location stores 8 bits of data. Hence, the addressability is 8 bits.
