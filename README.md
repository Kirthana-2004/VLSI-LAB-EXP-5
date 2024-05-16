# VLSI-LAB-EXP-5
SIMULATION AND IMPLEMENTATION OF FINITE STATE MACHINE

AIM: To simulate and synthesis finite state machine using Vivado 2023.1.

**APPARATUS REQUIRED: **
Vivado 2023.1.

Spartan6 FPGA

**PROCEDURE: **
Open Vivado: Launch Xilinx Vivado software on your computer.

Create a New Project: Click on "Create Project" from the welcome page or navigate through "File" > "Project" > "New".

Project Settings: Follow the prompts to set up your project. Specify the project name, location, and select RTL project type.

Add Design Files: Add your Verilog design files to the project. You can do this by right-clicking on "Design Sources" in the Sources window, then selecting "Add Sources". Choose your Verilog files from the file browser.

Specify Simulation Settings: Go to "Simulation" > "Simulation Settings". Choose your simulation language (Verilog in this case) and simulation tool (Vivado Simulator).

Run Simulation: Go to "Flow" > "Run Simulation" > "Run Behavioral Simulation". This will launch the Vivado Simulator and compile your design for simulation.

Set Simulation Time: In the Vivado Simulator window, set the simulation time if it's not set automatically. This determines how long the simulation will run.

Run Simulation: Start the simulation by clicking on the "Run" button in the simulation window.

View Results: After the simulation completes, you can view waveforms, debug signals, and analyze the behavior of your design.

Logic Diagram :

![image](https://github.com/navaneethans/VLSI-LAB-EXP-5/assets/6987778/34ec5d63-2b3b-4511-81ef-99f4572d5869)


VERILOG CODE:
~~~
module fsm_moore( clk, rst, inp, outp);

input clk, rst, inp;

output outp;

reg [1:0] state;

reg outp;

always @(posedge clk, posedge rst)

begin

if(rst)

state<=2'b00;

else

begin

case(state)

2'b00:

begin

if(inp) state <=2'b01;



else state <=2'b10;
end

2'b01:

begin

if (inp) state <=2'b11;
else state<=2'b10;
end

2'b10:
begin
if (inp) state<=2'b01;
else state <=2'b11;
end

2'b11:

begin

if (inp) state <=2'b01;
else state <=2'b10;

end

endcase

end

end

always @(posedge clk, posedge rst)

begin

if(rst)

outp <= 0;

else if(state == 2'b11)

outp <= 1;

else outp<= 0;

end

endmodule

~~~

OUTPUT:
![image](https://github.com/Kirthana-2004/VLSI-LAB-EXP-5/assets/144320880/5088245d-ef25-4b22-8c50-1f66e35b810e)
![image](https://github.com/Kirthana-2004/VLSI-LAB-EXP-5/assets/144320880/f3947423-9936-4b50-8d7d-21a4404fb14c)



RESULT: Simulation And Synthesis Finite State Machine is Successfully Verified using Vivado Software.



