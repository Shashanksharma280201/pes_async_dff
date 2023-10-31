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
Follow [Openlane2](https://github.com/Shashanksharma280201/openlane_2_installation) to install openlane2 , magic and spice

<details>
  <summary> PD process  </summary>
    <br>
</details>



