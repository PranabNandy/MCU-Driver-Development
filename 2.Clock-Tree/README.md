# MCU-Clock-Tree


<p align="center"> <img width="600" height="500" src="https://github.com/PranabNandy/MCU-Driver-Development/assets/80820274/3f694a66-af48-4d38-9cc3-4a014b02aacc"  /> </p>

### Clock Sources:
1) Crystal Oscillator ( external to the MCU)
2) The RC Oscillator (Internal to the MCU)
3) The PLL ( Internal to the MCU)

![Screenshot from 2023-09-23 01-59-13](https://github.com/PranabNandy/MCU-Driver-Development/assets/80820274/81f403a1-7b06-4581-91cc-e7b080e70726)

### HSE:
-  HSE can be provided to the MCU via a crystal Oscillator external or source (from another circuit or another MCU) 
-  On the STM32-DISC board, HSE is 8 MHz provided by the **onboard crystal Oscillator.**
-  On NUCLEO board,  HSE is of 8MHz pulled from ST-LINK circuit.

### Peripheral Clock Configuration
-  In modern MCUs, before using any peripheral, **you must enable its peripheral clock using peripheral clock registers**
-  By default, peripheral clocks of all most all peripherals will be **disabled** to **save power**
-  A peripheral won't take or respond to your configuration values until you enable its peripheral clock 
- In STM32 microcontrollers, peripheral clocks are managed through **RCC registers** 

![Screenshot from 2023-09-24 00-36-25](https://github.com/PranabNandy/MCU-Driver-Development/assets/80820274/8f7d0cf6-bea5-412c-9b0a-ca447a826cd8)
