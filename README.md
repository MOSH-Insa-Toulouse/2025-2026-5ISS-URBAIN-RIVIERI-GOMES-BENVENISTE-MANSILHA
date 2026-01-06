# 2025-2026-5ISS-URBAIN-RIVIERI-GOMES-BENVENISTE-MANSILHA
## Introduction

The objective of this project is to develop an electronic card on which we have integrated a gas sensor manufactured in the clean room at AIME (Inter-University Micro-Nano Electronics Laboratory). The electronic board includes an analog circuit for conditioning the sensor signal, a microcontroller (ESP32) for receiving the conditioned sensor signal and communicating with the other components on the board, a LoRa module for sending sensor data over a LoRa network using Chirpstack, and a buzzer to alert when a gas concentration threshold has been exceeded.

## Amplification and Conditionning stage: design and simulation

As part of this project, one part was dedicated to designing a stage for conditioning/amplifying the signal delivered by the gas sensor. This signal, which is processed by the ESP32-WROOM microcontroller ADC, must be readable and processable by the latter. To do this, the conditioning stage was designed around the component **LTC1050**, which was used because It has a really low input voltage offset as well as a good common-mode tolerance and relatively low voltage drift maintain the integrity and accuracy of the 10mV voltage measured at the terminals of R1. This is the schematic we get on LTSpice: 

<img width="1600" height="620" alt="ltspice_trans_impedance_amplifier" src="https://github.com/user-attachments/assets/e0cb9cca-ed16-45b4-8cee-7cf81f160eff" />

To ensure the full integrity of the signal and to ensure a good measurement of the signal for 

<img width="311" height="143" alt="ltspice_fc_table" src="https://github.com/user-attachments/assets/fb7688a2-4cde-467b-be0f-f81614f67151" />
