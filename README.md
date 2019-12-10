# Temp-humidity-2016

## Introduction

Humidity and temperature are common parameters to measure environmental conditions. This condition can be an essential when developers want to build up some system for fire alarm or triggering some action based on the environmental temperature or humidity.
In this Arduino based project we are going to measure ambient temperature and humidity and display it on a 16x2 LCD screen. A combined temperature and humidity sensor DHT11 are used with Arduino Uno to develop this Celsius and Fahrenheit scale thermometer and percentage scale humidity measurement project.
This document will provide instructions about which the electrical components that is required and how the device can be constructed. Additionally, the codes and explanations will be included in the latter part.

## Component

1. Arduino UNO
2. Solderless Breadboard;
3. Jumper wires;
4. DHT11 sensor module;
5. Tactile button module;
6. Tactile button;
7. LCD display;
8. I2C bus expansion board PCF8574*I2C for LCD;
*9. (optional)9V-battery & battery case;*

![arduino, breadboard and wires](/captured/arduino,breadboard&wires.jpg)

![sensors](/captured/sensors.jpg)

![battery](/captured/battery.jpg)

## Connection

### LCD & expansion board PCF8574*I2C

In order to control the LCD display with I2C connection, we align the LCD 16 pins with the 16 pins on the I2C expansion board (Either placing them on the breadboard or solder the LCD with the pins on expansion board).

![LCD and I2C expansion board](/captured/connection_LCD_1.jpg)

On expansion board, there are four pins, use jumper wires to connect with Arduino:
GND to GND:

- Vcc to 5V
- to Analog 4
- SCL to Analog 5

![connection with I2C bus](/captured/connection_LCD_2.jpg)

### Temp&Humidity sensors and tactile switch

DHT11 sensor module has 3 pins ( GND, Vcc, Vout); the Vout pin with digital pin 6 on Arduino

![connection with DHT11 sensor](/captured/DHT11_connection.jpg)

Tactile Button module connect with Arduino digital pin 2.

![tactile button](/captured/button_connection.jpg)

### Power supply

- Place battery in the case and hook the cable to the power supply module (PSM). 
- In order to supply power to Arduino, we can either:
- use jumper wires to connect 5V and GND pin of Arduino to respective pins (+), (-) on PSM.
- use usb cable to hook Arduino to the PSM.

![setup](/captured/final_1.jpg)

## Compiling

There are two sub project:

- I2C scanner
- Weather station

Before compiling the ”weather_station” sketch to Arduino, use ”i2c_scanner” project to retreive the address of the I2C bus interface while connecting expansion board on then replace the found address to the following line in Weather_station sketch:

`LiquidCrystal_I2C lcd([address], 2, 1, 0, 4, 5, 6, 7, 3, POSITIVE);`

Then compile the codes in Weather_station and test the product.

## Result

![tempture & humidity readings displayed on LCD](/captured/temp&humidity.jpg)
<https://youtu.be/NbEj2KyAm_U>