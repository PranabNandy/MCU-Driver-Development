### Now, we have  to understand How GPIO pin interrupts the processor?

<p align="center"> <img width="600" height="400" src="https://github.com/PranabNandy/MCU-Driver-Development/assets/80820274/941c0f12-3947-4d46-9d7a-b82157a5b2c3"  /> </p>

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

![Screenshot from 2023-09-27 23-40-26](https://github.com/PranabNandy/MCU-Driver-Development/assets/80820274/50e7e1cd-1c30-4b1c-b7b1-a8a212803719)



-  Configure the **trigger detection (failing/rising/both)** for **relevant EXTI** line (This is done via **EXTI controller register**) 
-  Implement the **interrupt handler** to service the interrupt 

<p align="center"> <img width="300" height="200" src="https://github.com/PranabNandy/MCU-Driver-Development/assets/80820274/3f694a66-af48-4d38-9cc3-4a014b02aacc"  /> </p>

![Screenshot from 2023-09-27 23-29-59](https://github.com/PranabNandy/MCU-Driver-Development/assets/80820274/6b2ab30e-4f0d-4008-8820-43fe9a17596e)

===================================================================================
### Without using volatile keyword
![Screenshot from 2023-09-30 07-07-52](https://github.com/PranabNandy/MCU-Driver-Development/assets/80820274/0f24b129-005d-4fc4-9775-5ccdc76141a6)
![Screenshot from 2023-09-25 23-08-41](https://github.com/PranabNandy/MCU-Driver-Development/assets/80820274/b45a420c-7db9-46ce-b233-6afc35c14141)



### volatile keyword
![Screenshot from 2023-09-30 07-16-13](https://github.com/PranabNandy/MCU-Driver-Development/assets/80820274/0340466d-2037-4175-9b9b-de0a012aec2a)

![Screenshot from 2023-09-25 23-11-32(1)](https://github.com/PranabNandy/MCU-Driver-Development/assets/80820274/0d3f2fb4-7622-4504-9c05-15235f18f5e2)
