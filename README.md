Skip to content
Navigation Menu
STEFFIJOHNBRITTO
JKFLIPFLOP-USING-IF-ELSE

Type / to search
Code
Pull requests
Actions
Projects
Security
Insights
Owner avatar
JKFLIPFLOP-USING-IF-ELSE
Public
forked from naavaneetha/JKFLIPFLOP-USING-IF-ELSE
STEFFIJOHNBRITTO/JKFLIPFLOP-USING-IF-ELSE
Go to file
t
Add file
This branch is 2 commits ahead of naavaneetha/JKFLIPFLOP-USING-IF-ELSE:main.
Folders and files
Name		
Latest commit
STEFFIJOHNBRITTO
STEFFIJOHNBRITTO
Update README.md
e2c0212
 · 
16 hours ago
History
db
EXP7
11 months ago
incremental_db
EXP7
11 months ago
output_files
EXP7
11 months ago
simulation
EXP7
11 months ago
JKFLIPFLOPUSINGIFELSE.qpf
EXP7
11 months ago
JKFLIPFLOPUSINGIFELSE.qsf
EXP7
11 months ago
JKFLIPFLOPUSINGIFELSE.qws
EXP7
11 months ago
JKFLIPFLOPUSINGIFELSE.v
EXP7
11 months ago
JKFLIPFLOPUSINGIFELSE.v.bak
EXP7
11 months ago
LICENSE
Initial commit
11 months ago
README.md
Update README.md
16 hours ago
Waveform1.vwf
EXP7
11 months ago
Repository files navigation
README
License
JKFLIPFLOP-USING-IF-ELSE
AIM:

To implement JK flipflop using verilog and validating their functionality using their functional tables

SOFTWARE REQUIRED:

Quartus prime

THEORY

JK Flip-Flop

JK flip-flop is the modified version of SR flip-flop. It operates with only positive clock transitions or negative clock transitions. The circuit diagram of JK flip-flop is shown in the following figure.

image

This circuit has two inputs J & K and two outputs Qtt & Qtt’. The operation of JK flip-flop is similar to SR flip-flop. Here, we considered the inputs of SR flip-flop as S = J Qtt’ and R = KQtt in order to utilize the modified SR flip-flop for 4 combinations of inputs. The following table shows the state table of JK flip-flop.

image

Here, Qtt & Qt+1t+1 are present state & next state respectively. So, JK flip-flop can be used for one of these four functions such as Hold, Reset, Set & Complement of present state based on the input conditions, when positive transition of clock signal is applied. The following table shows the characteristic table of JK flip-flop. Present Inputs Present State Next State

image

By using three variable K-Map, we can get the simplified expression for next state, Qt+1t+1. Three variable K-Map for next state, Qt+1t+1 is shown in the following figure.

image

The maximum possible groupings of adjacent ones are already shown in the figure. Therefore, the simplified expression for next state Qt+1t+1 is Q(t+1)=JQ(t)′+K′Q(t)Q(t+1)=JQ(t)′+K′Q(t)

Procedure

1.Type the program in Quartus software.

2.Compile and run the program.

3.Generate the RTL schematic and save the logic diagram.

4.Create nodes for inputs and outputs to generate the timing diagram.

5.For different input combinations generate the timing diagram.

PROGRAM

Program for flipflops and verify its truth table in quartus using Verilog programming.

Developed by: R Raihaan ahmed 
RegisterNumber: 24010543

module jk_ff (j, k, clk, rst, q);
  input j, k, clk, rst;
  output reg q;
  always @(posedge clk or posedge rst) begin
    if (rst)
      q <= 0; // Reset the flip-flop
    else if (j == 0 && k == 0)
      q <= q; // No change
    else if (j == 0 && k == 1)
      q <= 0; // Reset
    else if (j == 1 && k == 0)
      q <= 1; // Set
    else if (j == 1 && k == 1)
      q <= ~q; // Toggle
  end
endmodule
RTL LOGIC FOR FLIPFLOPS

Screenshot (79)

TIMING DIGRAMS FOR FLIP FLOPS

Screenshot (80)

RESULTS Implementation of JK flipflop using verilog and validating their functionality using their functional tables is executed and the output is verified successfully.

About
No description, website, or topics provided.
Resources
 Readme
License
 GPL-3.0 license
 Activity
Stars
 0 stars
Watchers
 0 watching
Forks
 0 forks
Report repository
Releases
No releases published
Packages
No packages published
Languages
VHDL
49.2%
 
Stata
18.5%
 
Verilog
15.6%
 
HTML
15.3%
 
Standard ML
1.4%
Footer
© 2024 GitHub, Inc.
Footer navigation
Terms
Privacy
Security
Status
Docs
Contact
Manage cookies
Do not share my personal information
