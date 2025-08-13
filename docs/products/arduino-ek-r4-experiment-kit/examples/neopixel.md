# NeoPixel Ring Patterns

Animate the 8‑LED ring on D5.

## Wiring
- DIN→D5, VCC→5V, GND→GND

<div class="video-wrapper"><iframe src="https://www.youtube.com/embed/mvdJesc4Bp0" title="NeoPixel Ring Patterns" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe></div>

## Code
```cpp
#include <Adafruit_NeoPixel.h>

#define PIN 5
#define N   8

Adafruit_NeoPixel strip(N, PIN, NEO_GRB + NEO_KHZ800);

void setup() {
  strip.begin();
  strip.show();
}

void colorWipe(uint32_t c, uint8_t wait) {
  for (int i = 0; i < N; i++) {
    strip.setPixelColor(i, c);
    strip.show();
    delay(wait);
  }
}

void loop() {
  colorWipe(strip.Color(255, 0, 0), 50);
  colorWipe(strip.Color(0, 255, 0), 50);
  colorWipe(strip.Color(0, 0, 255), 50);
}
```
