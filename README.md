# chromite-bug-bounty
# Week1

## Ratified Instructions
  - M Integer Multiplication and Division
  - A Atomic Instructions
  - F Floating Point Instruction
  - D Double Precision F
  - Q Quad Precision F
  - Zicsr Control Status Register
  - C Compressed Instruciton (16 bit)
  - Ziefenceei Instruction-Fetch Fence
## Few Unratified Instructions
  - V Vector Ops 
  - B Bitmanipulation Ops
  - N User-Level Interrupts
  - S Supervisor-level Instructions
  - K Crypto Extension
## Reason for Odd Immediate Encoding in the ISA
The ISA has a few types (R,S,I,J,B,U) of instruction formats that are used with offsets. These offsets are saved as immediates. The ISA follows a little-endian method of addressing and the lower two bits for a 32bit instruction are ones. 

-> The reason for the odd formats is to reduce hardware decoding complexity while also conforming to the other instructions. The instruction decoders can be made simpler by making most formats conform to a particular style. E.g The branch format has a few of its bits(12 and 11) scattered to make it such that the formats will always expect a particular value (eg:imm[5] ) at a specific instructions bit( eg:25th).
## How many instructions can you add ?

Within the 32-bit instr,only the OP codes are mutable and are 7 bits long. So that leaves us with 2^7(128) instructions. inculuding the 40 required for base ISA RV32I. So 88 instructions otherwise.
