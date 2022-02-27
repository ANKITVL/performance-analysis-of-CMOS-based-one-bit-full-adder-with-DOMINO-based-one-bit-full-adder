# Performance-analysis-of-CMOS-based-one-bit-full-adder-with-DOMINO-based-one-bit-full-adder
The repository represents the performance analysis of CMOS and DOMINO based one bit full adder using Synopsis Custom Compiler on 28nm CMOS Technology.
# Table of Contents
- Introduction
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

![FA](https://user-images.githubusercontent.com/94243690/155888747-0a4e8643-b282-414d-ac9c-b38eff90e61c.png)
###### Fig 1: CMOS based full-adder circut

## DOMINO Based Full-Adder:
Domino logic is a CMOS based evolution the dynamic logic techniques. There are various advantages of Domino logic like they have a smaller area unlike conventional CMOS logic, parasitic capacitance are smaller in domino logic so it provide high speed of operationand result is glitch free because each gate makes only one transition.It is based on either PMOS or NMOS transistors.In domino logic whenever the precharge happen i.e when clock(CLK)=0 the output node of the dynamic CMOS is precharge to a high logic level and inverter gives the output 0 and whenever CLK=1 then evaluation happens i.e either output goes to ground or remains at high.Below is the circuit diagram diagram helps to understand the functionality of full-adder based on CMOS.

![dominofa](https://user-images.githubusercontent.com/94243690/155888759-ea3c67c7-d65e-4d32-96fa-a5d85e69dff1.png)
###### Fig 2: DOMINO based full-adder circuit

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
###### Fig 3: Schematic diagram of CMOS based full-adder
### Schematic of DOMINO Based Full-Adder:
![domino based fa](https://user-images.githubusercontent.com/94243690/155883146-536205c3-ea37-41ba-860d-fc5c5105dc16.png)
###### Fig 4: Schematic diagram of DOMINO based full-adder
### Simulations:

### Transient Analysis
After creating and saving the schematic go to 'Tools' and open 'Primewave' to start the simulation. In the Primewave select the 'model file' i.e the '28nm PDK's .lib file presentin the HSPICE folder. After this select the 'tran' analysis in the analysis window and give the 'Start', 'Stop', and 'Step Size' parameters and save it. Then add the outputs which needs to be plotted by selecting the nets on the schematic.
One other thing we need to keep in mind is that here we have loop for which an initial condition needs to be declared. For that, we have to go to 'Setup -> Convergance aids' and select the net for which we want to set an initial condition.Then go to 'Simulations -> Netlist and Run' to generate a netlist and run the simulation to get the below output.

### CMOS based full-adder:
![cmos fa synopsys](https://user-images.githubusercontent.com/94243690/155883254-74d8b392-2a8a-4f76-8250-f891e9ece038.png)
###### Fig 5: Overview of Transient analysis for CMOS
![cmos vasedfa](https://user-images.githubusercontent.com/94243690/155883294-d525c2d0-b447-43e5-8741-7a575a4c7c06.png)
###### Fig 6: Transient analysis of CMOS based full-adder

### DOMINO based full-adder:
![synopsys_domino](https://user-images.githubusercontent.com/94243690/155883402-cd3afd17-a307-4cf6-ac8b-985881383588.png)
###### Fig 7: Overview of Transient analysis for DOMINO
![domino fawaveform](https://user-images.githubusercontent.com/94243690/155883438-7f29dcfe-96f0-4e51-914a-ae0c686d889b.png)
###### Fig 8: Transient analysis of DOMINO based full-adder

## Netlist of the Circuit:
### For CMOS based Full-Adder:
https://github.com/ANKITVL/performance-analysis-of-CMOS-based-one-bit-full-adder-with-DOMINO-based-one-bit-full-adder/blob/main/CMOS%20BASED%20FA%20NETLIST.txt
### For DOMINO based Full-Adder: 
https://github.com/ANKITVL/performance-analysis-of-CMOS-based-one-bit-full-adder-with-DOMINO-based-one-bit-full-adder/blob/main/DOMINO%20BASED%20FA%20NETLIST.txt

## Observations:
###### Table No.1: Performance parameter
![table of performance](https://user-images.githubusercontent.com/94243690/155883946-5cfe31bd-5f7d-44c8-86b7-df7a1bdbcd64.png)
## Author:
• Ankit Vivek, M.Tech(Microelectronics and VLSI design), Motilal Nehru National Institute of Technology, Allahabad,Uttar Pradesh-211004
## Acknowledgements:
- [Cloud Based  Analog IC Design Hackathon](https://pages.github.com/)
- [Synopsys India](https://pages.github.com/)
- [VLSI System Design (VSD) Corp.Pvt.Ltd India](https://pages.github.com/)
## References:
[1]Kamlesh Kukreti, Prashant Kumar, Shivangi Barthwal, Amit Juyal, Alankrita Joshi “Performance analyaisis of full adder based on domino logic technique” 2021 6th International conference on ICICT, Coimbatore, pp.312-316,2021







                              
