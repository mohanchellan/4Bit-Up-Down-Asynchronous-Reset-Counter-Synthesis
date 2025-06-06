# 4Bit-Up-Down-Asynchronous-Reset-Counter-Synthesis

## Aim:

Synthesize 4Bit-Up-Down-Asynchronous-Reset-Counter design using Constraints and analyse reports, Timing, area and Power.

## Tool Required:

Functional Simulation: Incisive Simulator (ncvlog, ncelab, ncsim)

Synthesis: Genus

### Step 1: Getting Started

Synthesis requires three files as follows,

◦ Liberty Files (.lib)

◦ Verilog/VHDL Files (.v or .vhdl or .vhd)

◦ SDC (Synopsis Design Constraint) File (.sdc)

 ### Step 2 : Creating an SDC File

•	In your terminal type “gedit input_constraints.sdc” to create an SDC File if you do not have one.

•	The SDC File must contain the following commands;

create_clock -name clk -period 2 -waveform {0 1} [get_ports "clk"]

set_clock_transition -rise 0.1 [get_clocks "clk"]

set_clock_transition -fall 0.1 [get_clocks "clk"]

set_clock_uncertainty 0.01 [get_ports "clk"]

set_input_delay -max 0.8 [get_ports "rst"] -clock [get_clocks "clk"]

set_output_delay -max 0.8 [get_ports "count"] -clock [get_clocks "clk"]

i→ Creates a Clock named “clk” with Time Period 2ns and On Time from t=0 to t=1.

ii, iii → Sets Clock Rise and Fall time to 100ps.

iv → Sets Clock Uncertainty to 10ps.

v, vi → Sets the maximum limit for I/O port delay to 1ps.

### Step 3 : Performing Synthesis

The Liberty files are present in the library path,

• The Available technology nodes are 180nm ,90nm and 45nm.

• In the terminal, initialise the tools with the following commands if a new terminal is being
used.

◦ csh

◦ source /cadence/install/cshrc

• The tool used for Synthesis is “Genus”. Hence, type “genus -gui” to open the tool.

• Genus Script file with .tcl file Extension commands are executed one by one to synthesize the netlist.

#### Synthesis RTL Schematic :

![de6d18a8-e6e7-4cae-9653-df6eea2b3eb0](https://github.com/user-attachments/assets/ac564a52-5fc0-4a5f-9a4c-495ff5b4a0a8)

#### Area report:
![63cf774a-a83b-430f-82ec-90d522e8a05e](https://github.com/user-attachments/assets/cc6cf22e-f867-4dae-b491-39a5c5615c74)

#### Power Report:
![719b34ef-dd85-40c1-baa8-31e66260af13](https://github.com/user-attachments/assets/80e67c8c-9d43-4e9f-a10d-048812ff0ae3)

#### Timing Report: 
![e906665d-9a29-43ac-9d4f-2858daf0b6bc](https://github.com/user-attachments/assets/d5637193-9c23-48ed-923f-beb25df8c060)

#### Result: 

The generic netlist has been created, and area, power, and timing reports have been tabulated and generated using Genus.





