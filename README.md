## 4-bit ALU - RTL Design and Verification

Self-Checking Verilog ALU implementation designed to learn RTL design and
verification principles

## Description:
It is an implementation of a 4-bit Arithmetic Logic Unit which supports 8
arithmetic operations including carry, zero and overflow flags. The ALU is
combined with an exhaustive and self-checking testbench which checks
all 2,048 possible input combinations against a reference model – not just
a small set of selected input vectors.

It was created as a first hands-on exercise in designing and verifying
digital circuits.

## Design:
Opcode - Operation
-------------------
000  -  ADD 

001  -  SUB 

010  -  AND 

011  -  OR 

100  -  XOR 

101  -  NOT 

110  -  Shift Left 

111  - Shift Right 

## Output: 
result (4-bit), carry_out, zero, overflow – common ALU

flags used to indicate special cases

## Verification Strategy:
Instead of randomly checking specific scenarios, the testbench:

Checks all 16 × 16 × 8 = 2,048 possible combinations of a, b, and opcode

Builds a golden model independently within the testbench for every combination

Reports a discrepancy when there is a difference between the design’s output and the expected value, along with the failing values

This strategy follows the central theme of functional verification in the industry, which is “Do not just check what is supposed to work; but rather try to break it; never trust the design itself.”


## Skills Demonstrated:
RTL design fundamentals in Verilog (combinational logic, always blocks, bit-level operations)

Self-checking testbench methodology

Exhaustive functional verification over hand-picked test vectors

## Possible Extensions:
Parameterize bit-width (4-bit → N-bit ALU)

Add signed comparison flags (a > b, a < b, a == b)

Rewrite the testbench using basic SystemVerilog assertions
