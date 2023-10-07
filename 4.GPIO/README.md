# GPIO Programming Model

![Screenshot from 2023-10-04 22-04-53](https://github.com/PranabNandy/MCU-Driver-Development/assets/80820274/e4293aca-cf25-4cc1-9a9a-b39f0697d80b)


![Screenshot from 2023-10-04 21-55-26](https://github.com/PranabNandy/MCU-Driver-Development/assets/80820274/16a687c6-e171-4610-8f3c-f1b398be94cc)

### Each GPIO port has a group of 16 GPIO pins

-  9 Ports === 16*9 == 144 GPIO pins must be therer.

-  But in the discovery board with 5 GPIO port, only 80 GPIO pins are available. **( GPIOA,GPIOB,GPIOC,GPIOD,GPIOE)**
-  Each GPIO pins governs by some registers
![Screenshot from 2023-10-07 10-42-06](https://github.com/PranabNandy/MCU-Driver-Development/assets/80820274/8a535a7a-7942-4f66-9baf-02bfea894800)

-  In STM32F4 discovery board, GPIO pins governs by these many registers
-   ![Screenshot from 2023-10-07 10-41-26](https://github.com/PranabNandy/MCU-Driver-Development/assets/80820274/4aedad27-9d10-4735-b8fe-cfb4031de144)




## GPIO Output Pin
![Screenshot from 2023-10-07 09-11-02](https://github.com/PranabNandy/MCU-Driver-Development/assets/80820274/1be46a45-56cb-4546-bd4a-ec50052b5092)

## GPIO Pin in INPUT mode
![Screenshot from 2023-10-07 08-36-46](https://github.com/PranabNandy/MCU-Driver-Development/assets/80820274/de187d34-ab37-4f27-9cef-0f3c685b0e66)

When the I/O port is programmed as Input:

-  The output buffer is disabled
-  The Schmitt trigger input is activated
-  The pull-up and pull-down resistors are activated depending on the value in the GPIOx_PUPDR register
- The data present on the I/O pin are sampled into the input data register every AHB1 clock cycle
- A read access to the input data register provides the I/O State

#### In Input mode, output circuit will be off.
#### In Output mode, input circuit still be on. 

## GPIO Pin in OUTPUT mode

#### When system input is 1

![Screenshot from 2023-10-07 08-42-01](https://github.com/PranabNandy/MCU-Driver-Development/assets/80820274/78f4b8d9-296a-4e9f-b17d-f9396efd9b70)

#### When system input is 0
![Screenshot from 2023-10-07 08-42-55](https://github.com/PranabNandy/MCU-Driver-Development/assets/80820274/9573e30a-04a0-4c68-9fa4-1ca16b689a03)

#### Open Drain Mode
Here we add external **VOL source and 1 Kohm register**
![Screenshot from 2023-10-07 08-51-26](https://github.com/PranabNandy/MCU-Driver-Development/assets/80820274/19c624ed-fb46-47b1-82b7-7dbd5e204967)
-  In some application we need high and low state then go with Push Pull configuration 
-  IN some application we need only high state then go with Open drain which uses external register and VOL source to achive the goal. 
