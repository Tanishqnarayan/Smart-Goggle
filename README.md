# Smart Goggle – Eye Drowsiness Detection using ESP32

## Project Description
This project implements a real-time eye drowsiness/dizziness detection system using an ESP32 and an IR eye blink sensor. The system detects prolonged eye closure and activates an active buzzer to alert the user. It is designed to be integrated into smart goggles for driver safety and fatigue monitoring.

---

## Hardware Used
- ESP32 Development Board  
- IR Eye Blink Sensor (Analog Output)  
- Active Buzzer  
- Jumper Wires  
- Power Supply / Battery  

---

## Software Used
- Arduino IDE  
- ESP32 Board Package  

---

## Pin Configuration
| Component | ESP32 Pin |
|---------|-----------|
| IR Sensor (Analog OUT) | GPIO 34 |
| Active Buzzer | GPIO 26 |
| VCC | 3.3V |
| GND | GND |

---

## Working Principle
1. The IR sensor continuously measures eye activity.
2. On startup, the system performs calibration:
   - Reads values when eyes are open
   - Reads values when eyes are closed
3. A threshold is calculated automatically.
4. If eyes remain closed for more than 2 seconds, the buzzer is activated.
5. Alarm stops when eyes open again.

---

## Algorithm
1. Initialize ESP32, buzzer, and serial monitor  
2. Calibrate IR sensor (open and closed eye values)  
3. Read sensor values continuously  
4. Compare values with threshold  
5. If eye closed duration ≥ preset time:
   - Trigger buzzer  
6. Stop buzzer when eye opens  

---

## Code Parameters
- `IR_PIN` : Analog pin for IR sensor  
- `BUZZER_PIN` : Digital pin for buzzer  
- `T_CLOSED` : Eye closure time threshold (seconds)  
- `SAMPLE_INTERVAL_MS` : Sampling delay  
- `CAL_SAMPLES` : Number of samples for calibration  

---

## Calibration Process
- User keeps eyes open for calibration
- User keeps eyes closed for calibration
- Average values are calculated
- Threshold is set dynamically to improve accuracy

---

## Applications
- Driver drowsiness detection  
- Accident prevention systems  
- Smart wearable devices  
- Fatigue monitoring  

---

## Future Enhancements
- Bluetooth or Wi-Fi alerts  
- Mobile app integration  
- Camera-based eye detection  
- GPS emergency notification  

---

## Project Structure
Smart-Goggle-Drowsiness-Detector/
│
├── smart_goggle_drowsiness.ino
├── README.md

---

## 👨‍💻 Developed By
<p id="dev"></p>

## 📜 License
<p id="lic"></p>

<script>
const devText = "Tanishq Narayan | IT Engineering";
const licText = "This project is developed for academic and learning purposes.";

let i = 0, j = 0;

function typeDev() {
  if (i < devText.length) {
    document.getElementById("dev").innerHTML += devText.charAt(i);
    i++;
    setTimeout(typeDev, 80);
  } else {
    setTimeout(typeLic, 500);
  }
}

function typeLic() {
  if (j < licText.length) {
    document.getElementById("lic").innerHTML += licText.charAt(j);
    j++;
    setTimeout(typeLic, 60);
  }
}

typeDev();
</script>