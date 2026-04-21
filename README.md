# PT100 4–20mA Temperature Monitoring using STM32F446RE

## 📌 Overview

This project reads temperature from a PT100 sensor using a 4–20mA transmitter and converts it into temperature using STM32F446RE ADC.

## ⚙️ Hardware Used

* STM32F446RE (Nucleo / bare board)
* PT100 RTD Sensor
* 4–20mA Transmitter
* 220Ω Resistor (current to voltage conversion)
* USB to TTL Converter (for serial monitor)

## 🔌 Working Principle

* 4–20mA current loop converted to voltage using 220Ω resistor
* ADC reads voltage (0–3.3V)
* Converted to current and then temperature

## 📐 Formula

* Voltage = ADC × 3.3 / 4095
* Current (mA) = Voltage / 220 × 1000
* Temperature (°C) = (Current - 4) × (100 / 16)

## ⚠️ Limitation

Using 220Ω resistor causes saturation above ~15mA (~68°C)

## 🔧 Pin Configuration

* PA0 → ADC Input
* PA2 → UART TX

## 🖥️ Serial Output Example

Voltage: 1.19 V | Current: 5.42 mA | Temp: 30.93 °C

## 🚀 Future Improvements

* Use 165Ω resistor for full range
* Add filtering (moving average)
* DMA + UART interrupt
* IoT integration (MQTT)

## 👨‍💻 Author

Md. Samiul Islam Sabbir
