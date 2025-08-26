# OLED Hello

Display text on the I2C OLED.

## Wiring
- VCC→5V, GND→GND, SCL→SCL, SDA→SDA

## Code
```cpp
#include <U8g2lib.h>

U8G2_SSD1306_128X64_NONAME_F_HW_I2C u8g2(U8G2_R0);

void setup() {
  u8g2.begin();
}

void loop() {
  u8g2.clearBuffer();
  u8g2.setFont(u8g2_font_ncenB08_tr);
  u8g2.drawStr(0, 24, "Hello EK R4!");
  u8g2.sendBuffer();
  delay(1000);
}
```
