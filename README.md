# Photonic Beer Bong 🍺⚡️

A high-precision, Bluetooth-enabled smart beer bong powered by an ESP32. It uses the physics of Total Internal Reflection (TIR) to detect fluid levels, accurately timing how fast a user drinks, and broadcasts the results to a custom web app leaderboard.

## ✨ Features
* **Physics-Based Sensor:** Uses TIR to detect the difference between liquid (beer) and air, starting and stopping the timer automatically.
* **Millisecond Precision:** Non-blocking C++ code ensures maximum polling rates for highly accurate chug times.
* **Wireless Dashboard:** Connects via Bluetooth Low Energy (BLE) to a custom web app.
* **Event & Leaderboard Management:** Tracks participant names, saves high scores to your device's local storage, and allows you to switch between different parties/events.
* **Remote Power Control:** Turn the LEDs and sensor logic on or off directly from your phone to save power between uses.

## 🛠 Hardware Required
* **Microcontroller:** ESP32 (Features built-in BLE)
* **Display:** 128x64 OLED Screen (SSD1306 via I2C)
* **Light Source:** WS2812B LED Strip 
* **Sensor:** Analog Light/Optical Sensor (Pin 34)

## 📱 How to Use the App (iOS)
Because Apple restricts standard browsers from accessing Web Bluetooth, iPhone users need a WebBLE browser.
1. Download **Bluefy** from the iOS App Store (Free).
2. Open Bluefy and navigate to the GitHub Pages URL for this repository.
3. Power on the ESP32.
4. Tap **Connect via Bluetooth** and select `PhotonicBong`.
5. Enter names, chug, and track your high scores!

## ⚙️ Calibration
If the sensor triggers too early or too late, adjust the `TIR_THRESHOLD` variable in the Arduino code. 
* Current default: `1500`
* Readings **below** the threshold = Liquid detected (Timer Starts)
* Readings **above** the threshold = Air detected (Timer Stops)
