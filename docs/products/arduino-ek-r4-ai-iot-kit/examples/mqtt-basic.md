# MQTT Publish/Subscribe

Send telemetry and handle a simple LED command via MQTT.

## Wiring
- Broker: `test.mosquitto.org` (demo)

## Code
```cpp
#include <WiFiS3.h>
#include <PubSubClient.h>

WiFiClient net;
PubSubClient mqtt(net);

const char* ssid = "YOUR_SSID";
const char* pass = "YOUR_PASS";

const char* host = "test.mosquitto.org";
const int   port = 1883;

const char* pubTopic = "stemsl/telemetry";
const char* subTopic = "stemsl/cmd";

void onMsg(char* topic, byte* payload, unsigned int len) {
  String s;
  for (unsigned int i = 0; i < len; i++) s += (char)payload[i];
  if (s == "led:on")  { pinMode(3, OUTPUT); digitalWrite(3, HIGH); }
  if (s == "led:off") { digitalWrite(3, LOW); }
}

void setup() {
  Serial.begin(115200);
  WiFi.begin(ssid, pass);
  while (WiFi.status() != WL_CONNECTED) { delay(500); }
  mqtt.setServer(host, port);
  mqtt.setCallback(onMsg);
}

void loop() {
  if (!mqtt.connected()) {
    if (mqtt.connect("stemsl-ekr4")) mqtt.subscribe(subTopic);
  }
  mqtt.loop();

  static unsigned long t = 0;
  if (millis() - t > 2000) {
    t = millis();
    int v = analogRead(A0);
    String msg = String("{"a0":") + v + "}";
    mqtt.publish(pubTopic, msg.c_str());
  }
}
```
