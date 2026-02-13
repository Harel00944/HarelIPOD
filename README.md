# HarelIPOD
 PCB Design of IPOD System Board integrating STM32F405  , GNSS, IMU, TFT display, SD card, SPI Flash and VS1053 audio codec with  USB control interface.


The board is structured around a central STM32F405 microcontroller acting as system controller.

<img width="1272" height="893" alt="image" src="https://github.com/user-attachments/assets/88cb897c-82b5-44ac-9cd9-7bfcd06aa8b2" />

Main Functional Blocks:
STM32F405 MCU
GNSS module (UART interface) With Antenna
 IMU 9DOF (I2C interface)
ST7735 TFT display (SPI interface)
VS1053 audio codec (SPI interface)
SD card (SDIO interface)
SPI Flash memory
USB control interface (Also Optionakl UART )
Push Buttoms
3 LDOs For PDN


