# Line Following Robot 

##  Objective
This project was developed as part of the **Robotics and Automation** curriculum to design and implement a **line-following robot** using the **STM32 microcontroller** that autonomously follows a predefined path marked by a black line on a light-colored surface.  
The robot utilizes an **IR sensor array** for path detection and **PWM-based motor control** for precise maneuvering.

---

##  Project Overview
The robot employs a **three-sensor feedback mechanism** to detect the line and adjust motor speed accordingly:

1. **Center Sensor Active** → Move straight (equal PWM on both motors)  
2. **Left Sensor Active** → Turn left (increase right motor speed)  
3. **Right Sensor Active** → Turn right (increase left motor speed)  
4. **Center + Side Active** → Sharp turn using differential speed control  
5. **All High/Low** → Stop condition (end of path or off-track)

---

##  Skills Demonstrated
- **STM32 microcontroller programming** using HAL libraries and Keil uVision  
- **PWM generation** for motor speed and direction control  
- **Digital sensor interfacing** for real-time line detection  
- **Embedded control logic design** for decision-based robot movement  
- **Motor driver interfacing** with dual DC motors  
- **Mechanical design and assembly** using laser-cut acrylic chassis  
- **Encoder feedback integration** for motor position and velocity tracking  

---

##  Tools & Technologies Used
| Category | Tools / Components |
|-----------|--------------------|
| **Microcontroller** | STM32F103C8T6 (Blue Pill) |
| **Sensors** | IR Line Sensors (Left, Center, Right) |
| **Motor Driver** | L298N Dual H-Bridge |
| **Actuators** | DC Motors with Encoders |
| **Chassis** | Laser-cut Acrylic (280mm × 210mm) |
| **Development Tools** | Keil uVision, STM32CubeIDE |
| **Peripherals Used** | PWM (TIM2), GPIO (A2, A5, B0), Encoder Inputs (A6-A7, B6-B7) |

---

##  Implementation Summary
- Designed and fabricated **custom acrylic chassis** (280mm × 210mm).  
- Configured **IR sensors** on GPIO pins A2 (Left), A5 (Center), B0 (Right).  
- Implemented **PWM motor control** on pins A0 (Right Motor) and A1 (Left Motor).  
- Developed **decision logic** for differential turning based on sensor states.  
- Integrated **encoder feedback** for position monitoring on pins A6–A7 and B6–B7.  
- Tuned **PWM values** (range: 6000–15000) to overcome static friction and ensure smooth motion.  

---

##  Results & Testing
| Parameter | Description | Result |
|------------|-------------|--------|
| Path Tracking | Smooth following of black line | ✅ |
| Turn Control | Accurate turning using PWM differential | ✅ |
| Sensor Reliability | Stable detection with threshold tuning | ✅ |
| Mechanical Stability | Balanced chassis, smooth movement | ✅ |
| Startup Response | No stalling, immediate motor response | ✅ |

---

## 📄 Full Project Report

You can read the complete report here: [**Line Following Robot – Full PDF Report**](./Robotics_Report.pdf)

---


##  Contact
**Muhammad Huzaifa**  

📧 [huzaifazahid888@gmail.com](mailto:huzaifazahid888@gmail.com)  
🔗 [linkedin.com/in/huzaifa-engineer](https://linkedin.com/in/huzaifa-engineer)
