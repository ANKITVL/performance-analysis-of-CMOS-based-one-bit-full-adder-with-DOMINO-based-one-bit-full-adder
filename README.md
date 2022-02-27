# Performance-analysis-of-CMOS-based-one-bit-full-adder-with-DOMINO-based-one-bit-full-adder
The repository represents the performance analysis of CMOS and DOMINO based one bit full adder.
# Table of Contents
- Intrduction
- CMOS Based Full-Adder
- Domino Based Full-Adder
- Tools Used
- Pre-Layout Schematics and Simulations
- Netlist of the Circuit
- Observations
- Author
- Acknowledgements
- References 
## Introduction
In our VLSI design most efficient things is that the devices are getting portable day by day. So domino logic is on of those technique to helps in improvement in area and high speed logic gate. In this paper basically we designed one bit full adder domino based technique and one bit CMOS based full adder and just compare their speed, power consumption. We give the supply voltage of 1.8V. It was assumed that according to domino logic full adder occupied circuit is 28.57% less area than CMOS based full adder.
## CMOS Based Full-Adder:
In our digital world the one-bit full adder circuit is one of the most widely used building blocks in all data processing and in digial signal processing architectures.In the following we are going to demonstrate the circuit structure and the realization of full adder using CMOS design style.Th expression of full-adder :
                                                              Sum =A⊕B⊕C  Carry= AB+AC+BC
Basically what i am doing that the two above function are realize by first i use carry signal to generate the sum output not by realizing independentl since it helps to reduce the complexity of the hardware. Using that technique total number of transistor used are 28 in which total nMOS is 14 and total pMOS is 14.Below is the circuit diagram diagram helps to understand the functionality of full-adder based on CMOS.

![One bit full-adder using CMOS](https://user-images.githubusercontent.com/94243690/155881437-373592a2-cc88-4500-bbd7-f9b33796248e.png)
## DOMINO Based Full-Adder:
Domino logic is a CMOS based evolution the dynamic logic techniques. There are various advantages of Domino logic like they have a smaller area unlike conventional CMOS logic, parasitic capacitance are smaller in domino logic so it provide high speed of operationand result is glitch free because each gate makes only one transition.It is based on either PMOS or NMOS transistors.In domino logic whenever the precharge happen i.e when clock(CLK)=0 the output node of the dynamic CMOS is precharge to a high logic level and inverter gives the output 0 and whenever CLK=1 then evaluation happens i.e either output goes to ground or remains at high.Below is the circuit diagram diagram helps to understand the functionality of full-adder based on CMOS.

![One bit full-adder using NP DOMINO ](https://user-images.githubusercontent.com/94243690/155881915-988f24ee-9c79-4a26-945e-08caa94b276d.png)
## Tools Used:
**• Synopsys Custom Compiler:**
The Synopsys Custom Compiler™ design environment is a modern solution for full-custom analog, custom digital, and mixed-signal IC design. As the heart of the Synopsys Custom Design Platform, Custom Compiler provides design entry, simulation management and analysis, and custom layout editing features. This tool was used to design the circuit on a transistor level.

**• Synopsys Primewave:**
PrimeWave™ Design Environment is a comprehensive and flexible environment for simulation setup and analysis of analog, RF, mixed-signal design, custom-digital and memory designs within the Synopsys Custom Design Platform. This tool helped in various types of simulations of the above designed circuit.

**• Synopsys 28nm PDK:**
The Synopsys 28nm Process Design Kit(PDK) was used in creation and simulation of the above designed circuit.
## Pre-Layout Schematics and Simulations:
### Schematic of CMOS Based Full-Adder:
![cmos fa](https://user-images.githubusercontent.com/94243690/155883052-9c9bfca4-6557-4eb1-a933-cc93d4d62985.png)
### Schematic of DOMINO Based Full-Adder:
![domino based fa](https://user-images.githubusercontent.com/94243690/155883146-536205c3-ea37-41ba-860d-fc5c5105dc16.png)
### Simulations:

### Transient Analysis
After creating and saving the schematic go to 'Tools' and open 'Primewave' to start the simulation. In the Primewave select the 'model file' i.e the '28nm PDK's .lib file presentin the HSPICE folder. After this select the 'tran' analysis in the analysis window and give the 'Start', 'Stop', and 'Step Size' parameters and save it. Then add the outputs which needs to be plotted by selecting the nets on the schematic.
One other thing we need to keep in mind is that here we have loop for which an initial condition needs to be declared. For that, we have to go to 'Setup -> Convergance aids' and select the net for which we want to set an initial condition.Then go to 'Simulations -> Netlist and Run' to generate a netlist and run the simulation to get the below output.

### CMOS based full-adder:
![cmos fa synopsys](https://user-images.githubusercontent.com/94243690/155883254-74d8b392-2a8a-4f76-8250-f891e9ece038.png)

![cmos vasedfa](https://user-images.githubusercontent.com/94243690/155883294-d525c2d0-b447-43e5-8741-7a575a4c7c06.png)

### DOMINO based full-adder:
![synopsys_domino](https://user-images.githubusercontent.com/94243690/155883402-cd3afd17-a307-4cf6-ac8b-985881383588.png)

![domino fawaveform](https://user-images.githubusercontent.com/94243690/155883438-7f29dcfe-96f0-4e51-914a-ae0c686d889b.png)

## Netlist of the Circuit:

### For CMOS based full-adder:
*  Generated for: PrimeSim
*  Design library name: analog_icdesign
*  Design cell name: cmos_fulladder
*  Design view name: schematic
.lib 'saed32nm.lib' TT

*Custom Compiler Version S-2021.09
*Sat Feb 26 17:16:40 2022

.global vdd gnd!
********************************************************************************
* Library          : analog_icdesign
* Cell             : inverter
* View             : schematic
* View Search List : hspice hspiceD schematic spice veriloga
* View Stop List   : hspice hspiceD
********************************************************************************
.subckt inverter gnd_1 in out vdd_1
xm0 out in vdd_1 vdd_1 p105 w=0.72u l=100n nf=1 m=1
xm1 out in gnd_1 gnd_1 n105 w=0.24u l=100n nf=1 m=1
.ends inverter

********************************************************************************
* Library          : analog_icdesign
* Cell             : cmos_fulladder
* View             : schematic
* View Search List : hspice hspiceD schematic spice veriloga
* View Stop List   : hspice hspiceD
********************************************************************************
xm11 net45 b net47 net47 n105 w=0.1u l=0.03u nf=1 m=1
xm10 net114 a net45 net45 n105 w=0.1u l=0.03u nf=1 m=1
xm9 net114 net110 net104 net104 n105 w=0.1u l=0.03u nf=1 m=1
xm8 net47 c gnd! gnd! n105 w=0.1u l=0.03u nf=1 m=1
xm7 net104 c gnd! gnd! n105 w=0.1u l=0.03u nf=1 m=1
xm6 net104 b gnd! gnd! n105 w=0.1u l=0.03u nf=1 m=1
xm5 net104 a gnd! gnd! n105 w=0.1u l=0.03u nf=1 m=1
xm3 net110 a net15 net15 n105 w=0.1u l=0.03u nf=1 m=1
xm2 net138 a gnd! gnd! n105 w=0.1u l=0.03u nf=1 m=1
xm1 net15 b gnd! gnd! n105 w=0.1u l=0.03u nf=1 m=1
xm0 net110 c net138 net138 n105 w=0.1u l=0.03u nf=1 m=1
xm38 net110 a net150 net150 p105 w=0.1u l=0.03u nf=1 m=1
xm24 gnd! b net138 gnd! p105 w=0.1u l=0.03u nf=1 m=1
xm23 net134 b net101 net101 p105 w=0.1u l=0.03u nf=1 m=1
xm22 net101 c vdd vdd p105 w=0.1u l=0.03u nf=1 m=1
xm25 net114 a net134 net134 p105 w=0.1u l=0.03u nf=1 m=1
xm20 net114 net110 net79 net79 p105 w=0.1u l=0.03u nf=1 m=1
xm19 net79 c vdd vdd p105 w=0.1u l=0.03u nf=1 m=1
xm18 net79 b vdd vdd p105 w=0.1u l=0.03u nf=1 m=1
xm17 net79 a vdd vdd p105 w=0.1u l=0.03u nf=1 m=1
xm16 net132 b vdd vdd p105 w=0.1u l=0.03u nf=1 m=1
xm14 net132 a vdd vdd p105 w=0.1u l=0.03u nf=1 m=1
xm13 net150 b vdd vdd p105 w=0.1u l=0.03u nf=1 m=1
xm12 net110 c net132 net132 p105 w=0.1u l=0.03u nf=1 m=1
xm37 net110 a net150 net150 p105 w=0.1u l=0.03u nf=1 m=1
xi27 gnd! net114 sum vdd inverter
xi26 gnd! net110 carry vdd inverter
v36 vdd gnd! dc=3
v35 b gnd! dc=0 pulse ( 0 3 0 10p 10p 10n 20n )
v34 c gnd! dc=0 pulse ( 0 3 0 10p 10p 50n 100n )
v33 a gnd! dc=0 pulse ( 0 3 0 10p 10p 30n 60n )








.tran '0n' '200n' name=tran

.option primesim_remove_probe_prefix = 0
.probe v(*) i(*) level=1
.probe tran v(a) v(b) v(c) v(carry) v(sum)

.temp 25



.option primesim_output=wdf


.option parhier = LOCAL






.end

### For DOMINO based full-adder:
*  Generated for: PrimeSim
*  Design library name: analog_icdesign
*  Design cell name: domino_fulladder
*  Design view name: schematic
.lib 'saed32nm.lib' TT

*Custom Compiler Version S-2021.09
*Sat Feb 26 17:21:07 2022

.global vdd gnd!
********************************************************************************
* Library          : analog_icdesign
* Cell             : inverter
* View             : schematic
* View Search List : hspice hspiceD schematic spice veriloga
* View Stop List   : hspice hspiceD
********************************************************************************
.subckt inverter gnd_1 in out vdd_1
xm0 out in vdd_1 vdd_1 p105 w=0.72u l=100n nf=1 m=1
xm1 out in gnd_1 gnd_1 n105 w=0.24u l=100n nf=1 m=1
.ends inverter

********************************************************************************
* Library          : analog_icdesign
* Cell             : domino_fulladder
* View             : schematic
* View Search List : hspice hspiceD schematic spice veriloga
* View Stop List   : hspice hspiceD
********************************************************************************
xm19 net73 c net59 net59 n105 w=240n l=100n nf=1 m=1
xm18 net59 phi gnd! gnd! n105 w=240n l=100n nf=1 m=1
xm17 net65 carry_bar net128 net128 n105 w=0.1u l=0.03u nf=1 m=1
xm16 net79 b net73 net73 n105 w=240n l=100n nf=1 m=1
xm15 net128 b net59 net59 n105 w=240n l=100n nf=1 m=1
xm14 net128 a net59 net59 n105 w=240n l=100n nf=1 m=1
xm13 net128 c net59 net59 n105 w=240n l=100n nf=1 m=1
xm12 net65 a net79 net79 n105 w=240n l=100n nf=1 m=1
xm11 net31 phi gnd! gnd! n105 w=240n l=100n nf=1 m=1
xm6 net35 b net31 net31 n105 w=240n l=100n nf=1 m=1
xm7 net39 b net31 net31 n105 w=240n l=100n nf=1 m=1
xm8 net35 a net31 net31 n105 w=240n l=100n nf=1 m=1
xm9 carry_bar c net35 net35 n105 w=240n l=100n nf=1 m=1
xm10 carry_bar a net39 net39 n105 w=240n l=100n nf=1 m=1
xm22 carry_bar phi vdd vdd p105 w=0.72u l=100n nf=1 m=1
xm23 net65 phi vdd vdd p105 w=0.72u l=100n nf=1 m=1
xi25 gnd! net65 sum vdd inverter
xi24 gnd! carry_bar carry vdd inverter
v31 vdd gnd! dc=3
v40 phi gnd! dc=0 pulse ( 3 0 0 10p 10p 40n 80n )
v39 a gnd! dc=0 pulse ( 0 3 0 10p 10p 30n 60n )
v41 c gnd! dc=0 pulse ( 0 3 0 10p 10p 50n 100n )
v37 b gnd! dc=0 pulse ( 0 3 0 10p 10p 10n 20n )








.tran '0n' '200n' name=tran

.option primesim_remove_probe_prefix = 0
.probe v(*) i(*) level=1
.probe tran v(a) v(b) v(c) v(carry) v(sum) v(phi)

.temp 25



.option primesim_output=wdf


.option parhier = LOCAL






.end

## Observations:
![table of performance](https://user-images.githubusercontent.com/94243690/155883946-5cfe31bd-5f7d-44c8-86b7-df7a1bdbcd64.png)
## Author:
• Ankit Vivek, M.Tech(Microelectronics and VLSI design), Motilal Nehru National Institute of Technology, Allahabad,Uttar Pradesh-211004
## Acknowledgements:
- [Cloud Based  Analog IC Design Hackathon](https://pages.github.com/)
- [Synopsys India](https://pages.github.com/)
- [VLSI System Design (VSD) Corp.Pvt.Ltd India](https://pages.github.com/)
## References:
[1]Kamlesh Kukreti, Prashant Kumar, Shivangi Barthwal, Amit Juyal, Alankrita Joshi “Performance analyaisis of full adder based on domino logic technique” 2021 6th International conference on ICICT, Coimbatore, pp.312-316,2021







                              
