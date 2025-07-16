# Arduino 7-Segment Display – Digit Cycle Project

This project uses an **Arduino Uno** to display the digits **0 to 9** sequentially on a **7-segment display**. Each digit is displayed for one second using dedicated functions. The project is created and tested using [Tinkercad Circuits](https://www.tinkercad.com/things/cMP2VZTr09F-copy-of-arduino-7-segment-display).

---

## 🔧 Components Used

- Arduino Uno
- 7-Segment Display (Common Cathode)
- 220Ω Resistors (×8)
- Breadboard
- Jumper Wires

---

## 📍 Pin Configuration

| Segment | Arduino Pin |
|---------|-------------|
| A       | 13          |
| B       | 12          |
| C       | 11          |
| D       | 10          |
| E       | 9           |
| F       | 8           |
| G       | 7           |
| DP (Decimal Point) | 6 |

> **Note:** The decimal point (pin H) is used in some digits like 2–4, 6, and 7 for variation.

---

## 🔌 Circuit Diagram

![7 Segment Display Circuit](circuit.png)

> *The image above shows the wiring of the 7-segment display to Arduino using resistors and digital pins D13 to D6.*

---

## 💻 Code Overview

The Arduino sketch defines one function for each digit (`zero()` to `nine()`), where each function lights up the necessary segments. The main `loop()` calls these functions one by one with a 1-second delay.

### ▶️ Code Behavior:
- All segment pins are declared as constants.
- Each digit is shown for 1 second using `delay(1000);`.
- Segment H (pin 6) controls the decimal point and is optional.

---

### 🧠 Example Function: `three()`
```cpp
void three(void) {
  digitalWrite(A, HIGH);
  digitalWrite(B, HIGH);
  digitalWrite(C, HIGH);
  digitalWrite(D, HIGH);
  digitalWrite(E, LOW);
  digitalWrite(F, LOW);
  digitalWrite(G, HIGH);
  digitalWrite(H, HIGH);
}
