# 2025-2026-5ISS-URBAIN-RIVIERI-GOMES-BENVENISTE-MANSILHA
## Introduction

The objective of this project is to develop an electronic card on which we have integrated a gas sensor manufactured in the clean room at AIME (Inter-University Micro-Nano Electronics Laboratory). The electronic board includes an analog circuit for conditioning the sensor signal, a microcontroller (ESP32) for receiving the conditioned sensor signal and communicating with the other components on the board, a LoRa module for sending sensor data over a LoRa network using Chirpstack, and a buzzer to alert when a gas concentration threshold has been exceeded.

## Amplification and Conditionning stage: design and simulation

As part of this project, one part was dedicated to designing a stage for conditioning/amplifying the signal delivered by the gas sensor. This signal, which is processed by the ESP32-WROOM microcontroller ADC, must be readable and processable by the latter. To do this, the conditioning stage was designed around the component **LTC1050**, which was used because It has a really low input voltage offset as well as a good common-mode tolerance and relatively low voltage drift maintain the integrity and accuracy of the 10mV voltage measured at the terminals of R1. This is the schematic we get on LTSpice: 

<img width="1600" height="620" alt="ltspice_trans_impedance_amplifier" src="https://github.com/user-attachments/assets/e0cb9cca-ed16-45b4-8cee-7cf81f160eff" />

To ensure the full integrity of the signal and to ensure a good measurement of the signal for 

<img width="311" height="143" alt="ltspice_fc_table" src="https://github.com/user-attachments/assets/fb7688a2-4cde-467b-be0f-f81614f67151" />



## Electrical schematic and PCB design

After all these simulation and in parallel with the software development of the ESP32 and its interaction with the LoRa module, the electronic board diagram was entered and the complete PCB routing was carried out. The electronic board diagram includes female connectors to facilitate the integration of the microcontroller and the LoRa module. With that a two-pins connector is included to ensure the correct power supply to the gas sensor's heating element. A buzzer has also been added to provide audible alerts when gas is detected, as well as a button for various uses, such as sending data or requesting a connection with the LoRa gateway. 

# Here is the electrical schematic of the board:

<img width="1989" height="1099" alt="Capture d&#39;écran 2026-01-06 163123" src="https://github.com/user-attachments/assets/c697286b-230c-4aa2-9af6-06584935a82d" />

# We gathered all the components we used for this board: 

| Reference        | Quantity | Value / Description         | 
|------------------|----------|-----------------------------|
| BZ1              | 1        | Buzzer                      | 
| C1, C3, C4       | 3        | 100 nF                      | 
| C2               | 1        | 1 µF                        | 
| J1               | 1        | Connector  1x02             | 
| J2               | 1        | Connector  module LoRa      | 
| J3               | 1        | Connector  femelle ESP      | 
| R1, R6, R8       | 3        | 10 kΩ                       | 
| R2, R4           | 2        | 100 kΩ                      | 
| R3, R5           | 2        | 1 kΩ                        | 
| SW2              | 1        | Push button                 | 
| U2               | 1        | Gaz Sensor                  | 
| U3               | 1        | LTC1050CN8-PBF (AOP)        | 

The electronic board diagram done, the PCB routing has been done and the goal was to minimized the size of the whole card. As a result, we decided to route on both sides (top and bottom) to save space and make it compact and to outsource PCB manufacturing to JLC PCB to have a more clean product. 

# Here is the final PCB layout: 

<img width="712" height="1153" alt="Capture d&#39;écran 2026-01-06 163302" src="https://github.com/user-attachments/assets/fa7053f5-c1f2-408f-9439-61978cafb3b5" />





