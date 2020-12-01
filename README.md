# Design-Verification-of-AMBA-APB-Protocol

## Table of Content
 - [Introduction of AMBA](https://github.com/suvam98/Design-Verification-of-AMBA-APB-Protocol#introduction-of-amba)
 - [Design principles](https://github.com/suvam98/Design-Verification-of-AMBA-APB-Protocol#design-principles)
 - [AMBA Bus specification](https://github.com/suvam98/Design-Verification-of-AMBA-APB-Protocol#amba-bus--specification)
   * [Types of AMBA Bus](https://github.com/suvam98/Design-Verification-of-AMBA-APB-Protocol#types-of-amba-bus)
   * [AMBA AHB](https://github.com/suvam98/Design-Verification-of-AMBA-APB-Protocol#amba-ahb)
   * [AMBA ASB](https://github.com/suvam98/Design-Verification-of-AMBA-APB-Protocol#amba-asb)
 - [Advance Peripheral Bus](https://github.com/suvam98/Design-Verification-of-AMBA-APB-Protocol#advance-peripheral-bus)
   * [APB Block Diagram]()
   * [Signal Descriptions of APB]()  
 
 ## Introduction of AMBA
 - Advanced Micro controller Bus Architecture (AMBA) is an open-standard that outlines how to connect and manage the different components or blocks within an SoC.

 - These designs typically have one or more micro controllers or microprocessors along with several other components — internal memory or external memory bridge, DSP, DMA, accelerators and various other peripherals like USB, UART, PCIE, I2C etc — all integrated on a single chip.  

 - Today, AMBA is widely used on a range of ASIC and SoC parts including applications processors used in modern portable mobile devices like smartphones. 

 AMBA was introduced by ARM in 1996. The first AMBA buses were the Advanced System Bus (ASB) and the Advanced Peripheral Bus (APB). 

 In its second version, AMBA 2 in 1999, ARM added AMBA High-performance Bus (AHB) that is a single clock-edge protocol.
 
 In 2003, ARM introduced the third generation, AMBA 3, including Advanced eXtensible Interface (AXI) to reach even higher performance interconnect and the Advanced Trace Bus (ATB) as part of the CoreSight on-chip debug and trace solution. 

 In 2010 the AMBA 4 specifications were introduced starting with AMBA 4 AXI4, then in 2011[2] extending system-wide coherency with AMBA 4 AXI Coherency Extensions (ACE). 

 In 2013[3] the AMBA 5 Coherent Hub Interface (CHI) specification was introduced, with a re-designed high-speed transport layer and features designed to reduce congestion.

 ## Design principles
 An important aspect of an SoC is not only which components or blocks it houses, but also how they interconnect. AMBA is a solution for the blocks to interface with each other.

 ## AMBA Bus  specification
 - An AMBA-based microcontroller typically consists of a high-performance system backbone bus (AMBA AHB or AMBA ASB), able to sustain the external memory bandwidth, on which the CPU, on-chip memory and other Direct Memory Access (DMA) devices reside. 
 - This bus provides a high-bandwidth interface between the elements that are involved in the majority of transfers. Also located on the highperformance bus is a bridge to the lower bandwidth APB, where most of the peripheral devices in the system are located (see figure).

 ![Untitled](https://user-images.githubusercontent.com/69890373/100754414-149f3a80-3411-11eb-98c5-e37e8dae5241.png)

 - AMBA is development of embedded microcontroller products with one or more CPUs or signal processors.
 - This is highly reusable peripheral appropriate for full-custom, standard cell and gate array technologies.
 - It provides a road-map for advanced cached CPU cores and the development of peripheral libraries to minimize the silicon infrastructure required to support efficient on-chip.

 ### Types of AMBA Bus
 Five interfaces are defined within the AMBA specification:

 - Advanced system bus (ASB)
 - Advanced peripheral bus (APB)
 - Advanced high-performance bus (AHB)
 - Advanced extensible interface (AXI)
 - Advanced trace bus (ATB)

 ### AMBA AHB
 Advanced High performance bus (AHB) is made for address the requirements of high-performance synthesizable designs. AMBA AHB is a new level of bus for the APB and implements the features high clock frequency systems including:

 - burst transfers
 - split transactions
 - Single cycle bus master handover
 - Single clock edge operation
 - Wider data bus configurations (64/128 bits)
 
 ### AMBA ASB
 The Advanced System Bus (ASB) specification defines a high-performance bus that can be used in the design of high performance 16 and 32-bit embedded microcontrollers. It supports the efficient connection of processors, on-chip memories and off chip external memory interfaces with low-power peripheral macro cell functions. The bus also provides the test infrastructure for modular macro cell test and diagnostic access. 
 
 ## Advance Peripheral Bus
 - Advanced Peripheral Bus (APB) is the part of Advanced Microcontroller Bus Architecture (AMBA) family protocols. 
 - It defines a low-cost interface that is optimized for minimal power consumption and reduced interface complexity.
 - The APB protocol is not pipelined, use it to connect to low-bandwidth peripherals that do not require the high performance of the AXI protocol.
 - The APB protocol relates a signal transition to the rising edge of the clock, to simplify the integration of APB peripherals into any design flow. Every transfer takes at least two cycles.
 - The APB can interface with the AMBA Advanced High-performance Bus Lite (AHB-Lite) and AMBA Advanced Extensible Interface (AXI). You can use it to provide access to the programmable control registers of peripheral devices. 
 - The AMBA APB appears as a local secondary bus that is encapsulated as a single AHB or ASB slave device.
 -  APB protocol uses massive memory-I/O accesses.
 - In APB protocol consist of single master device and multiple slave device.

 ### APB Block Diagram

 ![Img2](https://user-images.githubusercontent.com/69890373/100778984-b6cd1b80-342d-11eb-9816-2fda2fc16dff.png)

 ### Signal Descriptions of APB

 

