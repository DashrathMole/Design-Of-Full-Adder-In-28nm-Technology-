# Design-Of-1Bit-Full-Adder-In-28nm-Technology-

In this repository I designed Full adder in 28nm technology using Synopsys Custom Compiler.

# Table Of Content <br/>
* [Abstract](https://github.com/DashrathMole/Design-Of-Full-Adder/edit/main/README.md#abstract-)<br/>
* [Tool used](https://github.com/DashrathMole/Design-Of-Full-Adder/edit/main/README.md#tool-used)<br/>
* [Design-Of-Full-Adder](https://github.com/DashrathMole/Design-Of-Full-Adder/edit/main/README.md#Design-Of-Full-Adder)<br/>
* [Testbench schematics ](https://github.com/DashrathMole/Design-Of-Full-Adder/edit/main/README.md#Testbench-schematics)<br/>
* [Simulation result](https://github.com/DashrathMole/Design-Of-Full-Adder-In-28nm-Technology/edit/main/README.md#simulation-result)<br/>
* [Total Transistor ](https://github.com/DashrathMole/Design-Of-Full-Adder-In-28nm-Technology/blob/main/README.md#transistor-count-for-each-block)   <br/>
* [Netlist](https://github.com/DashrathMole/Design-Of-Full-Adder/edit/main/README.md#netlist)<br/>
* [Author](https://github.com/DashrathMole/Design-Of-Full-Adder/edit/main/README.md#author)<br/>
* [Acknowledgements](https://github.com/DashrathMole/Design-Of-Full-Adder/edit/main/README.md#acknowledgements-)<br/>
* [Reference](https://github.com/DashrathMole/Design-Of-Full-Adder/edit/main/README.md#reference-)<br/>
# Abstract <br/>
I designed and simulated a low power one bit, full adder circuits namely Novel 10T the adder.  The one bit Novel 10T,XOR/XNOR function technique has been used for the generation of full adders. The proposed design successfully works with the buffering circuit in the full adder design. All full adder circuits are design and analyse using 28nm Technology 1.8volt supply voltage. Due to lesser length requirement in the individual transistor, all the design of adders require lesser area as compared to existing design results in the tables. There is also improvement in terms of power, delay and power-delay product. Using  this 1bit  full adder we can design types of adder circuits 
# Tool used<br/>
*Synopsys Custom Compiler*:  The Synopsys Custom Compiler™ design environment is a modern solution for full-custom analog, custom digital, and mixed-signal IC design. As the heart of the Synopsys Custom Design Platform, Custom Compiler provides design entry, simulation management and analysis, and custom layout editing features. This tool was used to design the circuit on a transistor level.<br/>
*Synopsys Primewave*:  PrimeWave™ Design Environment is a comprehensive and flexible environment for simulation setup and analysis of analog, RF, mixed-signal design, custom-digital and memory designs within the Synopsys Custom Design Platform. This tool helped in various types of simulations of the above designed circuit.<br/>
*Synopsys 28nm PDK*:  The Synopsys 28nm Process Design Kit(PDK) was used in creation and simulation of the above circuit design.<br/>
# Full adder  <br/>
FA_Schematics<br/>
![FA_Schematics](https://user-images.githubusercontent.com/100442412/156121964-b53c4dbf-d20e-4569-bbd4-8c33eb510459.png)
FA_Symbol<br/>
![Screenshot(1123)](https://user-images.githubusercontent.com/100442412/156142944-2648b626-f11c-49f7-96c5-72d2e5414c44.png)
# Testbench schematics<br/>
![Testbench schematics](https://user-images.githubusercontent.com/100442412/156143060-a6331bdf-723a-44c0-a4ab-39ac6cf8f1d0.png)
# Simulation result<br/>
![waveform](https://user-images.githubusercontent.com/100442412/156143133-e64dc6e6-280b-49ae-8b29-63d5800247f9.png)
# Total transistor count<br/>
Transistor count-10
# Netlist<br/>
*  Generated for: PrimeSim
*  Design library name: 1_bit_FullAdder
*  Design cell name: 1_bit_FA_tb
*  Design view name: schematic
  .lib 'saed32nm.lib' TT

*Custom Compiler Version S-2021.09
*Tue Mar  1 09:56:36 2022

.global gnd!
********************************************************************************
* Library          : 1_bit_FullAdder
* Cell             : 1_bit_FA
* View             : schematic
* View Search List : hspice hspiceD schematic spice veriloga
* View Stop List   : hspice hspiceD
********************************************************************************
.subckt _1_bit_fa vdd vss a b cin cout sum

xm9 net37 net40 vss vss n105 w=0.1u l=0.03u nf=1 m=1</br>
xm8 net40 b net45 vss n105 w=0.1u l=0.03u nf=1 m=1 </br>
xm7 net40 a b vss n105 w=0.1u l=0.03u nf=1 m=1</br>
xm1 cout net37 cin vss n105 w=0.1u l=0.03u nf=1 m=1</br>
xm0 net40 cin sum vss n105 w=0.1u l=0.03u nf=1 m=1</br>
xm6 net40 net45 net25 vdd p105 w=0.1u l=0.03u nf=1 m=1</br>
xm5 net25 b vdd vdd p105 w=0.1u l=0.03u nf=1 m=1</br>
xm4 net37 net40 vdd vdd p105 w=0.1u l=0.03u nf=1 m=1</br>
xm3 cout net37 net45 vdd p105 w=0.1u l=0.03u nf=1 m=1</br>
xm2 net37 cin sum vdd p105 w=0.1u l=0.03u nf=1 m=1</br>
.ends _1_bit_fa

********************************************************************************
* Library          : 1_bit_FullAdder
* Cell             : 1_bit_FA_tb
* View             : schematic
* View Search List : hspice hspiceD schematic spice veriloga
* View Stop List   : hspice hspiceD
********************************************************************************
xi0 net8 gnd! in1 in2 in3 out carry _1_bit_fa</br
v1 net8 gnd! dc=1.8</br>
v7 in3 gnd! dc=0 pulse ( 0 1 0 0.1u 0.1u 12u 24u )</br>
v6 in2 gnd! dc=0 pulse ( 0 1 0 0.1u 0.1u 6u 12u )</br>
v5 in1 gnd! dc=0 pulse ( 0 1 0 0.1u 0.1u 3u 6u )</br>

.tran '1u' '30' name=tran

.option primesim_remove_probe_prefix = 0</br>
.probe v(*) i(*) level=1</br>
.probe tran v(out) v(in1) v(in2) v(in3) v(carry)</br>

.temp 25

.option primesim_output=wdf


.option parhier = LOCAL

.end
# Author<br/>
Dashrath P Mole, Third Year Electronics at Walchand College of Engineering Sangli,Maharashta,India.
# Acknowledgements <br/>
[Kunal Ghosh, Co-founder, VSD Corp. Pvt. Ltd.](https://www.linkedin.com/in/kunal-ghosh-vlsisystemdesign-com-28084836/)<br/>
[Cloud Based Analog IC Design Hackathon](https://www.iith.ac.in/events/2022/02/15/Cloud-Based-Analog-IC-Design-Hackathon/)<br/>
[Synopsys India](https://www.synopsys.com/)<br/>
# Reference <br/>
[1]	Neil H. E. Weste, David Harris and Ayan Banerjee, “CMOS VLSI Design, a Circuit and System Perspective”, 
    Third Edition, Pearson Education, Inc., (2005).
   
 [2]	Sung-Mo (Steve) Kang and Yusuf Leblebici, “CMOS 
      Digital Integrated Circuits Analysis & Design”, Tata McGraw-Hill, (2005). 
      
[3]	Manoj Kumar, Sandeep K. Arya, and Sujata Pandey, “A New Low Power Single Bit Full Adder Design with 14 Transistors using Novel 3 Transistors XOR Gate”,

[4] Udemy.com (Kunal Ghosh Sir Lectures).





