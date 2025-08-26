# Trimpot Analog Read

Use A1 to read a potentiometer.

## Wiring
- Wiper→A1, ends→5V/GND

## Code
```cpp
void setup() { Serial.begin(115200); }

void loop() {
  int v = analogRead(A1);
  float pct = (v / 1023.0) * 100.0;
  Serial.print("A1="); Serial.print(v); Serial.print(" (~");
  Serial.print(pct, 1); Serial.println("%)");
  delay(200);
}
```
