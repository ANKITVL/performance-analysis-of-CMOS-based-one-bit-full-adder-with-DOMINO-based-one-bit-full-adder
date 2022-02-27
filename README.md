# Performance-analysis-of-CMOS-based-one-bit-full-adder-with-DOMINO-based-one-bit-full-adder
The repository represents the performance analysis of CMOS and DOMINO based one bit full adder.
# Table of Contents
## Introduction
In our VLSI design most efficient things is that the devices are getting portable day by day. So domino logic is on of those technique to helps in improvement in area and high speed logic gate. In this paper basically we designed one bit full adder domino based technique and one bit CMOS based full adder and just compare their speed, power consumption. We give the supply voltage of 1.8V. It was assumed that according to domino logic full adder occupied circuit is 28.57% less area than CMOS based full adder.
## CMOS Based Full-Adder
In our digital world the one-bit full adder circuit is one of the most widely used building blocks in all data processing and in digial signal processing architectures.In the following we are going to demonstrate the circuit structure and the realization of full adder using CMOS design style.Th expression of full-adder :
                                                              Sum =A⊕B⊕C  Carry= AB+AC+BC
Basically what i am doing that the two above function are realize by first i use carry signal to generate the sum output not by realizing independentl since it helps to reduce the complexity of the hardware. Using that technique total number of transistor used are 28 in which total nMOS is 14 and total pMOS is 14.Below is the circuit diagram diagram helps to understand the functionality of full-adder based on CMOS.

![One bit full-adder using CMOS](https://user-images.githubusercontent.com/94243690/155881437-373592a2-cc88-4500-bbd7-f9b33796248e.png)
## DOMINO Based Full-Adder
Domino logic is a CMOS based evolution the dynamic logic techniques. There are various advantages of Domino logic like they have a smaller area unlike conventional CMOS logic, parasitic capacitance are smaller in domino logic so it provide high speed of operationand result is glitch free because each gate makes only one transition.It is based on either PMOS or NMOS transistors.In domino logic whenever the precharge happen i.e when clock(CLK)=0 the output node of the dynamic CMOS is precharge to a high logic level and inverter gives the output 0 and whenever CLK=1 then evaluation happens i.e either output goes to ground or remains at high.Below is the circuit diagram diagram helps to understand the functionality of full-adder based on CMOS.

![One bit full-adder using NP DOMINO ](https://user-images.githubusercontent.com/94243690/155881915-988f24ee-9c79-4a26-945e-08caa94b276d.png)
