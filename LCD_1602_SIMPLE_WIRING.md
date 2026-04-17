# LCD 1602 Wiring Instructions (Without Potentiometer)

This document outlines the simplified wiring instructions for connecting an LCD 1602 display directly to an Arduino without using a potentiometer for contrast adjustment.

## Components Needed:
- Arduino Board (e.g., Arduino Uno)
- LCD 1602 Display Module
- Jumper Wires
- Breadboard (optional)

## Wiring Connections:

| LCD Pin | Arduino Pin | Description |
|---------|-------------|-------------|
| 1 (VSS)  | GND         | Ground      |
| 2 (VDD)  | 5V          | Power       |
| 3 (V0)   | Directly to +5V | Contrast (fixed) |
| 4 (RS)   | Pin 12      | Register Select |
| 5 (RW)   | GND         | Read/Write (set to GND) |
| 6 (E)    | Pin 11      | Enable      |
| 7 (D0)   | Not Used    | Data 0     |
| 8 (D1)   | Not Used    | Data 1     |
| 9 (D2)   | Not Used    | Data 2     |
| 10 (D3)  | Not Used    | Data 3     |
| 11 (D4)  | Pin 5       | Data 4     |
| 12 (D5)  | Pin 4       | Data 5     |
| 13 (D6)  | Pin 3       | Data 6     |
| 14 (D7)  | Pin 2       | Data 7     |
| 15 (A)   | 5V          | LED Anode  |
| 16 (K)   | GND         | LED Cathode |

## Notes:
- Connecting the V0 pin (pin 3) directly to 5V means that the contrast will be fixed and may not be adjustable. This is suitable for many applications where a known good contrast is acceptable.
- Ensure all connections are secure to prevent circuit issues.

## Example Code:
Here's a simple code snippet to test the LCD:
```cpp
#include <LiquidCrystal.h>

LiquidCrystal lcd(12, 11, 5, 4, 3, 2);

void setup() {
  lcd.begin(16, 2);
  lcd.print("Hello, World!");
}

void loop() {
  // Do nothing here
}
```
