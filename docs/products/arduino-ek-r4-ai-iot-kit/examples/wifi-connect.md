# WiFi Connect & Ping

Connect to WiFi, print IP, and ping a host.

## Wiring
- Update `ssid` / `pass` before uploading.

## Code
```cpp
#include <WiFiS3.h>

const char* ssid = "YOUR_SSID";
const char* pass = "YOUR_PASS";

void setup() {
  Serial.begin(115200);
  Serial.print("Connecting to ");
  Serial.println(ssid);

  if (WiFi.begin(ssid, pass) != WL_CONNECTED) {
    Serial.println("WiFi connect failed");
    return;
  }

  Serial.print("Connected! IP: ");
  Serial.println(WiFi.localIP());
}

void loop() {
  static unsigned long t = 0;
  if (millis() - t > 3000) {
    t = millis();
    int r = WiFi.ping("8.8.8.8");
    Serial.print("Ping: ");
    Serial.println(r);
  }
}
```
