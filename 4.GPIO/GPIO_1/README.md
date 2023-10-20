# Different types of GPIO pin configuration
![Screenshot from 2023-10-07 12-22-01](https://github.com/PranabNandy/MCU-Driver-Development/assets/80820274/53485490-42db-4e29-b7bb-6b45d569c372)


# GPIO Output speed register
- **configure “how quick the GPIO transitions from H to L and L to H”. In other words you can control the slew rate of a pin**

![Screenshot from 2023-10-07 11-36-56](https://github.com/PranabNandy/MCU-Driver-Development/assets/80820274/80a7f2f9-1356-4132-8d7c-af8cf4774480)


![Screenshot from 2023-10-07 12-13-38](https://github.com/PranabNandy/MCU-Driver-Development/assets/80820274/c598b713-88a2-42a6-966f-54498a5cb7b4)


# GPIO clock enable register

![Screenshot from 2023-10-07 22-10-55](https://github.com/PranabNandy/MCU-Driver-Development/assets/80820274/4e6fd3b8-1ead-40e1-9567-d8886dba9c77)

# Alternate Functionality 

![Screenshot from 2023-10-07 22-37-54](https://github.com/PranabNandy/MCU-Driver-Development/assets/80820274/bec9acd8-6fe2-462c-9645-b8fc0b4a5a3f)















# Sample STM32 Cube
![Screenshot from 2023-10-07 22-57-13](https://github.com/PranabNandy/MCU-Driver-Development/assets/80820274/806f9c84-a8f9-46e7-a5d1-81af3022e088)
## Memory Organization
![Screenshot from 2023-10-17 18-13-25](https://github.com/PranabNandy/MCU-Driver-Development/assets/80820274/4c5dd0b1-18b5-42b6-a9d3-2da57bd2e533)
**What is Device Header file and what it contains ?**

This is a header file ("C" header file in our case) which contains Microcontroller specific details such as
- The base addresses of various memories present in the microcontroller such as (Flash, SRAM1,SRAM2,ROM,etc)
- The base addresses of various bus domains such as (AHBx domain, APBx domain)
- Base addresses of various peripherals present in different bus domains of the microcontroller
- Clock management macros ( i.e clock enable and clock disable macros)
- IRQ definitions
- Peripheral Register definition structures
- Peripheral register bit definitions
- Other useful microcontroller configuration macros

![Screenshot from 2023-10-17 21-37-28](https://github.com/PranabNandy/MCU-Driver-Development/assets/80820274/5b6bc920-99fd-4dcf-a272-9c52d7f6992b)
![Screenshot from 2023-10-18 06-19-55](https://github.com/PranabNandy/MCU-Driver-Development/assets/80820274/c793a29b-1238-4231-b82b-e197c9a22f68)
![Screenshot from 2023-10-18 06-22-31](https://github.com/PranabNandy/MCU-Driver-Development/assets/80820274/fb91d82e-717e-499e-91ea-c86d97b62058)

**GPIO Pin Interrupt Configuration**
- Pin must be in input configuration
- Configure the edge trigger (RT,FT,RFT)
- Enable interrupt delivery from peripheral to the processor (on peripheral side)
- Identify the IRQ number on which the processor accepts the interrupt from that pin
- Configure the IRQ priority for the identified IRQ number (Processor side)
- Enable interrupt reception on that IRQ number (Processor side)
- Implement IRQ handler

![Screenshot from 2023-10-18 06-53-36](https://github.com/PranabNandy/MCU-Driver-Development/assets/80820274/4e9b7e31-ca9f-48e5-82aa-ffb4a91381ab)
