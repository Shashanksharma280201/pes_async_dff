# pes_async_dff

In the context of digital design and hardware description languages (HDLs), "DFF" stands for "D Flip-Flop," and "async" is short for "asynchronous." Let's break down these terms:

- **D Flip-Flop (DFF):** A D Flip-Flop is a fundamental building block in digital circuits and sequential logic. It is used to store and synchronize data in a digital system. A DFF has two inputs: a data input (D) and a clock input (CLK). When a rising or falling edge of the clock signal is detected, the value on the data input is transferred to the output (Q). D Flip-Flops are crucial for creating sequential circuits, such as registers and memory elements.

- **Asynchronous (Async):** In the context of D Flip-Flops and sequential circuits, "asynchronous" refers to a situation where the clock signal is not used to control the operation of the flip-flop. Instead, the flip-flop responds immediately to changes on its data input, irrespective of the clock signal. Asynchronous operation can be used in certain situations where the timing and synchronization requirements are different from those in synchronous systems. However, asynchronous designs can be more complex and challenging to analyze due to potential hazards and timing issues.


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

# Openlane2 installation : 
- Follow [Openlane2](https://github.com/Shashanksharma280201/openlane_2_installation) to install openlane2 , magic , spice , NIX and Docker 

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

### To see the layout we use a tool called magic which we installed earlier.Type the following command in the terminal opened in the path to your design/runs/latest run folder/results/final/def/

```
magic -T /home/shashank/openlane/pdks/sky130A/libs.tech/magic/sky130A.tech lef read ../../../tmp/merged.nom.lef def read pes_dff_async.def &
```
![3](https://github.com/Shashanksharma280201/pes_async_dff/assets/79470436/70e9c2a0-7b52-4094-9199-4dc9eaad2ffc)


### The reports generated are given below

![1](https://github.com/Shashanksharma280201/pes_async_dff/assets/79470436/73feabe3-493b-4dd4-9c62-aec5a6e518cd)
![2](https://github.com/Shashanksharma280201/pes_async_dff/assets/79470436/d950e01f-1af4-4c2b-86f8-472c78622a82)
![3](https://github.com/Shashanksharma280201/pes_async_dff/assets/79470436/9de5e8cb-7551-4172-8442-4feafa22f955)
![4](https://github.com/Shashanksharma280201/pes_async_dff/assets/79470436/128e1469-7889-40c7-8bca-341dcf1da543)
![5](https://github.com/Shashanksharma280201/pes_async_dff/assets/79470436/0f29ce62-d6e0-44f1-af62-56f209578af2)
![6](https://github.com/Shashanksharma280201/pes_async_dff/assets/79470436/d81993a8-cdfa-46ca-a90b-12496af44859)
![7](https://github.com/Shashanksharma280201/pes_async_dff/assets/79470436/8d672c1e-a434-4567-a2dd-088c975b5865)






</details>



