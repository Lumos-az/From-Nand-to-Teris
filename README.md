# From-Nand-to-Teris

### 1.1 Boolean Logic

#### Distributive Laws

- (x AND (y OR z)) = (x AND y) OR (x AND z)

- (x OR (y AND z)) = (x OR y) AND (x OR z)

#### De Morgan Laws

- NOT(x AND y) = NOT(x) OR NOT(y)

- NOT(x OR y) = NOT(x) AND NOT(y)

### 1.2 Boolean Functions Synthesis

#### Truth Table to Boolean Expression

Construct boolean expression for each row whose out is 1 and then OR them together

#### NAND

(x NAND y) = NOT(x AND y)

#### Theorem

Any Boolean function can be represented using an expression containing only NAND operations

### 1.3 Logic Gates

### 1.4 Hardware Description Language

- HDL is a functional/declarative language

- The order of HDL statements is insignificant

### 1.6 Multi-Bit Buses

#### Sub-buses

- Buses can be composed from (and broken into) sub-buses
- Some syntactic choices of our HDL
  - Overlaps of sub-buses are allowed on output buses of parts
  - Width of internal pins is deduced automatically
  - "false" and "true" may be used as buses of any width

### 2.3 Negative Number

#### 2's Complement

Represent Negative number -x using the positive number 
$$
2^n-x
$$

### 2.4 Arithmetic Logic Unit

if zx then x = 0

if nx then x = !x

if zy then y = 0

if ny then y = !y

if f then out = x + y else out = x & y

if no then out = !out

if out == 0 then zr = 1 else zr = 0

if out < 0 then ng = 1 else ng = 0

### 3.1 Sequential Logic

Combinatorial: out[t] = function(in[t])

Sequential: out[t] = function(in[t - 1])

### 3.2 Flip Flops

Gates that can flip between two states are called Flip-Flops

#### 1-Bit Register

<img src="/Users/heangzhan/Library/Application Support/typora-user-images/image-20211201134443707.png" alt="image-20211201134443707" style="zoom: 33%;" />

if load(t - 1) then out(t) = in(t - 1) else out(t) = out(t - 1)

#### 1-Bit Register

<img src="/Users/heangzhan/Library/Application Support/typora-user-images/image-20211201135414986.png" alt="image-20211201135414986" style="zoom: 33%;" />

### 3.3 Memory Unites

#### RAM unit

- A sequence of n addressable registers, with addresses 0 to n - 1

- At any given point of time, only one register in the RAM is selected

- k(width of address input): k = log2n

- w(word width): No impact on the RAM logic 

<img src="/Users/heangzhan/Library/Application Support/typora-user-images/image-20211201164637759.png" alt="image-20211201164637759" style="zoom:33%;" />

### 3.4 Counters

- The  computer must keep track of which instruction should be fetched and executed next
  - This control mechanism can be realized by a Program Counter
- The PC contains the address of the instruction that will be fetched and executed next
  - Reset: fetch the first instruction
  - Next: fetch the next instruction
  - Goto: fetch instruction n

<img src="/Users/heangzhan/Library/Application Support/typora-user-images/image-20211201211847233.png" alt="image-20211201211847233" style="zoom:33%;" />

### 4.2 Machine Languages: Elements

#### Memory Hierarchy

- Accessing a memory location is expensive
- Solution: Memory Hierarchy

<img src="/Users/heangzhan/Library/Application Support/typora-user-images/image-20211208171952447.png" alt="image-20211208171952447" style="zoom: 33%;" />

#### Register

- Data Register
- Address Register

#### Address Modes

- Register
  - Add R1, R2
- Direct
  - Add R1, M[200]
- Indirect
  - Add R1, @A
- Immediate
  - Add 73, R1

### 4.3 The Hack Computer and Machine Language

#### Register

- D holds a 16-bit value
- A holds a 16-bit value
- M represents the 16-bit RAM register addressed by A

<img src="/Users/heangzhan/Library/Application Support/typora-user-images/image-20211208174222794.png" alt="image-20211208174222794" style="zoom: 33%;" />

#### The A-instruction

The first bit of A-instruction is 0

@value

- sets the A register to value
- Side effect: RAM[A] becomes the selected RAM register

#### The C-instruction

The first bit of C-instruction is 1

<img src="/Users/heangzhan/Library/Application Support/typora-user-images/image-20211208174919346.png" alt="image-20211208174919346" style="zoom:33%;" />

<img src="/Users/heangzhan/Library/Application Support/typora-user-images/image-20211209095855544.png" alt="image-20211209095855544" style="zoom:33%;" />

### 4.5 Input/Output

#### Screen memory map

<img src="/Users/heangzhan/Library/Application Support/typora-user-images/image-20211209102128654.png" alt="image-20211209102128654" style="zoom: 50%;" />

#### Keyboard memory map

<img src="/Users/heangzhan/Library/Application Support/typora-user-images/image-20211209104053671.png" alt="image-20211209104053671" style="zoom:50%;" />

### 4.6 - 4.8 Hack Programming

#### Working with registers and memory

- To terminate a program safely, end it with an infinite loop
- <img src="/Users/heangzhan/Library/Application Support/typora-user-images/image-20211209141023592.png" alt="image-20211209141023592" style="zoom:50%;" />

#### Branch

@LABEL translate to @n, where n is the instruction number following the (LABEL) declaration

#### Variables

- @temp: find some available memory register(say register n), and use it to represent the variable temp. So, from now on, each occurrence of @temp in the program will be translated into @n
- A reference to a symbol that has no corresponding label declaration is treated as a reference to a variable

#### Iteration

#### Pointers

Variables that store memory addressed are called pointers

#### Input/Output

<img src="/Users/heangzhan/Library/Application Support/typora-user-images/image-20211209152114948.png" alt="image-20211209152114948" style="zoom:50%;" />

### 5.1 Von Neumann Architechture

![image-20211215101638879](/Users/heangzhan/Library/Application Support/typora-user-images/image-20211215101638879.png)

### 5.2 The Fetch-Execute Cycle

#### Fetch-Execute Clash

<img src="/Users/heangzhan/Library/Application Support/typora-user-images/image-20211215104359804.png" alt="image-20211215104359804" style="zoom:50%;" />

#### Solution

<img src="/Users/heangzhan/Library/Application Support/typora-user-images/image-20211215103109359.png" alt="image-20211215103109359" style="zoom:50%;" />

#### Simpler Solution: Harvard Architecture

Keep program and Data in two separate memory modules

### 5.3 Central Processing Unit

#### Hack CPU Interface

<img src="/Users/heangzhan/Library/Application Support/typora-user-images/image-20211215105728285.png" alt="image-20211215105728285" style="zoom:50%;" />

#### Hack CPU Implement

<img src="/Users/heangzhan/Library/Application Support/typora-user-images/image-20211215111542971.png" alt="image-20211215111542971" style="zoom:50%;" />

### 5.4 The Hack Computer

#### Hack Computer implementation

<img src="/Users/heangzhan/Library/Application Support/typora-user-images/image-20211215175239063.png" alt="image-20211215175239063" style="zoom:50%;" />

#### Hardware Organization

<img src="/Users/heangzhan/Library/Application Support/typora-user-images/image-20211215175735850.png" alt="image-20211215175735850" style="zoom:50%;" />

### 6.1 Assembly Languages and Assemblers

#### Basic Assembler Logic

<img src="/Users/heangzhan/Library/Application Support/typora-user-images/image-20211218145754900.png" alt="image-20211218145754900" style="zoom:50%;" />

#### Symbol Table

- Used for labels/variables
- Assembler must replace names with addresses
- Forward references
  - Leave blank until label appears, then fix
  - In first pass just figure out all addresses

### 6.3-6.4 The Assembly Process

#### Translating A-instructions

- If value is a decimal constat, generate the equivalent 15-bit binary constant
- If value is a symbol, construct the Symbol table
  - Initialization: Pre-defined symbols
  - First pass: Label symbols
  - Second pass: Variable symbols

#### Translating C-instructions

For each field in the instruction, generate the corresponding binary code
