
# ALU (8BIT)

OPCODES
```
MUX_sel[2:0] = 
  000 → PASS
  001 → OR
  010 → AND
  011 → XOR
  100 → ADD
  101 → SUB
  110 → SHR
  111 → SHL
```

<img src="https://github.com/regalk13/cpu8bits-dls/blob/main/learning/alu/assets/ALU0.png?raw=true" />

OUT-FLAGS

1. Result[7:0]

Main 8-bit data bus.

2. VF flag

Vₓ register bit F (V_F) for every “flag” output, ALU should produce one single flag bit, write back into V_F:

    On ADD (8xy4):
    VF = carry-out of the 8-bit adder (1 if A+ B ≥ 256, else 0)

    On SUB (8xy5):
    VF = ¬borrow = 1 if A ≥ B, else 0

    On SHR (8xy6):
    VF = original bit 0 of A (the “shifted-off” LSB)

    On SHL (8xyE):
    VF = original bit 7 of A (the “shifted-off” MSB)

    All other operations (PASS, OR, AND, XOR) leave VF unchanged.

3. Zero Flag

4. Sign/Negative flag (N)

5. Overflow flag (V)


# Basic 4bit-ALU 

Basic 4bit-ALU (Inside project)

### ADDER
<img src="https://github.com/regalk13/cpu8bits-dls/blob/main/learning/alu/assets/ADDER.png?raw=true" />

### 4BIT-ADDER
<img src="https://github.com/regalk13/cpu8bits-dls/blob/main/learning/alu/assets/4BIT-ADDER.png?raw=true" />

### ALU

<img src="https://github.com/regalk13/cpu8bits-dls/blob/main/learning/alu/assets/ALU.png?raw=true" />
