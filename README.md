# Design of a CMOS Four-Quadrant Analog Multiplier using Gilbert Cell on 28nm CMOS technology

<dl>
  <dd> This repository presents the design of a CMOS Four-Quadrant Analog Multiplier built using a Gilbert Cell. It has been implemented on Synopsys Custom Compiler in 28nm CMOS technology node.
</dl>

## Table of Contents
* [Abstract](https://github.com/B-Kavya-Shruthi/CMOS-Analog-Multiplier-using-Gilbert-Cell/new/main?readme=1#abstract)
* [Tools Used](https://github.com/B-Kavya-Shruthi/CMOS-Analog-Multiplier-using-Gilbert-Cell/new/main?readme=1#tools-used)
* [Gilbert Multiplier Cell](https://github.com/B-Kavya-Shruthi/CMOS-Analog-Multiplier-using-Gilbert-Cell/new/main?readme=1#gilbert-multiplier-cell)
* [Working of a Basic CMOS Analog Multiplier using Gilbert Cell](https://github.com/B-Kavya-Shruthi/CMOS-Analog-Multiplier-using-Gilbert-Cell/new/main?readme=1#working-of-analog-multiplier)
* [Reference Circuit Diagram](https://github.com/B-Kavya-Shruthi/CMOS-Analog-Multiplier-using-Gilbert-Cell/new/main?readme=1#reference-circuit-diagram)
* [Design](https://github.com/B-Kavya-Shruthi/CMOS-Analog-Multiplier-using-Gilbert-Cell/new/main?readme=1#design)
* [Author](https://github.com/B-Kavya-Shruthi/CMOS-Analog-Multiplier-using-Gilbert-Cell/new/main?readme=1#author)
* [Acknowledgements](https://github.com/B-Kavya-Shruthi/CMOS-Analog-Multiplier-using-Gilbert-Cell/new/main?readme=1#acknowledgements)
* [References](https://github.com/B-Kavya-Shruthi/CMOS-Analog-Multiplier-using-Gilbert-Cell/new/main?readme=1#references)

## Abstract

<dl> 
  <dd> As the demand for portable electronics is increasing, CMOS analog multipliers operating with low supply voltages and low power consumption are crucial.
       A 4-quadrant analog multiplier is an important building block of many applications in modern analog VLSI signal and information processing [4]. 
       In this repository, the basic design of a 4-quadrant analog multiplier using Gilbert cell on 28nm CMOS technology is discussed and implemented.      
</dl>

## Tools Used

1. Synosys Custom Compiler
2. Synopsys 28nm PDK

## Gilbert Multiplier Cell

<dl>
  <dd>
    A Gilbert Multiplier Cell consists of two differential pairs whose gains are varied by two respective control voltages (Vcont1 and Vcont2) as given in Fig 1.
    The two control voltages define the respective tail currents and amplify the input by opposite gains.
    The gain can be continously varied from a negative value |Vout1/Vin| to a positive value |Vout2/Vin|, which are give by:
  </dd>
  <p align="center">
  <img src="https://user-images.githubusercontent.com/82320002/156306341-38a1154a-8540-4ce6-9926-7e87290f5e68.png" width=400 height=50> <br />
  <img src="https://user-images.githubusercontent.com/82320002/156306397-10c570b0-1745-4bfa-bd0a-35537eabdfd0.png" width=400 height=50>
  </p>
  <dd>
  where, gm denotes the transconductance of each transistor in equilibrium.[6]
    
  <p align="center">
  <br /> <img src="https://user-images.githubusercontent.com/82320002/156313113-a82c08be-7736-43a5-b9df-2641de0e2638.png")
  </p>
  <p align="center">
  Fig 1. Two Stages of Differential Pairs providing Variable Gain [6]
  </p>
                                                                                                                    
  <dd>
  In the circuit in Fig.1, a control differential pair can be used to vary currents I1 and I2 in opposite directions such that the gain of the amplifier changes monotonically. 
  In a cascode structure as given in Fig.2, the two differential pairs M1-M2 and M3-M4 are "stacked" on top of the control differential pair. 
  In arriving at the Gilbert cell topology, we opted to vary the gain of each differential pair through its tail current, thereby applying the control voltage to the bottom pair and the input signal to the top pairs.
  Vout is obtained by shorting the corresponding drain terminals to sum the currents and subsequently produce the output voltage.[4]
  </dd>
  
  <p align="center">
  <img src="https://user-images.githubusercontent.com/82320002/156316242-9d97c131-548e-4826-98f2-de2567f8b7b5.png">
  </p>
  <p align="center">
  Fig 2. Gilbert Multiplier Cell [6]
  </p>
  
## Working of a Basic CMOS Analog Multiplier using Gilbert Cell
  
  <p align="center">
  <img src="https://user-images.githubusercontent.com/82320002/156323698-3c3463dc-ba8d-4bd1-9ce9-d8bb96b317bc.png">
  </p>
  <p align="center">
  Fig 3. Complete Circuit Diagram of a Basic CMOS Analog Multiplier [3]
  </p>
<p>
    A CMOS analog multiplier consists of current mirrors and differential pairs. The drain current ID of an NMOS device can be described by
    <p align="center">
    <img src="https://user-images.githubusercontent.com/82320002/156320716-c0c08e96-c30a-42f4-9248-18cddd0b8c20.png"> <br />
    </p> 
  where, K is the transconductance parameter, Vgs is the gate-to-source voltage and VT is the threshold voltage, respectively. Assume that all the MOS devices in Fig.3
  were biased in saturation with their sources connected to the substrate. The currents I1, I2, I3 and I4 can be expressed as
  <p align="center">
    <br /> <img src="https://user-images.githubusercontent.com/82320002/156321784-fd35bb28-9bb9-469b-aa94-81461209468c.png"> <br />
    </p>
where K is the transconductance parameter of the devices M1-M6 and M9-M12. Let the aspect ratio of M14 (also Ml7) be twofold that of M13 (also M18). 
  The aspect ratios of M15 and M16 are equal. The current mirrors consisting of Ml3-Ml6 will force the current Ia (also Ib) to zero. The current I5 that flows through M5 is given by 
<p align="center">
    <img src="https://user-images.githubusercontent.com/82320002/156321867-838b86ad-39aa-402f-b8bc-d689e6e7ace6.png"> <br />
    </p>
where K5 is the transconductance parameter of M5. 
  The same current I5 that flows through M7 can be described as 
  <p align="center">
    <br /> <img src="https://user-images.githubusercontent.com/82320002/156321952-5ad870c7-1290-469f-947f-52037266f854.png"> <br />
    </p>
From the above equations, the output current Io can then be defined and given as 
    <p align="center">
    <br /> <img src="https://user-images.githubusercontent.com/82320002/156322044-2422b074-3247-4ec4-abce-209b0d9cb9c9.png"> <br />
  </p>
The output current Io can be extracted by using current mirrors or be converted into an output voltage by using resistors. [3]
  
## Reference Circuit Diagram
  <p align="center">
  <img src="https://user-images.githubusercontent.com/82320002/156317324-1ae2b722-ca76-4a00-acd2-af87f7e86f9c.png">
  </p>
  <p align="center">
  Fig. Reference Circuit used to design CMOS Analog Multiplier [2]
  </p>
    
## Design
  
  <p align="center">
  <img src="https://github.com/B-Kavya-Shruthi/CMOS-Analog-Multiplier-using-Gilbert-Cell/blob/main/Images/CMOS%20Analog%20Multiplier%20Circuit%20Schematic.PNG?raw=true">
  </p>
  <p align="center">
  Fig. CMOS Analog Multiplier Circuit Schematic
  </p>

  <p align="center">
  <img src="https://github.com/B-Kavya-Shruthi/CMOS-Analog-Multiplier-using-Gilbert-Cell/blob/main/Images/CMOS%20Analog%20Multiplier%20Symbol.PNG?raw=true">
  </p>
  <p align="center">
  Fig. CMOS Analog Multiplier Symbol
  </p>
  
  <p align="center">
  <img src="https://github.com/B-Kavya-Shruthi/CMOS-Analog-Multiplier-using-Gilbert-Cell/blob/main/Images/CMOS%20Analog%20Multiplier%20Simulation%20Schematic.PNG?raw=true">
  </p>
  <p align="center">
  Fig. CMOS Analog Multiplier Testbench Schematic
  </p>
  
  Note: Unfortunately, I obtained a spiky signal in the output waveform, and was unable to make corrections within the time constraints. Hence, I have not attached the screenshots of the simulation waveforms.
       
## Author
  
  B. Kavya Shruthi, B.Tech (Electronics and Communication), SRM Institute of Science and Technology, Kattankulathur
  
## Acknowledgements
* Kunal Ghosh, Co-founder, VSD Corp. Pvt. Ltd.
* Synopsys India
* IIT Hyderabad
* Cloud Based Analog IC Design Hackathon
* Sameer Durgoji, NIT Karnataka
* Chinmay panda, IIT Hyderabad
  
## References

1. G. Lee, H. Choi, Y. Yu, T. Kim, J. Kim and D. Kim, "Design of A CMOS Analog Multiplier using Gilbert Cell," 1999. [online] Koreascience.or.kr. Available at: <https://www.koreascience.or.kr/article/JAKO199911921383249.pdf> [Accessed 19 February 2022].
2. S. C. Qin and R. L. Geiger, “A +-5V CMOS analog multiplier," IEEE J. Solid-state Circuits, vol. SC-22, no. 6, pp. 1143-1146, Dec. 1987.
3. S. I. Liu, C. C. Chang and Y. S. Hwang, "New CMOS Four-Quadrant Multiplier and Squarer Circuits," Analog Integrated Circuits and Signal Processing, vol. 9, pp.257-263, 1996.
4. N. Khachab and M. Ismail, "A nonlinear CMOS analog cell for VLSI signal and information processing," IEEE J.Solid-state Circuits, vol. 26, no. 11, pp. 1698-1699, Nov. 1991.
5. B. Gilbert, “A Precise Four-Quadrant Multiplier with Subnanosecond Response,” IEEE J. Solid-State Circuits, vol. SC-3, pp. 365–373, Dec. 1968
6. B. Razavi, Design of analog CMOS integrated circuits. McGraw-Hill Education: New York, 2017.


    
