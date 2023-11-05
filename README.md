# MCU-Driver-Development




**TRM:** Information about Peripherals, peripheral implementtaiton, register sets, register config, clocks

**Datasheet:** Information about Pin details, electrical charecteristic

![Screenshot from 2023-09-26 11-32-29](https://github.com/PranabNandy/MCU-Driver-Development/assets/80820274/ee2dc599-4d9d-4584-a7cf-77f843c5e6b5)

### Function Block of STM32F40XX
![Screenshot from 2023-09-20 21-28-41](https://github.com/PranabNandy/MCU-Driver-Development/assets/80820274/8e110e28-376f-41fd-91a4-ee0afdfcbf5d)

### STM32CubeIDE

![Screenshot from 2023-09-23 01-45-36](https://github.com/PranabNandy/MCU-Driver-Development/assets/80820274/4a7fd8b9-c27b-4779-8358-0ca5f457258f)


# Summary:
![Screenshot from 2023-11-05 17-12-28](https://github.com/PranabNandy/MCU-Driver-Development/assets/34576104/bf68678c-43da-4af8-b61b-eebf8e67dc79)


## Boot Up:
For ARM you need to setup the vector table in the **reset handler.**

You need to locate the vector table at the offset directed by the **VTOR register** (Vector Table Offset Register)/ **VBAR in Arm-A.**

When ARM cortex boots up, it expects the first memory pointer by VTOR should be **( SP + reset Handler).**

SP will store CPU core's SP and reset vector/handler to its PC.

Reset vector is the address to ISR that the core has to execute.



![Screenshot from 2023-11-02 21-38-00](https://github.com/PranabNandy/MCU-Driver-Development/assets/34576104/0eef13a0-b309-40fb-9df8-21dd6bd19915)


VTOR has point to a defined location.


We point VTOR to the starting address of **Flash Memory (0x0800_0000)**

![Screenshot from 2023-11-02 23-10-56](https://github.com/PranabNandy/MCU-Driver-Development/assets/34576104/5705d8c7-a48f-4496-b59d-9b4697568448)


![Screenshot from 2023-11-05 14-09-25](https://github.com/PranabNandy/MCU-Driver-Development/assets/34576104/967f899e-5c54-45fd-aee4-e894f30f6db1)

### Clock Gating

![Screenshot from 2023-11-05 14-28-54](https://github.com/PranabNandy/MCU-Driver-Development/assets/34576104/e8408f46-2cea-4c89-abee-fedd36c36119)


### Clock Enable
Actually we need to go to APH1 peripheral clock to enable the GPIOA

![Screenshot from 2023-11-05 14-56-43](https://github.com/PranabNandy/MCU-Driver-Development/assets/34576104/b829e7e5-78ed-4dbd-86b6-c2fdd7f25084)

![Screenshot from 2023-11-05 14-58-08](https://github.com/PranabNandy/MCU-Driver-Development/assets/34576104/c398b855-9d23-4236-aae1-38dbb44a2953)

- So far we have completed the Enabling of GPIOA

### GPIO Mode setting 
![Screenshot from 2023-11-05 16-48-48](https://github.com/PranabNandy/MCU-Driver-Development/assets/34576104/6c21c097-12b6-4917-a810-f2adaef60b44)
![Screenshot from 2023-11-05 16-48-32](https://github.com/PranabNandy/MCU-Driver-Development/assets/34576104/c7628db2-3686-4c8a-a150-54d0a9812877)
![Screenshot from 2023-11-05 17-06-29](https://github.com/PranabNandy/MCU-Driver-Development/assets/34576104/61939568-5ff3-4c65-a788-e4801f001c6e)

### RCC Register Map
![Screenshot from 2023-11-05 17-15-36](https://github.com/PranabNandy/MCU-Driver-Development/assets/34576104/f12387a3-22df-4fd0-b0c8-d662576ce189)

**Now we know,**
-  How to flash a device
-  How to enable a peripheral
-  Set the Mode bit (in/out)
-  Put the data on output data register
