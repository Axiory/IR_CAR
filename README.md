# IR_CAR
A Infrared remote controlled car
# IR Remote Controlled Motor Driver

## Description
This project controls a motor driver using an IR remote. The Arduino receives IR signals from the remote and translates them into motor movements (forward, backward, left, right, and stop). The motor driver is controlled using PWM signals for speed control and digital signals for direction control.

## Components Required
- Arduino board
- L298N motor driver
- Two DC motors
- IR remote
- IR receiver module (connected to pin 11)
- Connecting wires
- Power supply (battery or adapter)

## Pin Configuration
- **IR Receiver**: Connected to pin 11
- **Motor Driver Pins**:
  - ENA: Pin 5 (Speed control for motor A)
  - ENB: Pin 10 (Speed control for motor B)
  - IN1: Pin 6
  - IN2: Pin 7
  - IN3: Pin 8
  - IN4: Pin 9

## How It Works
1. The IR receiver detects signals from the remote and decodes them.
2. The Arduino reads the decoded signal and compares it with predefined IR codes.
3. Based on the received IR signal:
   - **Forward (0xE718FF00)**: Both motors move forward at full speed.
   - **Backward (0xE31CFF00)**: Both motors move backward at full speed.
   - **Left (0xF708FF00)**: The right motor moves forward while the left motor stops.
   - **Right (0x55AFF00)**: The left motor moves forward while the right motor stops.
   - **Stop (Any other signal)**: Both motors stop.
4. The loop continuously checks for IR signals and updates the motor states accordingly.

## Setup Instructions
1. Connect the IR receiver to pin 11 of the Arduino.
2. Connect the motor driver to the Arduino as per the pin configuration.
3. Upload the provided code to the Arduino using the Arduino IDE.
4. Power up the Arduino and motor driver.
5. Use the IR remote to control the motors.

## Code Overview
- Uses the **IRremote** library to decode IR signals.
- Reads the raw IR signal and checks against predefined commands.
- Controls motor driver inputs to move the motors accordingly.
- Uses **analogWrite()** to control motor speed via PWM.

## Troubleshooting
- If the motors do not move:
  - Check power connections to the motor driver.
  - Ensure the correct IR remote codes are used.
  - Verify the IR receiver is properly connected and receiving signals.
- If movement is incorrect:
  - Swap motor connections if they move in the wrong direction.
  - Check the remote’s signal values by printing them in the Serial Monitor.

## Notes
- Ensure the **IRremote** library is installed in the Arduino IDE.
- Modify IR codes in the code if your remote uses different values.
- Adjust PWM values in **analogWrite()** to control motor speed.

This project provides a simple way to wirelessly control motors using an IR remote, making it ideal for robotic applications and automation projects.

