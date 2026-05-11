Overview
----------------------------------------------------
This repository contains the design, implementation, and analysis of a 6-Transistor (6T) Static Random Access Memory (SRAM) cell using Cadence Virtuoso. The project focuses on schematic design, transistor sizing for stability, and DC analysis (Butterfly Curve) to evaluate the Static Noise Margin (SNM).

-----------------------------------------------------

Designer : Krishna  
Tool used : Cadence Virtuoso  
Library   : gpdk045  
License   : IIT BOMBAY  

---------------------------------------------------------
 
THE COMPLETE SCHEMATIC OF SRAM 6T CELL
--------------------------------------------------------------------------------------------------------------------------------------

<img width="500" height="250" alt="image" src="https://github.com/user-attachments/assets/2d678c11-0107-433f-91c9-d0033df4634a" />

----------------------------------------------------------------------------------------------------------------------------------------------------------
Transistor Sizing
----------------------------------------------------------------------------------------------------------------------------------------------------------
<img width="500" height="250" alt="image" src="https://github.com/user-attachments/assets/fddddae2-8d32-4b3b-9731-38b80a448898" />

To ensure the cell operates correctly during read and write operations, the following sizing ratios were used:

Pull-Up (PMOS): Reference Width (Wp) - Acts as the load transistors in the cross-coupled inverters.

Pull-Down (NMOS): 2 * Wp - Driver transistors sized larger than PMOS to ensure a strong "0" and proper read stability.

Pass-Gate (NMOS): 1.5 * Wp - Access transistors sized between the driver and load to balance write-ability and read-stability (Cell Ratio and Pull-up Ratio).


--------------------------------------------------------------------------------------------------------------------------------------------------
Testbench SetupThe testbench is configured to perform DC Analysis.
---------------------------------------------------------------------------------------------------------------------------------------------------

1.  Voltage SourcesVDC (VDD): Set to the nominal voltage for your process node (e.g., 1.8V).VPULSE / VDC (WL): Word line held high at VDD to enable the access transistors during the sweep.VDC (BL/BLB): Bit lines tied to VDD for Read Margin analysis.
2.  Simulation ParametersAnalysis Type: DC Sweep.Sweep Variable: Input voltage source connected to one side of the internal latch.Sweep Range: 0V to VDD.
3.  Output VisualizationNodes: Q and QB (the internal storage nodes).Plotting: Use the "Y versus Y" function in the Cadence Virtuoso Visualization & Analysis tool. Plot $V(Q)$ vs $V(QB)$ and $V(QB)$ vs $V(Q)$ to generate the characteristic Butterfly Plot.


-----------------------------------------------------------------------------------------------------------------------------------
OUTPUT of DC Characterstics of 6T SRAM 
--------------------------------------------------------------------------------------------------------------------------------------

<img width="500" height="250" alt="image" src="https://github.com/user-attachments/assets/931c22b4-35d3-4b5f-b723-ab5caa01973f" />

------------------------------------------------------------------------------------------------------------------------------
BUTTERFLY CURVE using Y vs Y function
---------------------------------------------------------------------------------------------------------------------------

<img width="800" height="400" alt="image" src="https://github.com/user-attachments/assets/a9119b5f-2bc6-4415-bdea-5bd0d926384b" />



