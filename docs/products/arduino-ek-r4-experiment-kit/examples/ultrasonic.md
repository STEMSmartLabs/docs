# Ultrasonic Distance

Measure distance using HC‑SR04.

## Wiring
- TRIG→D4, ECHO→D7, VCC→5V, GND→GND

## Code
```cpp
const int TRIG = 4;
const int ECHO = 7;

long microsecondsToCm(long us) { return us / 29 / 2; }

void setup() {
  Serial.begin(115200);
  pinMode(TRIG, OUTPUT);
  pinMode(ECHO, INPUT);
}

void loop() {
  digitalWrite(TRIG, LOW); delayMicroseconds(2);
  digitalWrite(TRIG, HIGH); delayMicroseconds(10);
  digitalWrite(TRIG, LOW);
  long duration = pulseIn(ECHO, HIGH, 30000);
  long cm = microsecondsToCm(duration);
  Serial.print(cm); Serial.println(" cm");
  delay(300);
}
```
