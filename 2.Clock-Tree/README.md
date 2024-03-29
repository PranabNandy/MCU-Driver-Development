# MCU-Clock-Tree




### Clock Sources:
1) Crystal Oscillator ( external to the MCU)
2) The RC Oscillator (Internal to the MCU)
3) The PLL ( Internal to the MCU)

![Screenshot from 2023-09-23 01-59-13](https://github.com/PranabNandy/MCU-Driver-Development/assets/80820274/81f403a1-7b06-4581-91cc-e7b080e70726)

### HSE:
-  HSE can be provided to the MCU via a crystal Oscillator or external source (from another circuit or another MCU) 
-  On the STM32-DISC board, HSE is 8 MHz provided by the **onboard crystal Oscillator.**
-  On NUCLEO board,  HSE is of 8MHz pulled from ST-LINK circuit.

### Peripheral Clock Configuration 
-  In modern MCUs, before using any peripheral, **you must enable its peripheral clock using peripheral clock registers**
-  By default, peripheral clocks of all most all peripherals will be **disabled** to **save power**
-  A peripheral won't take or respond to your configuration values until you enable its peripheral clock 
- In STM32 microcontrollers, peripheral clocks are managed through **RCC registers** 
### Reset and clock control for STM32F42xxx and STM32F43xxx (RCC)
#### Reset
-  There are three types of reset, defined as **system Reset**, **power Reset** and **backup domain Reset**

- **System reset** : A system reset sets all registers to their reset values except the reset flags in the **clock controller CSR register** and the registers in the **Backup domain**
- **Power reset** : A power reset is generated when one of the following events occurs:
```
Power-on/power-down reset (POR/PDR reset) or brownout (BOR) reset When exiting the Standby mode
A power reset sets all registers to their reset values except the Backup domain
```
- **Backup domain reset** : The backup domain reset sets all RTC registers and the RCC_BDCR register to their reset values. The BKPSRAM is not affected by this reset. The only way of resetting the BKPSRAM is through the Flash interface by requesting a protection level change from 1 to 0.
A backup domain reset is generated when one of the following events occurs:
```
1. Software reset, triggered by setting the BDRST bit in the RCC Backup domain control
register (RCC_BDCR).
2. V DD or V BAT power on, if both supplies have previously been powered off.
```
![Screenshot from 2023-09-26 12-18-25](https://github.com/PranabNandy/MCU-Driver-Development/assets/80820274/e7ae4cd3-18cc-46c1-86d7-8a5e5b76b8d9)

=================================================================================

HSI is default clock when STM32 is out of reset **(main_peri_clock.c)**

- Lets take a peripheral, say  **ADA** 
- Lets take some ADC register say **CR1**
- Lets set **SCAN bit to 1**

Must enable its clock first

First check which bus it is connected **(APH2)**

Go to **RCC register** then search for appropiate register like **RCC APH2 peripheral clock** enable register

T bit should always be 1 for Arm cortex M4 processor


=======================================================================================
**(main_HSI_measurement.c)**

Write a program to output HSI clock on MCU pin and measure it using oscilloscope or logic analyzer
- Select the desired clock for the MCOx signal ( MCU clock output)
- Output the MCOx signal on the MCU pin

=======================================================================================

### HSE Measurement: (main_HSE_measurement.c)
-  Enable the HSE clock using HSEON bit (RCC_CR)
-  Wait until HSE clock from the external crystal stabilizes( only if crystal is connected) (Indicates if the high-speed external oscillitor is stable or not)
-  Switch the system clock to HSE (RCC_CFGR)
-   Do MCO1 settings to measure it

=======================================================================================
### Vector Table:
- Table of addresses or pointers
- Addresses of exception handlers ( system expection + interrupts)
![Screenshot from 2023-09-23 02-16-17](https://github.com/PranabNandy/MCU-Driver-Development/assets/80820274/e91230e5-27f7-4d76-bafd-f787dfa67ca7)



