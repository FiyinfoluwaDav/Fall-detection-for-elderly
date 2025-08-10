# 📍 Fall Detection System using ESP8266 & MPU-6050

This project implements a **fall detection system** using an **ESP8266 microcontroller** and an **MPU-6050 accelerometer & gyroscope sensor**.  
It detects sudden falls based on acceleration and orientation changes, then sends an alert via **IFTTT Webhooks** over Wi-Fi.

---

## ✨ Features
- 📊 Reads accelerometer and gyroscope data from MPU-6050.
- ⚡ Detects falls using a **three-trigger logic**:
  1. Low acceleration threshold (possible fall start).
  2. High acceleration threshold (impact detection).
  3. Orientation change detection (body position after fall).
- 🌐 Sends an **IFTTT event** when a fall is confirmed.
- 📶 Connects to Wi-Fi for real-time notifications.

---

## 🛠 Hardware Requirements
- **ESP8266** (NodeMCU, Wemos D1 Mini, etc.)
- **MPU-6050** accelerometer/gyroscope module
- Jumper wires
- Breadboard (optional)

---

## 🔌 Circuit Diagram
| MPU-6050 Pin | ESP8266 Pin |
|--------------|-------------|
| VCC          | 3.3V        |
| GND          | GND         |
| SCL          | D1 (GPIO5)  |
| SDA          | D2 (GPIO4)  |

---

## 📦 Software Requirements
- **Arduino IDE**
- ESP8266 board package
- Libraries:
  - `Wire.h`
  - `ESP8266WiFi.h`

---

## ⚙️ Setup & Configuration
1. **Install Arduino IDE** and add ESP8266 board support.
2. Install required libraries (`Wire`, `ESP8266WiFi`).
3. Connect the MPU-6050 to your ESP8266 as per the wiring table.
4. In the code:
   - Replace `--Enter WIFI Name--` with your Wi-Fi SSID.
   - Replace `--Enter WIFI Password--` with your Wi-Fi password.
   - Replace `--Enter Private Key from IFTTT--` with your **IFTTT Webhooks key**.
5. Upload the code to your ESP8266.

---

## 🌐 IFTTT Setup
1. Go to [IFTTT](https://ifttt.com/maker_webhooks).
2. Create a new **Applet**:
   - **If This:** Choose Webhooks → Event Name: `fall_detected`
   - **Then That:** Select desired notification method (e.g., SMS, Email).
3. Copy your **Webhook key** and paste it in the code.

---

## 📡 How It Works
1. MPU-6050 continuously measures acceleration & rotation.
2. Algorithm detects:
   - Initial low acceleration (fall start).
   - Sudden high acceleration (impact).
   - Change in orientation (post-fall position).
3. If all three triggers are met, an event is sent via IFTTT.
4. You receive an alert on your chosen device.

---

## 📷 Demonstration
![Circuit Diagram](https://raw.githubusercontent.com/FiyinfoluwaDav/Fall-detection-for-elderly/main/Circuit%20diagram.jpg)



---

## 📝 Example Serial Output

TRIGGER 1 ACTIVATED
TRIGGER 2 ACTIVATED
TRIGGER 3 ACTIVATED
FALL DETECTED
