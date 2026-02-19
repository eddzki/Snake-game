# Arduino 1602 LCD Snake Game #

A non-blocking Snake game for Arduino using a 1602 character LCD and an analog joystick. It uses `millis()` for input polling instead of `delay()` to maintain responsive joystick controls, preventing dropped inputs during the game loop.

## Hardware Requirements ##
* Arduino (Uno, Nano, or Mega)
* 1602A LCD Display with I2C Backpack (PCF8574 or similar)
* Analog Joystick Module

## Wiring Connections ##


**LCD I2C Backpack -> Arduino**
* VCC -> 5V
* GND -> GND
* SDA -> A4
* SCL -> A5

**Analog Joystick -> Arduino**
* VCC -> 5V
* GND -> GND
* X-Axis -> A0
* Y-Axis -> A1
* Switch -> D2

*Note: Analog pin A2 is left unconnected intentionally. It is read by the code to generate a random seed for food placement.*

## Dependencies ##
You need to install the following library via the Arduino IDE Library Manager or `arduino-cli`:
* **LiquidCrystal I2C** by Frank de Brabander

## Setup Instructions ##
1. Connect the hardware according to the wiring list.
2. Install the required LiquidCrystal I2C library.
3. Open the `.ino` file in your Arduino IDE.
4. Verify your LCD's I2C address. The code defaults to `0x27`. If your screen backlight turns on but no text appears (and your contrast potentiometer is adjusted correctly), change line 5 from `0x27` to `0x3F`.
5. Compile and upload the code to your Arduino.

## Controls ##
* Move the joystick Up, Down, Left, or Right to control the snake.
* Press the joystick button straight down to pause and resume the game.
