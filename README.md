# pes_async_dff

In the context of digital design and hardware description languages (HDLs), "DFF" stands for "D Flip-Flop," and "async" is short for "asynchronous." Let's break down these terms:

- **D Flip-Flop (DFF):** A D Flip-Flop is a fundamental building block in digital circuits and sequential logic. It is used to store and synchronize data in a digital system. A DFF has two inputs: a data input (D) and a clock input (CLK). When a rising or falling edge of the clock signal is detected, the value on the data input is transferred to the output (Q). D Flip-Flops are crucial for creating sequential circuits, such as registers and memory elements.

- **Asynchronous (Async):** In the context of D Flip-Flops and sequential circuits, "asynchronous" refers to a situation where the clock signal is not used to control the operation of the flip-flop. Instead, the flip-flop responds immediately to changes on its data input, irrespective of the clock signal. Asynchronous operation can be used in certain situations where the timing and synchronization requirements are different from those in synchronous systems. However, asynchronous designs can be more complex and challenging to analyze due to potential hazards and timing issues.



## Openlane2 installation 
- Follow [Openlane2](https://github.com/Shashanksharma280201/openlane_2_installation) to install openlane2 , magic , spice , NIX and Docker 


<details>
  <summary>GLS process</summary>
    <br>

## Code 
![Screenshot from 2023-10-19 00-33-23](https://github.com/Shashanksharma280201/pes_async_dff/assets/79470436/d9093e5f-a1c7-4c83-91df-e7cd96484e7e)

## TestBench code 
![image](https://github.com/Shashanksharma280201/pes_async_dff/assets/79470436/762aef1e-4054-4e75-942d-a4134201aa7c)


![Screenshot from 2023-10-18 23-59-06](https://github.com/Shashanksharma280201/pes_async_dff/assets/79470436/5e83a44b-3e23-488b-a43f-9451966da3cf)

![Screenshot from 2023-10-19 00-22-59](https://github.com/Shashanksharma280201/pes_async_dff/assets/79470436/7b0a5306-5ce6-4512-b7d6-4cdc45ae92ad)

## yosys

![Screenshot from 2023-10-19 00-23-26](https://github.com/Shashanksharma280201/pes_async_dff/assets/79470436/724f28c4-ec30-473e-ae6b-99402dace77e)

![Screenshot from 2023-10-19 00-23-40](https://github.com/Shashanksharma280201/pes_async_dff/assets/79470436/f9b5e397-9e5a-45d0-bed0-d5405c8962a6)

![Screenshot from 2023-10-19 00-05-58](https://github.com/Shashanksharma280201/pes_async_dff/assets/79470436/fcb4baa5-7d24-425d-b886-86b4fd3cd9c2)

![Screenshot from 2023-10-19 00-29-31](https://github.com/Shashanksharma280201/pes_async_dff/assets/79470436/36c52c62-38fd-4371-83e4-1753f18617c4)

</details>

<details>
  <summary> PD process  </summary>
    <br>
- First create a folder in you Openlane/design directory and save your design there.

![Screenshot from 2023-10-31 18-50-25](https://github.com/Shashanksharma280201/pes_async_dff/assets/79470436/958823c8-007a-4b45-aa74-66af1aa6a34a)

- Then create a folder named 'src' and save the main verilog code in that folder too and also save it outside the folder as well , with the verilog code also save the
```
sky130_fd_sc_hd__fast.lib
sky130_fd_sc_hd__slow.lib
sky130_fd_sc_hd__typical.lib
```
- create a config.json file outside your src folder.
- all the files are present at the top

![Screenshot from 2023-10-31 18-58-13](https://github.com/Shashanksharma280201/pes_async_dff/assets/79470436/84e60aea-4d69-4994-8a15-81791b489d54)

- create the pdk folder outside your design folder that is in Openlane/pdk

![Screenshot from 2023-10-31 19-01-05](https://github.com/Shashanksharma280201/pes_async_dff/assets/79470436/09796872-52f4-4aa8-85cc-60ddc38c2138)

![Screenshot from 2023-10-31 19-01-30](https://github.com/Shashanksharma280201/pes_async_dff/assets/79470436/cac5b70d-dced-4955-af26-97d437492161)

### Open terminal in home directory and type the following commands:
```
cd OpenLane/
cd designs/
mkdir pes_dff_async
cd pes_dff_async/
wget https://raw.githubusercontent.com/majilokesh/iiitb_tlc/main/config.json
mkdir src
cd src/
wget https://raw.githubusercontent.com/majilokesh/iiitb_tlc/main/iiitb_tlc.v
cd ../../../
sudo make mount
./flow.tcl -interactive
```
  
### STEPS RUNNING:

```

[STEP 1] : Running Synthesis.
[STEP 2] : Running Single-Corner Static Timing Analysis.
[STEP 3] : Running Initial Floorplanning, Setting Core Dimensions.
[STEP 4] : Running IO Placement.
[STEP 5] : Running Power planning with power {VPWR} and ground {VGND}.
[STEP 6] : Generating PDN.
[STEP 7] : Performing Random Global Placement.
[STEP 8] : Running Placement Resizer Design Optimizations.
[STEP 9] : Writing Verilog.
[STEP 10] : Running Detailed Placement.
[STEP 11] : Running Placement Resizer Timing Optimizations.
[STEP 12] : Writing Verilog, Routing.
[STEP 13] : Running Global Routing Resizer Timing Optimizations.
[STEP 14] : Writing Verilog.
[STEP 15] : Running Detailed Placement.
[STEP 16] : Running Global Routing, Starting FastRoute Antenna Repair Iterations.
[STEP 17] : Running Fill Insertion.
[STEP 18] : Writing Verilog.
[STEP 19] : Running Detailed Routing, No DRC violations after detailed routing.
[STEP 20] : Writing Verilog, Running parasitics-based static timing analysis.
[STEP 21] : Running SPEF Extraction at the min process corner.
[STEP 22] : Running Multi-Corner Static Timing Analysis at the min process corner.
[STEP 23] : Running SPEF Extraction at the max process corner.
[STEP 24] : Running Multi-Corner Static Timing Analysis at the max process corner.
[STEP 25] : Running SPEF Extraction at the nom process corner...
[STEP 26] : Running Single-Corner Static Timing Analysis at the nom process corner...
[STEP 27] : Running Multi-Corner Static Timing Analysis at the nom process corner...
[STEP 28] : Running Magic to generate various views, Streaming out GDS-II with Magic, Generating MAGLEF views...
[STEP 29] : Streaming out GDS-II with Klayout...
[STEP 30] : Running XOR on the layouts using Klayout...
[STEP 31] : Running Magic Spice Export from LEF...
[STEP 32] : Writing Powered Verilog.
[STEP 33] : Writing Verilog.
[STEP 34] : Running LEF LVS.
[STEP 35] : Running Magic DRC, Converting Magic DRC Violations to Magic Readable Format, Converting Magic DRC Violations to Klayout Database, Converting DRC Violations to RDB Format, No DRC violations after GDS streaming out, Running Antenna Checks.
[STEP 36] : Running OpenROAD Antenna Rule Checker.
[STEP 37] : Running CVC, Saving final set of views, 
Saving runtime environment, 
Generating final set of reports, Created manufacturability report at 'designs/iiitb_tlc/runs/RUN_2022.06.07_10.39.52/reports/manufacturability.rpt', 
Created metrics report at 'designs/iiitb_tlc/runs/RUN_2022.06.07_10.39.52/reports/metrics.csv', 
There are no max slew violations in the design at the typical corner, There are no hold violations in the design at the typical corner, There are no setup violations in the design at the typical corner.

[SUCCESS]: Flow complete.

```  

### Interactive OpenLane flow
Open terminal in home directory and then type the following:

```

cd OpenLane/ 
sudo make mount 

./flow.tcl -interactive
package require openlane 0.9
prep -design pes_dff_async

run_synthesis
run_floorplan
run_placement
run_cts
run_routing
run_magic
run_magic_spice_export
run_magic_drc
run_netgen
run_magic_antenna_check
```

## Synthesis stage:
Synthesis is a fundamental stage in the digital design flow. It takes an abstract hardware description and generates a netlist consisting of logical gates and flip-flops that represent the desired functionality of the design.

![Screenshot from 2023-10-31 23-09-08](https://github.com/Shashanksharma280201/pes_async_dff/assets/79470436/7f036e86-b5be-4e42-b41c-16bcbc2cae9a)

- Area report

![Screenshot from 2023-10-31 23-10-14](https://github.com/Shashanksharma280201/pes_async_dff/assets/79470436/084ec341-d0d7-4e6e-8888-fecb74474205)



## Floorplan stage:

The floorplan stage in digital integrated circuit design involves creating a high-level layout for the chip, defining the core area, the locations of I/O pads, and other critical structures. It establishes the overall physical framework for the chip design and serves as a foundation for subsequent stages such as placement and routing. During the floorplan stage, designers make decisions about the chip's dimensions, aspect ratio, power grid, and other essential aspects to meet the project's requirements. The goal is to efficiently allocate space for various components while adhering to design constraints, ultimately ensuring that the chip will meet its performance, power, and area goals.


![Screenshot from 2023-10-31 22-36-07](https://github.com/Shashanksharma280201/pes_async_dff/assets/79470436/30708c23-3ce6-4a84-910c-6b31eb7079a5)

```
magic -T /home/shashank/OpenLane/pdk/sky130A/libs.tech/magic/sky130A.tech lef read ../../tmp/merged.nom.lef def pes_dff_async.def &
```

![Screenshot from 2023-10-31 22-46-50](https://github.com/Shashanksharma280201/pes_async_dff/assets/79470436/59fc8b10-e7ff-4132-93be-edb508fc9956)


## Placement stage:

The placement stage in digital integrated circuit design involves determining the physical positions of synthesized logic cells on the chip's layout. This critical step aims to optimize the arrangement of cells to minimize wirelength, meet design constraints, and achieve desired performance. Placement typically involves global placement, which provides a rough layout, followed by legalization to ensure cells conform to design rules and spacing requirements. The outcome of this stage is a physical placement file that specifies the coordinates of each cell, serving as the basis for subsequent routing and design verification steps. Efficient placement is essential for optimizing area, power, and signal timing in the final chip design.

![Screenshot from 2023-10-31 22-48-30](https://github.com/Shashanksharma280201/pes_async_dff/assets/79470436/c2b91560-2872-42af-9fef-575f20a7c01c)
```
magic -T /home/shashank/OpenLane/pdk/sky130A/libs.tech/magic/sky130A.tech lef read ../../tmp/merged.nom.lef def pes_dff_async.def &
```
![Screenshot from 2023-10-31 22-49-44](https://github.com/Shashanksharma280201/pes_async_dff/assets/79470436/00bd8d88-8bb1-4e78-acad-4b1ad0a67d44)

## Cts stage:

The CTS (Clock Tree Synthesis) stage is responsible for creating a clock distribution network that ensures reliable and synchronized clock signals reach all the sequential elements (like flip-flops) in the chip. This stage involves the following key steps:

- Buffer Insertion: The CTS process inserts buffers into the clock network to balance and distribute the clock signal evenly. Buffers help in reducing clock skew, ensuring that all parts of the chip receive clock signals simultaneously.

- Clock Tree Construction: The clock tree is constructed by connecting the buffers in a hierarchical fashion from the global clock source (e.g., a PLL or external input) to the leaf-level cells throughout the chip.

- Skew Minimization: The CTS stage aims to minimize clock skew, which is the variation in arrival times of the clock signal at different points in the design. Minimizing skew ensures that all registers see the same clock edge simultaneously, which is crucial for proper circuit operation.

- Power Optimization: CTS also involves power optimization techniques to reduce dynamic and static power consumption in the clock distribution network.

- Constraints and Timing: It takes into consideration the design constraints related to clock paths, such as clock-to-q requirements, setup and hold times, and other timing considerations.

- Clock Gating: Clock gating cells may be inserted in the clock tree to save power when certain parts of the chip are not in use, and the clock can be temporarily disabled.


![Screenshot from 2023-10-31 22-51-38](https://github.com/Shashanksharma280201/pes_async_dff/assets/79470436/4a354bbf-843f-4a84-bd5f-336de575ee4a)

- The reports generated are given below , after the run_cts command 

![Screenshot from 2023-10-31 19-45-44](https://github.com/Shashanksharma280201/pes_async_dff/assets/79470436/fe5958c2-aaf2-4549-af80-1442e246c11a)
![Screenshot from 2023-10-31 19-45-51](https://github.com/Shashanksharma280201/pes_async_dff/assets/79470436/874f1e08-6b57-47ba-a219-bda51d2c2f0d)
![Screenshot from 2023-10-31 19-45-57](https://github.com/Shashanksharma280201/pes_async_dff/assets/79470436/af857d12-4fdc-4540-89f4-1f8b3f69d0ec)
![Screenshot from 2023-10-31 19-46-03](https://github.com/Shashanksharma280201/pes_async_dff/assets/79470436/9fe8e5f2-d0a7-4f89-a1ff-4cbf27b8a6e0)
![Screenshot from 2023-10-31 19-46-08](https://github.com/Shashanksharma280201/pes_async_dff/assets/79470436/07893715-193f-416f-8d63-075e748bcffa)
![Screenshot from 2023-10-31 19-46-13](https://github.com/Shashanksharma280201/pes_async_dff/assets/79470436/6145438b-466e-4988-963a-f134bcbed995)
![Screenshot from 2023-10-31 19-46-21](https://github.com/Shashanksharma280201/pes_async_dff/assets/79470436/cfb7d683-fe76-45f9-9589-11fc7d124c56)
![Screenshot from 2023-10-31 19-46-25](https://github.com/Shashanksharma280201/pes_async_dff/assets/79470436/3d77187c-1d7d-4ddf-8589-a32c156b4ce7)

## Routing stage:

- The routing stage is responsible for creating the physical wire connections between the placed cells on the chip layout. This involves determining the paths for signal wires, power distribution, and clock signals, while adhering to design rules, avoiding congestion, and optimizing for various factors such as wirelength, signal delay, and power consumption.

![Screenshot from 2023-10-31 23-13-52](https://github.com/Shashanksharma280201/pes_async_dff/assets/79470436/7fc9a4bc-a0f8-47c9-bebd-7b4a93749a2a)

```
magic -T /home/shashank/OpenLane/pdk/sky130A/libs.tech/magic/sky130A.tech lef read ../../tmp/merged.nom.lef def pes_dff_async.def &
```
![Screenshot from 2023-10-31 23-15-07](https://github.com/Shashanksharma280201/pes_async_dff/assets/79470436/898610d3-3086-4356-82de-5222e48d02f6)



### Magic Spice report

- A "Magic Spice report" stage would suggest a point in the design flow where you are generating reports that combine information from Magic (layout design) and Spice (circuit simulation) tools. These reports might contain critical details about how the physical layout of the integrated circuit corresponds to its electrical behavior, helping designers identify and address any issues or validate the design.

![Screenshot from 2023-10-31 23-16-25](https://github.com/Shashanksharma280201/pes_async_dff/assets/79470436/4cc4f6cf-81d4-4de8-84a1-237f52908152)


![Screenshot from 2023-10-31 19-48-41](https://github.com/Shashanksharma280201/pes_async_dff/assets/79470436/f142f93b-ea91-4670-a7c4-2d644f84a856)
![Screenshot from 2023-10-31 19-48-44](https://github.com/Shashanksharma280201/pes_async_dff/assets/79470436/f68c7a61-6a5d-4d61-9952-2c48c4cd81f6)
![Screenshot from 2023-10-31 19-48-49](https://github.com/Shashanksharma280201/pes_async_dff/assets/79470436/7502a6b9-c416-4b88-9b7b-7cc314cdf989)


### magic antenna check 

- The "magic antenna check" is essential for addressing reliability concerns and ensuring that the final chip design will not experience problems related to charge buildup and oxide damage, which could affect the functionality and longevity of the integrated circuit.

![Screenshot from 2023-10-31 23-18-10](https://github.com/Shashanksharma280201/pes_async_dff/assets/79470436/9b3aad7d-cdac-411a-be72-395b48e91eb0)


![Screenshot from 2023-10-31 19-50-57](https://github.com/Shashanksharma280201/pes_async_dff/assets/79470436/9e7665d6-22d6-442c-8fa8-d737b43ca742)
![Screenshot from 2023-10-31 19-51-01](https://github.com/Shashanksharma280201/pes_async_dff/assets/79470436/77fd6900-b521-4b35-b25a-dd158d4abe98)
![Screenshot from 2023-10-31 19-51-05](https://github.com/Shashanksharma280201/pes_async_dff/assets/79470436/7f4eb9cf-2add-42b3-a8bb-efd638db0fc6)


### To see the layout we use a tool called magic which we installed earlier.Type the following command in the terminal opened in the path to your design/runs/latest run folder/results/final/def/

```
magic -T /home/shashank/openlane/pdks/sky130A/libs.tech/magic/sky130A.tech lef read ../../../tmp/merged.nom.lef def read pes_dff_async.def &
```
![3](https://github.com/Shashanksharma280201/pes_async_dff/assets/79470436/70e9c2a0-7b52-4094-9199-4dc9eaad2ffc)


</details>



