# MCU-Driver-Development




**TRM:** Information about Peripherals, peripheral implementtaiton, register sets, register config, clocks

**Datasheet:** Information about Pin details, electrical charecteristic

![Screenshot from 2023-09-26 11-32-29](https://github.com/PranabNandy/MCU-Driver-Development/assets/80820274/ee2dc599-4d9d-4584-a7cf-77f843c5e6b5)

### Function Block of STM32F40XX
![Screenshot from 2023-09-20 21-28-41](https://github.com/PranabNandy/MCU-Driver-Development/assets/80820274/8e110e28-376f-41fd-91a4-ee0afdfcbf5d)

### STM32CubeIDE

![Screenshot from 2023-09-23 01-45-36](https://github.com/PranabNandy/MCU-Driver-Development/assets/80820274/4a7fd8b9-c27b-4779-8358-0ca5f457258f)

# Boot Up:
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



Now we know,
-  How to flash a device
-  How to enable a peripheral
