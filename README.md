# 🔌 Arduino Sensor-Based Relay & Buzzer Control System

🎥 **Project Showcase (LinkedIn):**  
👉 https://www.linkedin.com/posts/priyanjall_embeddedsystems-iot-roadsafety-activity-7353774634267303936-SvEN

A real-time Arduino project that detects **button/sensor press duration** and triggers a **relay and buzzer** accordingly.  
This system demonstrates efficient timing using `millis()` instead of blocking delays.

---

## 📌 Overview

This project reads input from a sensor (or push button) and performs actions based on how long the input remains active:

- **Short Press** → No action  
- **Long Press (≥ 3 seconds)** → Relay turns ON  
- **Very Long Press (≥ 6 seconds)** → Buzzer turns ON  

Once the button is released, all outputs reset.

---

## ⚙️ Hardware Requirements

- Arduino Board (Uno / Nano / Mega)
- Push Button or Digital Sensor
- Relay Module
- Buzzer
- Jumper Wires
- Breadboard (optional)

---

## 🔌 Pin Configuration

| Component      | Arduino Pin |
|----------------|------------|
| Sensor Input   | 10         |
| Relay          | 13         |
| Buzzer         | A0         |

---

## 📦 Software Requirements

- Arduino IDE (latest version recommended)

### Installing Libraries

This project uses only built-in Arduino functions.  
For general guidance on installing libraries:

🔗 http://www.arduino.cc/en/Guide/Libraries

---

## 🚀 Working Principle

1. The system continuously reads the sensor state.
2. When the button is pressed:
   - The current time is recorded using `millis()`.
3. The duration of the press is calculated:
   - If duration ≥ **3000 ms** → Relay is activated
   - If duration ≥ **6000 ms** → Buzzer is activated
4. When the button is released:
   - Relay and buzzer are turned OFF
   - Timer resets

---

## 🧠 Key Concepts Used

- Non-blocking timing using `millis()`
- State tracking (previous vs current sensor state)
- Time-based event triggering
- Embedded system control logic

---

## ▶️ How to Run the Project

1. Connect components as per the pin configuration
2. Open the Arduino IDE
3. Upload the code to your Arduino board
4. Open the Serial Monitor (baud rate: `9600`)
5. Press and hold the button:
   - Hold for 3 seconds → Relay ON  
   - Hold for 6 seconds → Buzzer ON  
6. Release the button to reset the system

---

## 🧪 Sample Serial Output

```
Press button
Button pressed
Button long pressed
Button released
```

---

## ⚠️ Important Notes

- Ensure proper power supply for the relay module
- Avoid using `delay()` for better responsiveness
- Timing values can be adjusted in the code:
  ```cpp
  unsigned long minSensorDuration = 3000;
  unsigned long minSensorDuration2 = 6000;
  ```
- For noisy inputs, consider adding debouncing logic

---

## 🚧 Future Enhancements

- Add LCD/OLED display for status output  
- Integrate with IoT (WiFi/Bluetooth control)  
- Use interrupts for faster response  
- Add mobile app control  

---

## 👨‍💻 Author

**Prajwal Sahu**  
B.Tech CSE (Data Science)

---

## ⭐ Support

If you found this project helpful, consider giving it a ⭐ on GitHub.
