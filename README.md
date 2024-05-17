# EXPERIMENT-3 SIMULATION AND IMPLEMENTATION OF MULTIPLIER
# DATE:

# AIM:

 To simulate and synthesis multiplier using Xilinx ISE.

# APPARATUS REQUIRED:

vivado 14.7
Spartan6 FPGA
  
# PROCEDURE:

STEP:1  Start  the vivado navigator, Select and Name the New project.
STEP:2  Select the device family, device, package and speed.       
STEP:3  Select new source in the New Project and select Verilog Module as the Source type.                       
STEP:4  Type the File Name and Click Next and then finish button. Type the code and save it.
STEP:5  Select the Behavioral Simulation in the Source Window and click the check syntax.                       
STEP:6  Click the simulation to simulate the program and  give the inputs and verify the outputs as per the truth table.               
STEP:7  Select the Implementation in the Sources Window and select the required file in the Processes Window.
STEP:8  Select Check Syntax from the Synthesize  XST Process. Double Click in the  FloorplanArea/IO/Logic-Post Synthesis process in the User Constraints process group. UCF(User constraint File) is obtained. 
STEP:9  In the Design Object List Window, enter the pin location for each pin in the Loc column Select save from the File menu.
STEP:10 Double click on the Implement Design and double click on the Generate Programming File to create a bitstream of the design.(.v) file is converted into .bit file here.
STEP:11  On the board, by giving required input, the LEDs starts to glow light, indicating the output.

Logic Diagram:
![image](https://github.com/navaneethans/VLSI-LAB-EXP-3/assets/6987778/7713750f-65e6-41c0-8082-5005eac4031c)

2 bit Multiplier:

VERILOG CODE:
```
module multiplier2by2(C,A,B);
input [1:0]A,B;
output [3:0]C;
wire w1,w2,w3,w4;
and (C[0],A[0],B[0]);
and (w1,A[0],B[1]);
and (w2,A[1],B[0]);
and (w3,A[1],B[1]);
halfadder ha1(C[1],w4,w1,w2);
halfadder ha2(C[2],C[3],w3,w4);
endmodule
module halfadder(sum,carry,a,b);
input a,b;
output sum,carry;
xor(sum,a,b);
and(carry,a,b);
endmodule
```

OUT PUT:

![image](https://github.com/Sandeep9347/VLSI-LAB-EXP-3/assets/160619092/ec53ffe2-1049-479e-be3a-b718e12beaab)

LOGIC DIAGRAM:

![image](https://github.com/navaneethans/VLSI-LAB-EXP-3/assets/6987778/d95215dd-8cf1-4e08-93cc-96adfdd7fbdc)


4 Bit Multiplier:

VERILOG CODE:
```
module multiplier_4bit(
input [3:0] a, b,
output [7:0] result
);
assign result = a * b;
endmodule
```

OUT PUT:

![image](https://github.com/Sandeep9347/VLSI-LAB-EXP-3/assets/160619092/8fda14e4-3715-417f-adfc-4cf8490064bb)



Result:

THUS THE SIMULATION AND IMPLEMENTATION OF MULTIPLIER IS DONE BY USING VERILOG CODE AND OUTPUT VERIFIED SUCCESSFULLY.



