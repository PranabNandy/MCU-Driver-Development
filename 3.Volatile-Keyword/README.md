Now, we have  to understand How GPIO pin interrupts the processor?
![Screenshot from 2023-09-27 23-09-45](https://github.com/PranabNandy/MCU-Driver-Development/assets/80820274/941c0f12-3947-4d46-9d7a-b82157a5b2c3)

- whats the design?
- How the vendor delivers the **GPIO** interrupt to the processor?

- Some peripherals deliver their interrupt to the **NVIC** over the **EXTI line**
![Screenshot from 2023-09-27 23-12-49](https://github.com/PranabNandy/MCU-Driver-Development/assets/80820274/b8e3480f-89cf-4679-8072-d7b6d17d413c)


- Some peripherals deliver their interrupt directly to **the NVIC**
- this is the design of STM. you may find some other design in TI


### Button Interrupt
#### How does a button issue interrupt to the processor in STM32? (main.c)
-  the button is connected to a **GPIO pin** of the microcontroller
-  the GPIO pin should be configured to input mode
-  the link between a **GPIO port** and the relevant **EXTI( EXTI0 or EXTI1)** line must be established using the **SYSCFG_EXTICRx** register
-  
<p align="center"> <img width="700" height="500" src="https://github.com/PranabNandy/MCU-Driver-Development/assets/80820274/8f7d0cf6-bea5-412c-9b0a-ca447a826cd8"  /> </p>

-  Configure the **trigger detection (failing/rising/both)** for **relevant EXTI** line (This is done via **EXTI controller register**) 
-  Implement the **interrupt handler** to service the interrupt 

<p align="center"> <img width="300" height="200" src="https://github.com/PranabNandy/MCU-Driver-Development/assets/80820274/3f694a66-af48-4d38-9cc3-4a014b02aacc"  /> </p>

![Screenshot from 2023-09-27 23-29-59](https://github.com/PranabNandy/MCU-Driver-Development/assets/80820274/6b2ab30e-4f0d-4008-8820-43fe9a17596e)

===================================================================================
