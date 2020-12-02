# Design and-Verification-of-AMBA-APB-Protocol

## Table of Content
 - [Introduction of AMBA](https://github.com/suvam98/Design-Verification-of-AMBA-APB-Protocol#introduction-of-amba)
 - [Design principles](https://github.com/suvam98/Design-Verification-of-AMBA-APB-Protocol#design-principles)
 - [AMBA Bus specification](https://github.com/suvam98/Design-Verification-of-AMBA-APB-Protocol#amba-bus--specification)
   * [Types of AMBA Bus](https://github.com/suvam98/Design-Verification-of-AMBA-APB-Protocol#types-of-amba-bus)
   * [AMBA AHB](https://github.com/suvam98/Design-Verification-of-AMBA-APB-Protocol#amba-ahb)
   * [AMBA ASB](https://github.com/suvam98/Design-Verification-of-AMBA-APB-Protocol#amba-asb)
 - [Advance Peripheral Bus](https://github.com/suvam98/Design-Verification-of-AMBA-APB-Protocol#advance-peripheral-bus)
   * [APB Block Diagram](https://github.com/suvam98/Design-Verification-of-AMBA-APB-Protocol#apb-block-diagram)
   * [Signal Descriptions of APB](https://github.com/suvam98/Design-Verification-of-AMBA-APB-Protocol#signal-descriptions-of-apb) 
 - [Design and operating states of APB](https://github.com/suvam98/Design-Verification-of-AMBA-APB-Protocol#design-and-operating-states-of-apb)
   * [Write operation](https://github.com/suvam98/Design-Verification-of-AMBA-APB-Protocol#write-operation)
   * [Read operation](https://github.com/suvam98/Design-Verification-of-AMBA-APB-Protocol#write-operation-1)
 - [Simulation result](https://github.com/suvam98/Design-Verification-of-AMBA-APB-Protocol#simulation-result) 
 - [Conclusion](https://github.com/suvam98/Design-Verification-of-AMBA-APB-Protocol#conclusion)
 - [Future work](https://github.com/suvam98/Design-Verification-of-AMBA-APB-Protocol#future-work)    
 - [Acknowledgement](https://github.com/suvam98/Design-Verification-of-AMBA-APB-Protocol#acknowledgement)
 - [References](https://github.com/suvam98/Design-Verification-of-AMBA-APB-Protocol#references)
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

![image](https://user-images.githubusercontent.com/69890373/100849030-f89aa800-34a7-11eb-81c7-fd4a40170dcf.png)

 ### Signal Descriptions of APB

 | Signal | Source | Description |
 | --- | --- | --- |
 | **PCLK** | Clock source | Clock. The rising edge of **PCLK** times all transfers on the APB. |
 | **PSELn** | APB bridge | Select. The APB bridge unit generates this signal to each peripheral bus slave. It indicates that the slave device is selected and that a data transfer is required. There is a **PSELn** signal for each slave. |
 | **PRESET** | System bus equivalent | Reset. The APB reset signal is active LOW. This signal is normally connected directly to the system bus reset signal. |
 | **PADDR** | APB bridge | Address. This is the APB address bus. It can be up to 32 bits wide and is driven by the peripheral bus bridge unit. |
 | **PENABLE** | APB bridge | Enable. This signal indicates the second and subsequent cycles of an APB transfer. |
 | **PWRITE** | APB bridge | Direction. This signal indicates an APB write access when HIGH and an APB read access when LOW. |
 | **PWDATA** | APB bridge | Write data. This bus is driven by the peripheral bus bridge unit during write cycles when **PWRITE** is HIGH. This bus can be up to 32 bits wide. |
 | **PREADY** | Slave interface | Ready. The slave uses this signal to extend an APB transfer. |
 | **PRDATA** | Slave interface | Read Data. The selected slave drives this bus during read cycles when **PWRITE** is LOW. This bus can be up to 32-bits wide. |
 | **PSLVERR** | Slave interface | This signal indicates a transfer failure. APB peripherals are not required to support the **PSLVERR** pin. This is true for both existing and new APB peripheral designs. Where a peripheral does not include this pin then the appropriate input to the APB bridge is tied LOW. |

## Design and operating states of APB

![Img3](https://user-images.githubusercontent.com/69890373/100839325-0a754e80-349a-11eb-862c-79a6a0d62c84.png)

- **IDLE** is the normal state of the APB. When a transfer is necessary the bus relocates into the SETUP state, where the suitable select signal, **PSELn**, is asserted.
- The bus only waits in the SETUP state for one clock cycle and always moves to the ACCESS state on the next rising edge of the clock.
- **ACCESS** will enable signal, **PENABLE**, is asserted in the ACCESS state.
- The write, write data signals, select, and address must remain stable during the transition from the SETUP to ACCESS state. 
-  ACCESS state is controls when to exit by the **PREADY** signal from the slave.
- These are the conditions one is if **PREADY** is held LOW by the slave then the peripheral bus remains in the ACCESS state another is **PREADY** is driven HIGH by the slave then the ACCESS state is exited and the bus returns to the IDLE state if no more transfers are required after that it will start the same cycle.
   
### Write operation

![image](https://user-images.githubusercontent.com/69890373/100841560-74dbbe00-349d-11eb-9c17-ea28fddd68f2.png)

- At T1, a write transfer starts with PADDR, PWDATA, PWRITE, and PSEL, being registered at the rising edge of PCLK. It is called the SETUP cycle. 
- At the next rising edge of the clock T2 it is called ACCESS cycle, PENABLE, and PREADY, are registered. When asserted, PENABLE indicates starting of Access phase of the transfer. When asserted, PREADY indicates that the slave can complete the transfer at the next rising edge of PCLK. 
- The PADDR, PWDATA, and control signals all remain valid until the transfer completes at T3, the end of the Access phase.
- The PENABLE, is disabled at the end of the transfer. The select signal PSEL is also disabled unless the transfer is to be followed immediately by another transfer to the same peripheral.

### Read operation

![image](https://user-images.githubusercontent.com/69890373/100842327-b0c35300-349e-11eb-9592-4c23aad06403.png)

- During read operation the PENABLE, PSEL, PADDR PWRITE, signals are asserted at the clock edge T1 (SETUP cycle). 
- At the clock edge T2, (ACCESS cycle), the PENABLE, PREADY are asserted and PRDATA is also read during this phase. The slave must provide the data before the end of the read transfer.

## Simulation result

![image](https://user-images.githubusercontent.com/69890373/100843927-16184380-34a1-11eb-9252-f88b465c880e.png)

## Conclusion
- The APB bus is designed using the Verilog HDL according to the specification and is verified using EDAplayground. 
- The simulation results show that the data read from a  particular memory location is same as the data written to the given memory location. Hence, the design is functionally correct.

## Future work

- To verify the above design using **system verilog**.

## Acknowledgement

- Dr. Saroj Rout, Associate Professor, Silicon Institute of Technology, Bhubaneswar
- Mr. Santunu Sarangi, Assistant Professor, Silicon Institute of Technology, Bhubaneswar

## References

[1]URL:[click here](http://wwwmicro.deis.unibo.it/~magagni/amba99.pdf)

[2]ARM, “AMBA Specification Overview”, available at [URL](http://www.arm.com/)

[3]ARM, “AMBA Specification (Rev 2.0)”, available at [URL](http://www.arm.com)

[4]URL:[click here](http://www.differencebetween.net/techno logy/difference-between-ahb-and-apb)

[5]Samir Palnitkar, “Verilog HDL: A guide to Digital Design and Synthesis (2nd Edition), Pearson, 2008.


 

 

