# MCU-Driver-Development

![Screenshot from 2023-10-04 21-55-26](https://github.com/PranabNandy/MCU-Driver-Development/assets/80820274/16a687c6-e171-4610-8f3c-f1b398be94cc)

### Each GPIO port has a group of 16 GPIO pins

-  9 Ports === 16*9 == 144 GPIO pins must be therer.

-  But in the discovery board with 5 GPIO port, only 80 GPIO pins are available. **( GPIOA,GPIOB,GPIOC,GPIOD,GPIOE)**
-  Each GPIO pins governs by some registers
![Screenshot from 2023-10-07 10-42-06](https://github.com/PranabNandy/MCU-Driver-Development/assets/80820274/8a535a7a-7942-4f66-9baf-02bfea894800)

-  In STM32F4 discovery board, GPIO pins governs by these many registers
-   ![Screenshot from 2023-10-07 10-41-26](https://github.com/PranabNandy/MCU-Driver-Development/assets/80820274/4aedad27-9d10-4735-b8fe-cfb4031de144)
