# RF-Climate-Transmission
This small project is about wireless climate monitoring system.
The working pricniple is based on reading data from climate sensors and sending them to another device with the help of RF communication. 
Transmitter reads sensor data and sends via NRF24L01.
Receiver displays live values on OLED display.

## Hardware
- ESP32-38-pin (transmitter + receiver)
- NRF24L01 radio modules
- DHT11/DHT22 sensor
- SSD1306 OLED display

## Wiring

This project uses two separate ESP32 boards:

- **TX (Transmitter):** reads the flame, light, temperature, humidity, and gas sensors, then sends the data wirelessly.
- **RX (Receiver):** receives the sensor data through the NRF24L01 and displays it on the OLED.

Each board should have its **own battery and power switch**, allowing both devices to work wirelessly without a USB cable.

---

## TX (Transmitter)

### NRF24L01 → ESP32

| NRF24L01 | ESP32 |
|----------|-------|
| VCC | 3.3V |
| GND | GND |
| CE | GPIO 4 |
| CSN | GPIO 5 |
| SCK | GPIO 18 |
| MOSI | GPIO 23 |
| MISO | GPIO 19 |

### OLED Display

| OLED | ESP32 |
|------|-------|
| VCC | 3.3V |
| GND | GND |
| SDA | GPIO 21 |
| SCL | GPIO 22 |

### Sensors

| Sensor | ESP32 |
|---------|-------|
| Flame Sensor (AO) | GPIO 25 |
| DHT11 Data | GPIO 26 |
| Light Sensor (AO) | GPIO 35 |
| MQ-2 Gas Sensor (AO) | GPIO 34 |

---

## RX (Receiver)

### NRF24L01 → ESP32

| NRF24L01 | ESP32 |
|----------|-------|
| VCC | 3.3V |
| GND | GND |
| CE | GPIO 2 |
| CSN | GPIO 15 |
| SCK | GPIO 18 |
| MOSI | GPIO 23 |
| MISO | GPIO 19 |

### OLED Display

| OLED | ESP32 |
|------|-------|
| VCC | 3.3V |
| GND | GND |
| SDA | GPIO 4 |
| SCL | GPIO 5 |
