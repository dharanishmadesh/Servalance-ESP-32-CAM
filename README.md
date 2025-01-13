# ESP32-CAM Telegram Bot

This project demonstrates how to use the ESP32-CAM module to create a Telegram bot that can capture and send photos, read sensor data, and toggle the flash LED via Telegram commands. It also includes motion detection functionality to send photos automatically when motion is detected.

## Features

- **Photo Capture**: Capture and send photos via Telegram.
- **Motion Detection**: Automatically detect motion and send alerts with photos.
- **Sensor Readings**: Retrieve temperature and humidity data from the BME280 sensor.
- **Flash Control**: Toggle the ESP32-CAM's flash LED via Telegram.
- **User Authentication**: Only authorized users can interact with the bot.

## Hardware Requirements

- ESP32-CAM module (AI-Thinker model recommended)
- PIR motion sensor
- BME280 sensor (for temperature and humidity readings)
- Power supply (e.g., USB adapter or battery)

## Software Requirements

- Arduino IDE
- Required libraries:
  - [UniversalTelegramBot](https://github.com/witnessmenow/Universal-Arduino-Telegram-Bot)
  - [ArduinoJson](https://github.com/bblanchon/ArduinoJson)
  - [SparkFun BME280](https://github.com/sparkfun/SparkFun_BME280_Arduino_Library)

## Wiring Diagram

### ESP32-CAM Pin Configuration

| **ESP32-CAM Pin** | **Component**         | **Description**           |
|-------------------|-----------------------|---------------------------|
| GPIO14            | BME280 SDA           | I2C Data Line             |
| GPIO15            | BME280 SCL           | I2C Clock Line            |
| GPIO13            | PIR Sensor Output    | Motion Detection Input    |
| GPIO4             | Flash LED            | Toggleable Flashlight     |

## Setup Instructions

1. **Install Libraries**:
   - Open the Arduino IDE.
   - Go to **Sketch > Include Library > Manage Libraries**.
   - Search for and install `UniversalTelegramBot`, `ArduinoJson`, and `SparkFun BME280`.

2. **Configure Wi-Fi and Telegram**:
   - Replace the placeholders in the code with your Wi-Fi credentials (`ssid` and `password`).
   - Get your Telegram bot token by creating a bot using [@BotFather](https://core.telegram.org/bots#botfather) on Telegram.
   - Replace `BOTtoken` and `chatId` in the code with your bot token and chat ID.

3. **Upload the Code**:
   - Connect the ESP32-CAM to your computer using a USB-to-TTL converter.
   - Select the appropriate board and port in the Arduino IDE.
   - Upload the code.

4. **Run the Bot**:
   - Once uploaded, monitor the Serial Monitor for debugging.
   - Use the Telegram app to interact with the bot.

## Commands

- `/start` - Displays a welcome message with available commands.
- `/photo` - Captures and sends a photo.
- `/flash` - Toggles the flash LED.
- `/readings` - Sends temperature and humidity readings.

## Additional Notes

- Ensure your ESP32-CAM is connected to a stable Wi-Fi network.
- The motion sensor triggers photo capture when movement is detected.
- Only authorized users (based on `chatId`) can interact with the bot.

## Troubleshooting

- **Camera Initialization Failed**:
  - Ensure the camera is properly connected to the ESP32-CAM module.
  - Use an AI-Thinker model for compatibility.

- **Wi-Fi Connection Issues**:
  - Double-check your SSID and password.
  - Ensure the ESP32-CAM is within the Wi-Fi signal range.

- **Telegram Bot Not Responding**:
  - Verify the bot token and chat ID.
  - Ensure the ESP32-CAM has internet access.

## License

This project is licensed under the MIT License. Feel free to use and modify the code for personal and commercial purposes.

---

Developed with ❤️ by dharanish.
