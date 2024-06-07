## 🦾 Phần Cứng

<iframe width="766" height="543" src="https://www.youtube.com/embed/vwZRSlxhgT8" title="Demo Hệ Thống Tản Nhiệt | Cơ sở và Ứng dụng IoT | HCMUTE" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

```c++
#define up 16
#define dw 18
#define mode1 15
#define relay1 12
#define relay2 13

#include <Wire.h>
#include <LiquidCrystal_I2C.h>
#include <Arduino.h>
#include <WiFi.h>
#include <WebSocketsClient.h>
#include <ArduinoJson.h>

LiquidCrystal_I2C lcd(0x27, 16, 2); // Địa chỉ I2C của màn hình LCD

const char *ssid = "khanh";
const char *password = "123456789*";
const char *serverAddress = "server-iot-54eb32613657.herokuapp.com";
const int serverPort = 80;

const int lm35Pin1 = 34; // Chân nối cảm biến LM35 thứ nhất
const int lm35Pin2 = 35; // Chân nối cảm biến LM35 thứ hai

WebSocketsClient webSocket;
int rl1 = 0;
int rl2 = 0;
int n = 0;
int tt = 0;
int t_set1 = 34;
int t_set2 = 34;
float temp1 = 0;
float temp2 = 0;
float sum1 = 0, sum2 = 0;
int readings = 50; // Số lần đọc để lấy trung bình

bool relay1ControlledByWebSocket = false;
bool relay2ControlledByWebSocket = false;

void setup() {
  Serial.begin(115200);
  pinMode(up, INPUT); // CẤU HÌNH NÚT NHẤN UP LÀ NGÕ VÀO
  pinMode(dw, INPUT);
  pinMode(mode1, INPUT);
  pinMode(relay1, OUTPUT);
  pinMode(relay2, OUTPUT);
  lcd.init(); // Khởi động màn hình LCD
  lcd.backlight(); // Bật đèn nền cho màn hình LCD
  lcd.clear(); // Xóa màn hình LCD

  // Connect to Wi-Fi
  WiFi.begin(ssid, password);
  while (WiFi.status() != WL_CONNECTED) {
    delay(1000);
    Serial.println("Connecting to WiFi...");
  }
  Serial.println("Connected to WiFi");

  // Connect to WebSocket server
  webSocket.begin(serverAddress, serverPort, "/");
  webSocket.onEvent(webSocketEvent);
  webSocket.setReconnectInterval(5000);
}

void webSocketEvent(WStype_t type, uint8_t *payload, size_t length) {
  switch (type) {
    case WStype_DISCONNECTED:
      Serial.println("WebSocket disconnected");
      break;
    case WStype_CONNECTED:
      Serial.println("WebSocket connected");
      break;
    case WStype_TEXT:
      String message = String((char*)payload);
      if (message == "{\"type\":\"fanControl\",\"status\":\"on\"}") {
        digitalWrite(relay1, LOW);
        digitalWrite(relay2, LOW); // Turn on relay1
        relay1ControlledByWebSocket = true;
        Serial.println("Relay1 turned ON");
      } else if (message == "{\"type\":\"fanControl\",\"status\":\"off\"}") {
        digitalWrite(relay1, HIGH);
        digitalWrite(relay2, HIGH); // Turn off relay1
        relay1ControlledByWebSocket = false;
        Serial.println("Relay1 turned OFF");
      }
      break;
    // case WStype_BIN:
    //   // Handle binary data
    //   break;
    // case WStype_ERROR:
    // case WStype_FRAGMENT_TEXT_START:
    // case WStype_FRAGMENT_BIN_START:
    // case WStype_FRAGMENT:
    // case WStype_FRAGMENT_FIN:
    //   break;
  }
}

void kt_nd() {
  sum1 += analogRead(lm35Pin1);
  sum2 += analogRead(lm35Pin2);
  n++;
  if (n == readings) {
    temp1 = (sum1 / 8.19) / readings;
    temp2 = (sum2 / 8.19) / readings;
    n = 0;
    sum1 = 0;
    sum2 = 0;
  }
}

void ht_nd() {
  // Hiển thị nhiệt độ lên màn hình LCD
  lcd.setCursor(0, 0);
  lcd.print("Temp1: ");
  lcd.print(temp1);
  lcd.print(" C");
  lcd.setCursor(0, 1);
  lcd.print("Temp2: ");
  lcd.print(temp2);
  lcd.print(" C");
}

void ht_nd_nguong() {
  // Hiển thị nhiệt độ lên màn hình LCD
  lcd.setCursor(0, 0);
  lcd.print("Temp_set1: ");
  lcd.print(t_set1);
  lcd.print(" C");

  lcd.setCursor(0, 1);
  lcd.print("Temp_set2: ");
  lcd.print(t_set2);
  lcd.print(" C");
}

void ktxl_nn_mode1() {
  if (digitalRead(mode1) == 0) {
    delay(60);
    if (digitalRead(mode1) == 0) {
      lcd.clear();
      if (tt == 0) {
        tt = 1;
        ht_nd_nguong();
      }
    }
  }
  if (digitalRead(mode1) == 0) {
    delay(60);
    if (digitalRead(mode1) == 0) {
      lcd.clear();
      if (tt == 1) {
        tt = 0;
        ht_nd();
      }
    }
  }
}

void ktxl_nn() {
  if (digitalRead(up) == 0) {
    delay(60);
    if (digitalRead(up) == 0 && (t_set1 < 70) && (t_set2 < 70)) {
      t_set1++;
      t_set2++;
    }
  }
  if (digitalRead(dw) == 0) {
    delay(60);
    if (digitalRead(dw) == 0 && (t_set1 > 25) && (t_set2 > 25)) {
      t_set1--;
      t_set2--;
    }
  }
}

void dk_dc() {
  kt_nd();
  ht_nd();
  if (!relay1ControlledByWebSocket) {
    if (temp1 > t_set1) {
      digitalWrite(relay2, LOW);
      rl2 = 1;
    } else {
      digitalWrite(relay2, HIGH);
      rl2 = 0;
    }
  }
  if (!relay1ControlledByWebSocket) {
    if (temp2 > t_set2) {
      digitalWrite(relay1, LOW);
      rl1 = 1;
    } else {
      digitalWrite(relay1, HIGH);
      rl1 = 0;
    }
  }
}

void loop() {
  kt_nd();
  ktxl_nn_mode1();
  ktxl_nn();
  if (tt == 0) {
    ht_nd();
    dk_dc();
  }
  if (tt == 1) {
    ht_nd_nguong();
  }

  webSocket.loop();

  // Send a message every 5 seconds
  static unsigned long lastMillis = 0;
  if (millis() - lastMillis > 5000) {
    StaticJsonDocument<200> doc;
    doc["type"] = "sensorData";
    JsonObject status = doc.createNestedObject("status");
    status["temp1"] = temp1;
    status["temp2"] = temp2;
    status["relay1"] = rl1;
    status["relay2"] = rl2;
    char jsonBuffer[200];
    serializeJson(doc, jsonBuffer);

    // Send JSON data via WebSocket
    webSocket.sendTXT(jsonBuffer);
    Serial.println(jsonBuffer);
    lastMillis = millis();
  }
}
```
