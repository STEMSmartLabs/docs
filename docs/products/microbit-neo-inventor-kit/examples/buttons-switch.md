# Button & Switch Input

Read a momentary button on D12.

## Wiring
- Button→D12 to GND with INPUT_PULLUP

## Code
```cpp
void setup() {
  Serial.begin(115200);
  pinMode(12, INPUT_PULLUP);
}

void loop() {
  bool pressed = (digitalRead(12) == LOW);
  Serial.print("Button pressed: ");
  Serial.println(pressed ? "YES" : "NO");
  delay(200);
}
```
