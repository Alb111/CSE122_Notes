## Moore's Law and Scaling
- traditionally as transitiors shrunk there power and size went down. This meant as generations went to we were able to make chips with more transistors and more effiecent power (this is Dennard's Scaling)
- However current shrink transistors is becoming more impossible do to lightography limitations and physics limitations (to small for electors to flow/block)
- we cant add more transitors to chips as that creates to much heat / need for power
- since we cant just realy on faster/smaller transistors for speed we are starting to do multi core archetecture and stuff like stack transistors vertically and redesign transistors to use finfets and stuff like that

## Design Flow

**Front End**
1) [HDL design](#What-is-a-HDL)
2) [Systhesis](#Systhesis)
3) [Static Timing Analysis](#Static-Timing-Analysis)

**Back End**
1) [Floorplanning](#Floorplanning)
2) [Placement](#Placement)
3) [Clock Systhesis](#Clock-Systhesis)
4) [Routing](#Routing)
6) [DRC/LVS](#DRC/LVS)
5) [OPC/RET](#OPC/RET)

## What is a HDL
- HDL: Hardware Design Languauge
- a language to design hardware, at the begining it was only used for logic simulation now it used systhesize logic into hardware primatives (think ands and ors or fpga primatives)
- Examples of HDLs: Verilog, VHDL

## Systhesis
- converts HDL to more effiecent logic and then logic libary gates (the and, nor, xor gates manufracturor provides)
- logic is omptimized with a 2 level K-map

## Static Timing Analysis
- Ensures setup and hold times are met
  - setup time -> is singal stable for long enough before clock edge (did I get datat on time)
  - hold time -> is singal stable for long enough after clock edge (did I hold the data I send for long enough)

## Floorplanning
- Given where floorplanning placed the different modules and io how can we draw the wires that connect everything
- Assigns where power pads go

## Placement 
- places all the small cells inside the florrplanned regions, their placement is optimized for timing, wirelength, and power

## Clock Sythesis
- route wires for clock everwhere it needs to go
- place buffers and other stuff so we can effect the following:
  - skew: difference between clk arrival times at different registers
  - power: clk networks cosume power, how can we reduce this while timing works
  - slew: how square clk is, clks with slow slew cause uncertainity and delay 
  - yield: percent of chips that work after tapeout

## Routing
- once everything is placed draw the wires that connect everything and add buffers and stuff for timing

## DRC/LVS
- Checks that a design meets the design rules for the fab

## OPC/RET
- adjust the masks so that they work in lithograpthy

