# Edge Impulse: Vibration Classifier

Train a TinyML model for vibration patterns and deploy as an Arduino library.

## Wiring
- Sensor SIG→A0, 5V, GND

## Code
```cpp
// Skeleton: sample A0 @100 Hz and run classifier()
#include <your_edge_impulse_inference.h>

void setup() { Serial.begin(115200); }

void loop() {
  // Fill signal buffer from analogRead(A0) ...
  // ei_impulse_result_t result = run_classifier(&signal, &result, false);
  // if (result.classification[0].value > 0.8) { /* act */ }
}
```
