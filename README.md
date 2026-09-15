# Gas + Fire Alarm System (Arduino)

An Arduino Uno project that continuously monitors a gas sensor and a fire sensor, and triggers a visual (LED) and audible (buzzer) alarm when a gas leak or fire is detected.

## How It Works

The sketch reads two sensors in a continuous loop:

- **Gas sensor** (analog, pin `A0`): reads a value representing gas concentration.
- **Fire sensor** (digital, pin `2`): reads `HIGH`/`LOW` depending on whether fire/flame is detected.

If the gas reading reaches or exceeds a threshold (`300`) **or** the fire sensor reports `HIGH`, the system triggers an alarm:

- Turns the LED (pin `13`) **ON**
- Turns the buzzer (pin `8`) **ON**
- Prints `!!! ALARM !!!` to the Serial Monitor

Otherwise, the LED and buzzer stay off, and the current sensor readings are printed to the Serial Monitor every loop.

## Hardware Requirements

- Arduino Uno (or compatible board)
- Gas sensor module (e.g., MQ-2) connected to pin `A0`
- Fire/flame sensor module connected to digital pin `2`
- LED connected to pin `13` (built-in LED can be used)
- Buzzer connected to pin `8`
- Jumper wires and breadboard

## Wiring Summary

| Component     | Arduino Pin |
|----------------|-------------|
| Gas sensor     | A0          |
| Fire sensor    | 2           |
| LED            | 13          |
| Buzzer         | 8           |

## Software Requirements

- [Arduino IDE](https://www.arduino.cc/en/software) (or PlatformIO)

## Uploading the Sketch

1. Open `Robotics_Arduino.ino` in the Arduino IDE.
2. Select your board: **Tools > Board > Arduino Uno**.
3. Select the correct COM port: **Tools > Port**.
4. Click **Upload**.
5. Open **Tools > Serial Monitor** (baud rate `9600`) to see live sensor readings.

## Example Serial Output

```
Gas: 120 | Fire: 0
Gas: 145 | Fire: 0
Gas: 310 | Fire: 0
!!! ALARM !!!
```

## Possible Improvements

- Make the gas threshold configurable instead of hardcoded (`300`).
- Add a way to silence/reset the alarm without restarting the board.
- Log alarm events with timestamps if a real-time clock module is added.

## License

Add a license of your choice (e.g., MIT) here.
