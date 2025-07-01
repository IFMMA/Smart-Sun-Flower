1 | Overview
This project keeps two small solar panels pointed at the brightest light source by comparing readings from four light-dependent resistors (LDRs) and moving two servos in horizontal (azimuth) and vertical (elevation) axes.
Perfect as a classroom demo or a starting point for full-size trackers.

## 🔧 Features
- Tracks sunlight in two axes using LDR sensors
- Moves panel using servo motors
- Real-time light sensing and adjustment
- Low-cost and scalable

2 |📦 Components Used
| Qty | Component                  | Example Part No. | Notes                              |
| --- | -------------------------- | ---------------- | ---------------------------------- |
| 1   | **Arduino Uno**            | A000066          | Any ATmega328P board works         |
| 2   | **Micro 6 V hobby servo**  | SG90             | One for azimuth, one for elevation |
| 4   | **LDR (photo-resistor)**   | GL5528           | 5 mm common type                   |
| 4   | 10 kΩ **resistor**         | ¼ W              | Voltage divider for LDRs           |
| 2   | **Mini solar panel**       | 5 V / 100 mA     | Demonstration panels               |
| 1   | Half-size **breadboard**   | –                | For quick wiring                   |
| -   | **Male-male jumper wires** | –                | Flexible dupont leads              |
| 1   | **USB A-B cable**          | –                | Programming & power                |
| -   | Acrylic Platform           | or 3D printed    | to mount components                |

3 | Circuit Diagram (دائرة التوصيل)
![image](https://github.com/user-attachments/assets/4a061dcf-ebe1-43c7-bb2f-64091c055cae)

4 | 📝 How it Works
|        Block          |                             Purpose                              |
| --------------------- | ---------------------------------------------------------------- |
| **Read sensors**      | Four `analogRead()` calls give light intensity (0-1023).         |
| **Average & compare** | Differences between top/bottom and left/right decide motion.     |
| **Move servos**       | If difference exceeds `tol`, increment or decrement angle by 1°. |
| **Limits**            | Stops at predefined min/max to protect wiring.                   |

Key wiring points:

Arduino Pin        	Connected To	                 Purpose
   A0              	LDR - bottom-right        	Analog light input
   A1	              LDR - top-right	
   A2	              LDR - top-left	
   A3	              LDR - bottom-left	
   D2	              Servo 1 signal	           Horizontal (azimuth)
   D4               	Servo 2 signal	         Vertical (elevation)
   5V	              LDR + Servo Vcc	               Power rail
  GND	              LDR + Servo GND             	Common ground

Tip: If servos jitter when USB-powered, feed them from an external 5V supply (share GND with Arduino).


5 | 🚀 Future Improvements
- Add real-time data logging
- Use solar panel output to auto-adjust sensitivity
- Weather protection
  
6 | Key Benefits
This system provides an excellent opportunity to explore renewable energy technologies while increasing the efficiency of solar panels. It's an engaging and practical project for anyone interested in Arduino and sustainable energy solutions.
  

7 | Refrences
https://simplecircuitslol.blogspot.com/2024/12/solar-tracking-system.html
https://www.youtube.com/watch?v=zXX4d5eyvb8
for 3D printed parts : https://drive.google.com/file/d/1X7swlCgIOaA7oxch0vdxHGQf87q6AdvF/view
Feel free to fork, modify, or build upon it.

---
