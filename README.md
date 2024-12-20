# 4-BIT-RIPPLE-COUNTER

**AIM:**

To implement  4 Bit Ripple Counter using verilog and validating their functionality using their functional tables

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

**4 Bit Ripple Counter**

A binary ripple counter consists of a series connection of complementing flip-flops (T or JK type), with the output of each flip-flop connected to the Clock Pulse input of the next higher-order flip-flop. The flip-flop holding the least significant bit receives the incoming count pulses. The diagram of a 4-bit binary ripple counter is shown in Fig. below.

![image](https://github.com/naavaneetha/4-BIT-RIPPLE-COUNTER/assets/154305477/cb4b74d4-31ab-4359-95d0-d22e67daba13)

In timing diagram Q0 is changing as soon as the negative edge of clock pulse is encountered, Q1 is changing when negative edge of Q0 is encountered(because Q0 is like clock pulse for second flip flop) and so on.

![image](https://github.com/naavaneetha/4-BIT-RIPPLE-COUNTER/assets/154305477/a573a7d6-014e-4e54-93e6-e2ac9530960b)

![image](https://github.com/naavaneetha/4-BIT-RIPPLE-COUNTER/assets/154305477/85e1958a-2fc1-49bb-9a9f-d58ccbf3663c)

**Procedure**
```
 1.Write the Verilog code in Quartus Prime for the 4-bit ripple counter.
 2.Compile and run the program to ensure it is error-free.
 3.Generate the RTL schematic to visualize the flip-flop connections.
 4.Create nodes for the clock input (CLK) and counter outputs (Q0, Q1, Q2, Q3).
5.Simulate the design for multiple clock cycles to observe the ripple effect.
 6.Verify the timing diagrams to ensure the counter toggles through all states (0000 to
 1111).
 7.Save the RTL schematic and timing diagrams for documentation and validation.
```
 

**PROGRAM**
```
module ripple(
   input wire clk,  // Clock input
   output reg [3:0] count // 4-bit counter output
 );
 // Counter logic
 always @(posedge clk) begin
   if (count == 4'b1111) // Reset when count reaches 15
       count <= 4'b0000;
   else
       count <= count + 1; // Increment count
 end
 endmodule
 // Testbench
 module RippleCounter_tb;
 // Inputs
 reg clk;
 // Outputs
 wire [3:0] count;
 // Instantiate the counter
 RippleCounter uut(
   .clk(clk),
   .count(count)
 );
 // Clock generation
 initial begin
   clk = 0;
   forever #5 clk = ~clk; // Toggle clock every 5 time units
 end

Program for 4 Bit Ripple Counter and verify its truth table in quartus using Verilog programming.

Developed by:Ashwin Kumar E RegisterNumber:24900900
```

**RTL LOGIC FOR 4 Bit Ripple Counter**

![Screenshot 2024-12-20 085614](https://github.com/user-attachments/assets/2b662c00-9c2d-4056-a94d-a7e4bc8d9f01)


**TIMING DIGRAMS FOR 4 Bit Ripple Counter**

![Screenshot 2024-12-20 085628](https://github.com/user-attachments/assets/57fdec03-78df-403a-abf2-4611006ce657)
![Screenshot 2024-12-20 085638](https://github.com/user-attachments/assets/52c4edce-aa88-4b3f-83a7-566085c4b47d)

**TRUTH TABLE**

![Screenshot 2024-12-20 085653](https://github.com/user-attachments/assets/e3f0b4d2-facb-41bd-bb1a-796ae3f18f25)




**RESULTS**
```
 Thus, the 4-bit Ripple Counter was successfully implemented, and its functionality was
 validated using the truth table
 ```
