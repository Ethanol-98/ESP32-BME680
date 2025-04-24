# Environment Station

A Wi-Fi–enabled environmental data logger using an ESP32 and BME680 sensor. It serves a web interface and streams real-time temperature, humidity, pressure, and gas resistance readings over WebSockets.

## Features

- **Standalone Wi-Fi Access Point**: ESP32 hosts its own network (`Environment` / `ESP32pass`).
- **Secure Web UI**: HTTP basic authentication (`admin`/`ESP32`).
- **Real-Time Charts**: Live, lightweight line charts powered by Chart.js, updated via WebSockets.
- **Configurable Update Interval**: Default 2 seconds between readings.
- **Easy Integration**: All HTML/JS embedded in flash; no external server dependencies.

## Hardware Requirements

- ESP32 development board (ESP32-D, DevKitC, etc.)
- Adafruit BME680 sensor (I2C)
- Standard micro‑USB cable for power and programming

## Wiring

```
BME680 VIN → ESP32 3.3 V
BME680 GND → ESP32 GND
BME680 SDA → ESP32 GPIO 21
BME680 SCL → ESP32 GPIO 22
```

## Software Setup

1. Install Arduino IDE (or Arduino CLI).
2. In **Boards Manager**, install **esp32 by Espressif Systems**.
3. In **Library Manager**, install:
   - Adafruit BME680
   - Adafruit Unified Sensor
   - Adafruit BusIO
   - AsyncTCP
   - ESPAsyncWebServer

## Usage

1. Open the `Environment Station` sketch in Arduino IDE.
2. Update SSID/password or credentials if desired.
3. Select your ESP32 board and COM port.
4. Click **Verify** then **Upload**.
5. Open Serial Monitor at 115200 baud to see AP IP.
6. Connect to Wi-Fi network `Environment` (password `ESP32pass`).
7. Browse to `http://192.168.4.1/`, log in with **admin** / **ESP32**.
8. View live charts updating every 2 seconds.

## Customization

- **Change Wi-Fi Credentials**: Modify `ap_ssid` / `ap_passwd`.
- **Adjust Update Interval**: Change `updateInterval` in milliseconds.
- **Chart Appearance**: Tweak Chart.js options in HTML block.

## License

MIT License. Feel free to fork and extend!

