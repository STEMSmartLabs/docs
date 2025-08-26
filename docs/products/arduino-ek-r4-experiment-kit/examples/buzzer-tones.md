# Buzzer Tones

Play tones on a passive buzzer.

## Wiring
- \+ → D11, − → GND

## Code
```cpp
#define BUZZ 11

void setup() { pinMode(BUZZ, OUTPUT); }

void play(int f, int ms) { tone(BUZZ, f, ms); delay(ms + 20); }

void loop() {
  play(440, 250);
  play(660, 250);
  play(880, 250);
  delay(500);
}
```
