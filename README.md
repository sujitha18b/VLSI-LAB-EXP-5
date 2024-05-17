# EXP 5

# DATE: 

# SIMULATION AND IMPLEMENTATION OF FINITE STATE MACHINE

# AIM: 
To simulate and synthesis finite state machine using Xilinx ISE.

# APPARATUS REQUIRED: 

Xilinx 14.7 
Spartan6 FPGA

# PROCEDURE: 
STEP:1 Start the Xilinx navigator, Select and Name the New project.
STEP:2 Select the device family, device, package and speed. 
STEP:3 Select new source in the New Project and select Verilog Module as the Source type. 
STEP:4 Type the File Name and Click Next and then finish button. Type the code and save it. 
STEP:5 Select the Behavioral Simulation in the Source Window and click the check syntax. 
STEP:6 Click the simulation to simulate the program and give the inputs and verify the outputs as per the truth table. 
STEP:7 Select the Implementation in the Sources Window and select the required file in the Processes Window. 
STEP:8 Select Check Syntax from the Synthesize XST Process. Double Click in the Floorplan Area/IO/Logic-Post Synthesis process in the User Constraints process group. UCF(User constraint File) is obtained. 
STEP:9 In the Design Object List Window, enter the pin location for each pin in the Loc column Select save from the File menu. 
STEP:10 Double click on the Implement Design and double click on the Generate Programming File to create a bitstream of the design.(.v) file is converted into .bit file here. 
STEP:11 On the board, by giving required input, the LEDs starts to glow light, indicating the output.
STEP:12 Load the Bit file into the SPARTAN 6 FPGA 

# Logic Diagram :

![image](https://github.com/navaneethans/VLSI-LAB-EXP-5/assets/6987778/34ec5d63-2b3b-4511-81ef-99f4572d5869)


# VERILOG CODE:

module fsm(clk,rst,x,z);

input clk,rst,x;

output z;

reg [2:1] ps,ns;

parameter s0=2'b00,s1=2'b01,s2=2'b10,s3=2'b11;

always@(x,posedge clk)

case(ps)

s0:if(x)

ns=s1;

else

ns=s0;

s1:if(x)

ns=s1;

else

ns=s2;

s2:if(x)

ns=s3;

else

ns=s0;

s3:if(x)

ns=s1;

else

ns=s0;

endcase

always@(posedge clk)

if(rst)

ps<=s0;

else

ps=ns;

assign z=(ps==s3);

endmodule
# OUTPUT:

![image](https://github.com/sujitha18b/VLSI-LAB-EXP-5/assets/161813783/e705e273-d12b-4bc3-a910-3d30cf1a059d)

![image](https://github.com/sujitha18b/VLSI-LAB-EXP-5/assets/161813783/04063f06-8cc4-45a3-9737-4dac2a1f5c1b)


# RESULT:
Thus the finite state machine is simulated using VIVADO 2023.1 and the output is verified successfully.



