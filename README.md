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




Design Process & System Validation
Proof of Concept (POC) Phase

The project initially started as a Proof of Concept using the MCU board developed during my final electrical engineering  project (MCU Board) .
<img width="923" height="911" alt="image" src="https://github.com/user-attachments/assets/e01bfb94-5182-45db-a689-c20272f94df7" />

This stage was focused on validating the core system architecture and firmware framework before committing to a full custom PCB design.

The POC stage allowed:

Validation of peripheral communication (UART, SPI, I2C, SDIO)

Early firmware driver development

Audio codec functional testing

GNSS and IMU data acquisition validation

USB-CDC control interface testing

Once the system functionality was verified at the board level, the project transitioned into a full custom PCB design phase.

PCB Design Phase

After successful feasibility validation, a complete PCB design process was initiated.

The board was designed with strong emphasis on:

Proper Power Distribution Network (PDN) architecture

Controlled grounding strategy

Stable clock routing

SPI and SDIO signal integrity considerations

Decoupling capacitor placement optimization

Clean return current paths

Functional interface isolation where required

Logical and serviceable component placement

The objective was to design a reliable multi-interface embedded system board capable of operating all subsystems simultaneously without signal integrity degradation.

Particular care was taken to ensure proper integrity across:

SDIO interface

Multiple SPI buses

Audio streaming path

GNSS UART interface

I2C IMU communication

Industrial Design Concept

The mechanical concept was inspired by a compact handheld device, similar in form factor philosophy to a portable media player.

Design considerations included:

Side-mounted power button

USB Type-C charging and data interface

Dedicated headphone output

External antenna connector for GNSS

Front-facing TFT display

The component placement strategy aimed to reflect a consumer-style device layout while maintaining professional board-level routing constraints.

System Performance & Functional Validation

The system has been successfully powered, validated and tested.

Verified subsystems include:

GNSS receiver operational and providing valid geographic position data

IMU delivering stable Yaw, Pitch and Roll orientation data

SD Card operational with FATFS integration

MP3 playback from SD via VS1053 audio codec

Clean and stable audio output through headphone interface

SPI Flash functional and available for future data logging implementation

TFT display operating correctly with graphical output

The SPI Flash is intended for future expansion as a data logger, enabling cross-referenced logging between u-blox GNSS data and IMU orientation data.

The TFT display infrastructure is fully operational and prepared for future UI features such as song list browsing and system status visualization.

Push-button inputs are implemented in hardware but have not yet undergone full validation testing.

Performance Evidence

Live GNSS fix

IMU orientation output

Audio playback confirmation

Display functionality


PCB Layer Stack-Up

The board was designed as a 4-layer PCB and manufactured by JLCPCB.

Layer structure:

Layer 1 – Signals

Layer 2 – Solid GND plane

Layer 3 – Power plane

Layer 4 – Signals

This stack-up was selected to provide stable return paths, improved EMI performance and controlled impedance routing while maintaining reasonable manufacturing cost.

Controlled Impedance & Routing Considerations

Special attention was given to high-speed and RF traces:

The USB interface between the USB Type-C connector and the STM32F405 was routed as a 90Ω differential pair, with length matching, tight coupling and continuous GND reference.

The RF trace between the u-blox GNSS module and the external antenna connector was routed as a 50Ω controlled impedance microstrip, referenced to a solid ground plane to preserve signal quality and minimize reflections.

General routing principles included:

Proper PDN structure with a dedicated power layer

Solid uninterrupted GND reference

Correct decoupling placement near each IC

Clean placement strategy to support signal integrity

<img width="1189" height="793" alt="image" src="https://github.com/user-attachments/assets/44a7a26b-583d-498c-9b92-7fbc977cdada" />
<img width="1193" height="786" alt="image" src="https://github.com/user-attachments/assets/b824f920-dafe-4f04-bd50-41f3e0c5fbb5" />
<img width="1192" height="790" alt="image" src="https://github.com/user-attachments/assets/ec14622f-ddd9-4a2f-aa24-84973a94cd3a" />
<img width="1198" height="790" alt="image" src="https://github.com/user-attachments/assets/0bd984b1-01f0-4362-ad71-fb06cb33a00c" />
<img width="1101" height="719" alt="image" src="https://github.com/user-attachments/assets/f874bba5-9146-47b2-b480-84eaa8d0283c" />







