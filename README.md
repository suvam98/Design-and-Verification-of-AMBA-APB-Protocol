# Design-Verification-of-AMBA-APB-Protocol

## Table of Content
 - [Introduction of AMBA](https://github.com/suvam98/Design-Verification-of-AMBA-APB-Protocol#introduction-of-amba)
 - AMBA Bus architecture
 - Advance Peripheral Bus(APB)
 - Design and Operating states of APB
 - Simulation result of APB design
 - Conclusion
 - Acknowledgement
 - References

 ## Introduction of AMBA
 - The Advanced Micro controller Bus Architecture (AMBA) bus protocols is a set of interconnect specifications from ARM that standardizes on chip communication mechanisms between various functional blocks (or IP) for building high performance SOC design.

 - These designs typically have one or more micro controllers or microprocessors along with several other components — internal memory or external memory bridge, DSP, DMA, accelerators and various other peripherals like USB, UART, PCIE, I2C etc — all integrated on a single chip.  

 - Today, AMBA is widely used on a range of ASIC and SoC parts including applications processors used in modern portable mobile devices like smartphones. 

 AMBA was introduced by ARM in 1996. The first AMBA buses were the Advanced System Bus (ASB) and the Advanced Peripheral Bus (APB). 

 In its second version, AMBA 2 in 1999, ARM added AMBA High-performance Bus (AHB) that is a single clock-edge protocol.
 
 In 2003, ARM introduced the third generation, AMBA 3, including Advanced eXtensible Interface (AXI) to reach even higher performance interconnect and the Advanced Trace Bus (ATB) as part of the CoreSight on-chip debug and trace solution. 

 In 2010 the AMBA 4 specifications were introduced starting with AMBA 4 AXI4, then in 2011[2] extending system-wide coherency with AMBA 4 AXI Coherency Extensions (ACE). 

 In 2013[3] the AMBA 5 Coherent Hub Interface (CHI) specification was introduced, with a re-designed high-speed transport layer and features designed to reduce congestion.


 - The Advanced Peripheral Bus (APB) is part of the Advanced Microcontroller Bus Architecture
(AMBA) protocol family. It defines a low-cost interface that is optimized for minimal power
consumption and reduced interface complexity.
- The APB protocol is not pipelined, use it to connect to low-bandwidth peripherals that do not
require the high performance of the AXI protocol.
- The APB protocol relates a signal transition to the rising edge of the clock, to simplify the
integration of APB peripherals into any design flow. Every transfer takes at least two cycles.
- 
