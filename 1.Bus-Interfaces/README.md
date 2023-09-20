# MCU-Bus-interface
### A Sample Program 
![oie_fRNVPSrofedQ](https://github.com/PranabNandy/MCU-Driver-Development/assets/80820274/b02c7b38-61ff-4294-85b1-7000fc26860a)

### Cortex M4 Processor has 3 AHB and 1 APB

![Screenshot from 2023-09-20 21-39-05](https://github.com/PranabNandy/MCU-Driver-Development/assets/80820274/3c03e709-113c-44fb-a936-b9a541e9882e)


-  If the Instructions are present between **0x0000 0000 to 0x1FFF FFFC** then **Cortex** Processor will Fetch the Instruction using **I-CODE Bus Interface**
-  Else outside that range then using **System Bus**
-  If the Data are present between **0x0000 0000 to 0x1FFF FFFF** then **Cortex** Processor will Fetch the Instruction using **D-CODE Bus Interface**
-  Else outside that range then using **System Bus**
![Screenshot from 2023-09-20 21-59-47](https://github.com/PranabNandy/MCU-Driver-Development/assets/80820274/7f70329e-42cb-4478-ae8c-665ee87462f5)

-  **System Bus** operates at 180MHz **(HCLK)**
-  **APB1 (P1CLK)** = 42/45 MHz    **APB2 (P2CLK)** = 84/90 MHz
-  Processor can fetch Data and Instr from Flash simultaneously not from SRAM
-  USB OTG and GPIO can not communicate with processor simultaneously
  

![Screenshot from 2023-09-20 21-10-01](https://github.com/PranabNandy/MCU-Driver-Development/assets/80820274/c40ed0fa-7250-4b8e-a7c7-19c66db594b6)

