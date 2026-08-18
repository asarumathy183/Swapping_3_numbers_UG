# Swapping_3_numbers_UG
## Experiment: Write and Simulate Swapping of Three Numbers using Verilog HDL and Verify with Testbench

## Aim

To write, simulate, and verify the swapping of three numbers using Verilog HDL and validate the functionality using a testbench in Xilinx Vivado.

## Apparatus Required

* Xilinx Vivado Design Suite
* Computer System (Windows/Linux)
* Verilog HDL Simulator (Integrated in Vivado)

## Procedure

1. Open Xilinx Vivado and create a new RTL project.
2. Create a Verilog source file named **swap3.v**.
3. Write the Verilog HDL code for swapping three numbers.
4. Save the design file.
5. Create a testbench file named **swap3_tb.v**.
6. Apply different input values through the testbench.
7. Run **Behavioral Simulation**.
8. Observe the waveform and verify whether the values are swapped correctly.
9. Record the simulation results.

## Verilog HDL Code

```
module swap_1(
input [3:0] a,
input [3:0] b,
input [3:0] c,
output reg [3:0] x,
output reg [3:0] y,
output reg [3:0] z
);
reg [3:0] ta,tb,tc;
reg [3:0] temp;
always@(*)begin
ta=a;
tb=b;
tc=c;
temp=ta;
ta=tb;
tb=tc;
tc=temp;
x=ta;
y=tb;
z=tc;
end
endmodule
```

## Testbench Code

```
`timescale 1ns/1ps
module swap_tb;
    reg [3:0] a;
    reg [3:0] b;
    reg [3:0] c;

    wire [3:0] x;
    wire [3:0] y;
    wire [3:0] z;

    swap_1 uut (
        .a(a),
        .b(b),
        .c(c),
        .x(x),
        .y(y),
        .z(z)
    );

    initial begin
        a = 4'd1;  b = 4'd2;  c = 4'd3;
        #10;

        a = 4'd5;  b = 4'd7;  c = 4'd9;
        #10;

        a = 4'd10; b = 4'd12; c = 4'd15;
        #10;

        a = 4'd0;  b = 4'd8;  c = 4'd4;
        #10;

        $finish;
    end
endmodule
```

## Expected Output
<img width="800" height="700" alt="image" src="https://github.com/user-attachments/assets/4510af87-e233-43fe-8b45-ebf3dd8fc6a7" />
<img width="800" height="700" alt="image" src="https://github.com/user-attachments/assets/0124c0e7-f155-4ce6-9071-f950d7f5135f" />

## Result

The swapping operation is successfully simulated using Verilog HDL.

## Conclusion

Thus, the Verilog HDL program for swapping three numbers was implemented and simulated successfully using Xilinx Vivado. The output waveform and simulation results verified the correct cyclic swapping of the three numbers using the testbench.
