# Line Following Robot

This was a Robotics and Automation course project, a small robot built on an STM32 that follows a black line on a light surface on its own, using an IR sensor array to detect the line and PWM-controlled motors to steer.

## What it does

Three IR sensors (left, center, right) sit at the front of the robot and read the line as it moves. Depending on which sensors are picking up the line, the robot adjusts each motor's speed to stay on track:

- Center sensor active: go straight, equal PWM on both motors
- Left sensor active: turn left by speeding up the right motor
- Right sensor active: turn right by speeding up the left motor
- Center plus one side active: sharper turn using a bigger difference in motor speed
- All sensors high or all low: stop, since it means the robot has reached the end of the path or gone off track

## How it's built

- STM32F103C8T6 (Blue Pill) programmed with HAL libraries in Keil uVision.
- IR sensors wired to GPIO pins A2 (left), A5 (center), and B0 (right).
- Motor control through PWM on pins A0 and A1, driving the motors through an L298N dual H-bridge.
- Encoder feedback wired on pins A6/A7 and B6/B7 for tracking motor position and speed.
- Chassis is custom laser-cut acrylic, 280mm by 210mm.
- Spent some time tuning the PWM range (roughly 6000 to 15000) since anything lower didn't have enough force to overcome the motors' static friction and the robot wouldn't move smoothly.

## Tools used

STM32F103C8T6, Keil uVision, STM32CubeIDE, L298N motor driver, DC motors with encoders, IR line sensors, laser-cut acrylic chassis.

## Result

The robot tracked the line smoothly, turned accurately using the differential PWM logic, and the sensors gave stable readings once the detection threshold was tuned properly. The chassis stayed balanced during movement and the robot responded immediately at startup without stalling.

## Full report

The complete write-up is in this repo: [Line Following Robot – Full PDF Report](./Robotics_Report.pdf)
