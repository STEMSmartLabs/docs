# DHT11 Temperature & Humidity

Read ambient temperature and humidity.

## Wiring
- DHT11 OUT→D8; VCC→5V; GND→GND

## Code
```cpp
#include <DHT.h>

#define DHTPIN 8
#define DHTTYPE DHT11

DHT dht(DHTPIN, DHTTYPE);

void setup() {
  Serial.begin(115200);
  dht.begin();
}

void loop() {
  float h = dht.readHumidity();
  float t = dht.readTemperature();
  if (isnan(h) || isnan(t)) {
    Serial.println("Sensor error");
    delay(2000);
    return;
  }
  Serial.print("T: "); Serial.print(t);
  Serial.print(" C  H: "); Serial.println(h);
  delay(2000);
}
```
