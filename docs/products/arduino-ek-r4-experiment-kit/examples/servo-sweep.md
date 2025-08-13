# Servo Sweep

Sweep a micro servo on D9.

## Wiring
- Signal→D9, VCC→5V, GND→GND

## Code
```cpp
#include <Servo.h>

Servo s;

void setup() { s.attach(9); }

void loop() {
  for (int a = 0; a <= 180; a += 2) { s.write(a); delay(15); }
  for (int a = 180; a >= 0; a -= 2) { s.write(a); delay(15); }
}
```
