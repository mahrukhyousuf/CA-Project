# RISC-V Pipelined Processor  

## Project Overview  
This project involves designing and implementing a **5-stage pipelined RISC-V processor** capable of executing the **Bubble Sort algorithm**. The goal was to enhance our understanding of processor architecture by constructing a single-cycle processor, converting it into a pipelined processor, and implementing hazard detection mechanisms.  

## Team Members  
- **Mahrukh Yousuf (08055)**  
- **Ayesha Eiman (08013)**  
- **Arsal Jangda (08514)**  

## Tasks & Implementation  

### **Task 1: Bubble Sort Implementation (Single-Cycle Processor)**  
- Converted Bubble Sort into **RISC-V Assembly** and verified it using the **Venus Simulator**.  
- Converted the assembly instructions into **machine code** and integrated them into the **Instruction Memory**.  
- Modified a previously built **single-cycle processor** (from Lab 11) to execute Bubble Sort.  
- Components modified:  
  - **Instruction Memory**  
  - **Data Memory**  
  - **Register File**  
  - **Branch Unit**  
  - **ALU Control & ALU (64-bit)**  
- **Simulation Results:** The algorithm successfully sorted the array in simulation.  

### **Task 2: Pipelined RISC-V Processor Implementation**  
- Transformed the single-cycle processor into a **5-stage pipelined processor** using the following pipeline registers:  
  1. **IF/ID** - Instruction Fetch/Decode  
  2. **ID/EX** - Instruction Decode/Execute  
  3. **EX/MEM** - Execute/Memory  
  4. **MEM/WB** - Memory/Write Back  
- These registers ensure proper instruction execution while preventing data interference.  
- **Test Cases & Simulation:** The pipeline successfully processed instructions, with values passing through all stages.  

### **Task 3: Implementing Hazard Detection**  
- Implemented hazard detection to handle:  
  - **Data hazards** (when an instruction depends on a previous instruction’s result)  
  - **Structural hazards** (resource conflicts)  
  - **Control hazards** (incorrect branch predictions)  
- Introduced a **Hazard Detection Module** that stalls the processor when required.  
- Implemented a **Forwarding Unit** to optimize execution by forwarding data instead of stalling.  
- **Simulation Results:** Hazards were detected and mitigated using stalling and forwarding techniques.  

### **Performance Comparison: Single-Cycle vs Pipelined**  
- The **single-cycle processor** executed Bubble Sort in **1000 nanoseconds**.  
- The **pipelined processor** took **more than 1000 nanoseconds** due to unavoidable stalls.  
- **Key Finding:** Despite pipelining, performance was affected by hazard-induced stalls.  

## Challenges Faced  
- Debugging module interconnections.  
- Handling branch equal (`beq`) instruction implementation.  
- Ensuring proper control signal assignment in pipeline stages.  

## Tools & References  
- **Simulator:** Venus RISC-V Simulator  
- **Textbook:** *Computer Organization and Design: The Hardware/Software Interface (RISC-V Edition)* by David A. Patterson, John L. Hennessy  
 

## Conclusion  
Through this project, we developed a deeper understanding of processor architecture, pipelining, and hazard management. The transition from a single-cycle to a pipelined processor strengthened our grasp of execution optimization techniques.  

