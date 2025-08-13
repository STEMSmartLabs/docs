# Blink LED

Blink an LED on D3.

## Wiring
- D3 → resistor → LED → GND

## Code
```cpp
const int LED = 3;

void setup() {
  pinMode(LED, OUTPUT);
}

void loop() {
  digitalWrite(LED, HIGH);
  delay(500);
  digitalWrite(LED, LOW);
  delay(500);
}
```
