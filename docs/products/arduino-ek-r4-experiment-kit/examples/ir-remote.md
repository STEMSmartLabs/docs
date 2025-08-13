# IR Remote Decode

Read codes from the IR receiver.

## Wiring
- OUT→D6 (example), VCC→5V, GND→GND

## Code
```cpp
#include <IRremote.h>

const int RECV_PIN = 6;

void setup() {
  Serial.begin(115200);
  IrReceiver.begin(RECV_PIN, ENABLE_LED_FEEDBACK);
}

void loop() {
  if (IrReceiver.decode()) {
    Serial.println(IrReceiver.decodedIRData.decodedRawData, HEX);
    IrReceiver.resume();
  }
}
```
